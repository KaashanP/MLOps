# MLOps Project

A comprehensive MLOps project template for building, training, and deploying machine learning models.

## Project Structure

```
MLOps/
│
├── data/                   # Data directory (managed by DVC)
│   ├── raw/               # Raw, immutable data
│   ├── processed/         # Cleaned and processed data
│   └── external/          # External data sources
│
├── notebooks/             # Jupyter notebooks for exploration
│
├── src/                   # Source code
│   ├── data/             # Data loading and processing
│   ├── features/         # Feature engineering
│   ├── models/           # Model training and evaluation
│   └── visualization/    # Visualization scripts
│
├── models/               # Trained models (managed by DVC)
│
├── configs/              # Configuration files
│   └── config.yaml      # Main configuration
│
├── logs/                 # Training and execution logs
│
├── experiments/          # Experiment tracking
│
├── requirements.txt      # Python dependencies
├── .dvcignore           # DVC ignore patterns
├── .env.example         # Environment variables template
└── README.md            # This file
```

## Getting Started

### Prerequisites

- Python 3.9+
- pip or conda
- Git
- DVC (Data Version Control)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/KaashanP/MLOps.git
cd MLOps
```

2. Create a virtual environment:
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Copy environment variables:
```bash
cp .env.example .env
# Edit .env with your configurations
```

5. Initialize DVC (if not already initialized):
```bash
dvc init
```

## Usage

### Data Management with DVC

Track data files:
```bash
dvc add data/raw/dataset.csv
git add data/raw/dataset.csv.dvc .gitignore
git commit -m "Add raw dataset"
```

Pull data:
```bash
dvc pull
```

### Training Models

```bash
python src/models/train.py
```

### Experiment Tracking with MLflow

Start MLflow UI:
```bash
mlflow ui
```

Access at: http://localhost:5000

## MLOps Tools

- **DVC**: Data and model versioning
- **MLflow**: Experiment tracking and model registry
- **Git**: Code versioning
- **pytest**: Testing framework

## Development Workflow

1. Create a new branch for your feature
2. Make changes and track data with DVC
3. Track experiments with MLflow
4. Run tests: `pytest`
5. Commit code and push
6. Create a pull request

## Best Practices

- Always version your data with DVC
- Track all experiments with MLflow
- Write tests for your code
- Document your models and experiments
- Use configuration files for hyperparameters
- Never commit large data files or models to Git

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT License
