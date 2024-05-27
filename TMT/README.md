# TMT

## Installation

1. **Set up a virtual environment:**

    ```bash
    # On Unix/Linux/MacOS
    python3 -m venv TMT

    # On Windows
    python -m venv TMT
    ```

2. **Activate the virtual environment:**

    ```bash
    # On Unix/Linux/MacOS
    source TMT/bin/activate

    # On Windows
    .\TMT\Scripts\activate
    ```

3. **Install dependencies:**

    Once the virtual environment is activated, you can install the required dependencies using pip.

    ```bash
    cd code
    pip install -r requirements.txt



## Usage
To test TMT
```bash
python test_TMT_dynamic.py --model_path ${your_model_path} --data_path ${your_validation_data_path} --result_path ${path_to_save_results}
