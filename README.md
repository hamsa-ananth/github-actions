name: Simple CI Pipeline

# Trigger the workflow on push or pull request to the main branch
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build-and-test:
    # Use the latest Ubuntu virtual machine
    runs-on: ubuntu-latest

    steps:
      # Step 1: Download your code into the runner
      - name: Checkout Code
        uses: actions/checkout@v4

      # Step 2: Run a single command
      - name: Say Hello
        run: echo "Starting the pipeline..."

      # Step 3: Run multiple commands
      - name: Run Tests
        run: |
          echo "Running unit tests..."
          echo "All tests passed!"
