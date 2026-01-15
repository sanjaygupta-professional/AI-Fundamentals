# CLAUDE.md - AI-Fundamentals Repository Guide

This document provides essential context for AI assistants working with the AI-Fundamentals codebase.

## Repository Overview

**AI-Fundamentals** is an educational repository focused on artificial intelligence concepts, implementations, and learning resources. The repository serves as a comprehensive guide for understanding AI from foundational principles to practical applications.

## Current Status

This is a new project. Create directories and files as needed following the planned structure below.

## Planned Project Structure

```
AI-Fundamentals/
├── CLAUDE.md              # AI assistant guidelines (this file)
├── README.md              # Project overview and getting started
├── docs/                  # Documentation and tutorials
│   ├── concepts/          # Theoretical AI concepts
│   ├── tutorials/         # Step-by-step guides
│   └── references/        # API references and cheat sheets
├── src/                   # Source code implementations
│   ├── algorithms/        # Core AI algorithm implementations
│   ├── models/            # Model architectures
│   ├── utils/             # Utility functions and helpers
│   └── examples/          # Working examples and demos
├── notebooks/             # Jupyter notebooks for interactive learning
├── data/                  # Sample datasets (small files only)
├── tests/                 # Unit and integration tests
└── requirements.txt       # Python dependencies
```

## Development Guidelines

### Code Style

- **Python**: Follow PEP 8 style guide
- Use type hints for function signatures
- Write docstrings for all public functions and classes
- Keep functions focused and under 50 lines when possible
- Use meaningful variable and function names

### File Naming Conventions

- Python files: `snake_case.py`
- Notebooks: `descriptive_name.ipynb`
- Documentation: `kebab-case.md` or `Title Case.md`
- Test files: `test_<module_name>.py`

### Documentation Standards

- Every module should have a corresponding documentation file
- Include code examples in documentation
- Keep explanations beginner-friendly when possible
- Add references to external resources where appropriate

## Key Commands

### Environment Setup

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# or
venv\Scripts\activate     # Windows

# Install dependencies
pip install -r requirements.txt
```

### Running Tests

```bash
# Run all tests
pytest tests/

# Run specific test file
pytest tests/test_<module>.py

# Run with coverage
pytest --cov=src tests/
```

### Linting and Formatting

```bash
# Format code
black src/ tests/

# Check linting
flake8 src/ tests/

# Type checking
mypy src/
```

## AI Assistant Guidelines

### When Working on This Repository

1. **Educational Focus**: All code and documentation should be educational. Prioritize clarity over cleverness.

2. **Progressive Complexity**: Organize content from basic to advanced. Start with fundamentals before diving into complex topics.

3. **Practical Examples**: Include runnable examples for every concept. Theory should be accompanied by implementation.

4. **Dependencies**: Prefer widely-used, well-maintained libraries (numpy, pandas, scikit-learn, pytorch, tensorflow).

5. **Comments**: Add explanatory comments for complex algorithms. Explain the "why" not just the "what".

### Content Categories

When adding new content, categorize appropriately:

- **Concepts**: Mathematical foundations, theory, principles
- **Algorithms**: Specific AI/ML algorithm implementations
- **Models**: Neural network architectures, model definitions
- **Tutorials**: Step-by-step learning guides
- **Examples**: Complete, runnable demonstration code

### Code Implementation Standards

```python
# Example of expected code style
from typing import List, Optional
import numpy as np

def calculate_loss(
    predictions: np.ndarray,
    targets: np.ndarray,
    reduction: str = "mean"
) -> float:
    """
    Calculate the mean squared error loss.

    Args:
        predictions: Model predictions array
        targets: Ground truth values
        reduction: How to reduce the loss ('mean', 'sum', 'none')

    Returns:
        Computed loss value

    Example:
        >>> preds = np.array([1.0, 2.0, 3.0])
        >>> actual = np.array([1.1, 2.0, 2.9])
        >>> calculate_loss(preds, actual)
        0.0066...
    """
    squared_diff = (predictions - targets) ** 2

    if reduction == "mean":
        return float(np.mean(squared_diff))
    elif reduction == "sum":
        return float(np.sum(squared_diff))
    return squared_diff
```

### Notebook Standards

- Start with a markdown cell explaining the notebook's purpose
- Include table of contents for long notebooks
- Clear outputs before committing (or use nbstripout)
- Add section headers with markdown cells
- Include visualizations where helpful

## Git Workflow

### Branch Naming

- Feature branches: `feature/<description>`
- Bug fixes: `fix/<description>`
- Documentation: `docs/<description>`
- Experiments: `experiment/<description>`

### Commit Messages

Follow conventional commits format:
- `feat:` New feature or content
- `fix:` Bug fix
- `docs:` Documentation changes
- `refactor:` Code refactoring
- `test:` Adding or updating tests
- `chore:` Maintenance tasks

Example: `feat: add gradient descent implementation with visualization`

### Pull Request Guidelines

- Provide clear description of changes
- Include examples or screenshots for visual changes
- Ensure all tests pass
- Update documentation if needed

## Common Topics Covered

This repository may include content on:

- **Machine Learning Basics**: Regression, classification, clustering
- **Neural Networks**: Perceptrons, MLPs, activation functions
- **Deep Learning**: CNNs, RNNs, Transformers, attention mechanisms
- **Optimization**: Gradient descent variants, learning rate scheduling
- **Evaluation**: Metrics, cross-validation, hyperparameter tuning
- **Natural Language Processing**: Tokenization, embeddings, language models
- **Computer Vision**: Image processing, object detection
- **Reinforcement Learning**: MDPs, Q-learning, policy gradients

## Troubleshooting

### Common Issues

1. **Import Errors**: Ensure virtual environment is activated and dependencies installed
2. **CUDA Issues**: Check PyTorch/TensorFlow GPU compatibility
3. **Memory Errors**: Reduce batch size or use data generators
4. **Version Conflicts**: Use exact versions in requirements.txt

### Getting Help

- Check existing documentation in `docs/`
- Review similar implementations in `src/examples/`
- Consult inline comments and docstrings

## Contributing

When contributing to this repository:

1. Follow the established code style and conventions
2. Add tests for new functionality
3. Update documentation as needed
4. Keep changes focused and atomic
5. Ensure backward compatibility when modifying existing code

---

*This CLAUDE.md file was created to provide context for AI assistants working with this codebase. Update as the project evolves.*
