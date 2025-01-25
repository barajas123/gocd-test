#!/bin/bash

set -e  # Exit script on error

echo "[INFO] Installing dependencies..."
pip install -r requirements.txt

echo "[INFO] Checking code formatting with black..."
black --check .

if [ $? -eq 0 ]; then
    echo "[SUCCESS] Formatting check passed!"
else
    echo "[ERROR] Formatting issues detected."
    exit 1
fi

echo "[INFO] Running unit tests..."
pytest --tb=short

if [ $? -eq 0 ]; then
    echo "[SUCCESS] All tests passed!"
else
    echo "[ERROR] Tests failed."
    exit 1
fi

echo "[INFO] CI pipeline completed successfully!"
