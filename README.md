# Finance App

This is a full-stack personal finance application that helps you track your income and expenses. It uses a Go backend, a React frontend, and a Python AI service for automatic transaction categorization.

## Features

- User registration and authentication
- Add, edit, and delete transactions
- Automatic transaction categorization using a machine learning model
- Dashboard with a summary of your financial situation
- View transactions by category
- Responsive design for mobile and desktop

## Tech Stack

- **Frontend:** React, TypeScript, Vite, Tailwind CSS
- **Backend:** Go, Gin
- **AI Service:** Python, Flask, Scikit-learn
- **Database:** PostgreSQL
- **Containerization:** Docker, Docker Compose

## Project Structure

```
finance-app/
├── categorizer-ai-service/ # Python AI service for transaction categorization
├── data/                   # Training data for the AI model
├── finance-backend-go/     # Go backend service
├── finance-frontend/       # React frontend application
├── models/                 # Trained AI models
├── docker-compose.yml      # Docker Compose configuration
├── init.sql                # Database initialization script
├── README.md               # This file
└── train.py                # Script to train the AI model
```

## Getting Started

### Prerequisites

- Docker
- Docker Compose

### Installation

1.  Clone the repository:

    ```bash
    git clone https://github.com/still-breath/finance-app-golang.git
    cd finance-app
    ```

2.  Create a `.env` file in the root directory and configure the environment variables. You can use the `.env.example` file as a template.

3.  Build and run the application using Docker Compose:

    ```bash
    docker-compose up --build
    ```

4.  The application will be available at the following URLs:

    -   **Frontend:** [http://localhost:3000](http://localhost:3000)
    -   **Backend:** [http://localhost:8080](http://localhost:8080)
    -   **AI Service:** [http://localhost:5000](http://localhost:5000)

## Training the AI Model

The AI model is trained on the data in the `data/training_data.xlsx` file. To retrain the model, you can run the `train.py` script:

### With Docker

```bash
docker-compose run --rm categorizer-ai python train.py
```

This will create new `model.pkl` and `vectorizer.pkl` files in the `models` directory.

### Locally

First, install the required Python libraries:

```bash
pip install -r requirements.txt
```

Then, run the training script:

```bash
python3 train.py
```

This will also create new `model.pkl` and `vectorizer.pkl` files in the `models` directory.

## API Endpoints

The backend API documentation is available at [http://localhost:8080/swagger/index.html](http://localhost:8080/swagger/index.html) when the application is running.

## Contributing

Contributions are welcome! Please feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License.
