# WE'RE MOVING! USE THIS REPO INSTEAD: https://github.com/Xelvanta/Anndromeda-RoyaleAPI

# Royale High API

This is a Quart API to fetch Royale High item names and their community values from Traderie.

## Setup Instructions

### Prerequisites

1. **Python 3.x**: Make sure you have Python 3.x installed. You can download it from [python.org](https://www.python.org/).
2. **pip**: Ensure you have pip (Python package installer) installed. It usually comes with Python.

### Installation

1. **Clone the Repository**:

    ```bash
    git clone https://github.com/ProjectAnndromeda/royalehigh-api.git
    cd royalehigh-api
    ```

2. **Create a Virtual Environment** (optional but recommended):

    ```bash
    python -m venv venv
    ```

3. **Activate the Virtual Environment**:

    - **Windows Command Prompt**:

        ```bash
        venv\Scripts\activate
        ```

    - **Windows PowerShell**:

        ```powershell
        .\venv\Scripts\Activate.ps1
        ```

    - **macOS/Linux**:

        ```bash
        source venv/bin/activate
        ```

4. **Install Dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

5. **Install Playwright Browsers**:

    After installing the dependencies, you need to install the necessary browser binaries for Playwright:

    ```bash
    playwright install
    ```

### Running the API

1. **Run the Quart Application**:

    ```bash
    quart run
    ```

2. **Access the API**:

    Open Google Chrome or an API client (like Insomnia) and navigate to:

    ```
    http://127.0.0.1:5000/items
    ```

### Example Response

```json
[
    {
        "name": "14 Karat Gold Infinity Chain",
        "value": 14000
    },
    {
        "name": "2019 Party Hat",
        "value": 10000
    },
    {
        "name": "2020 Lunar Rat Ears",
        "value": 4000
    },
    ...
]
```

## Key Considerations

### **API Response Time**

The API may take some time to return data due to the process of scraping multiple pages. The script handles pagination and will stop once no more items are detected.

- **Consideration:** If you encounter timeouts in your API client, consider increasing the timeout settings for your requests. This adjustment will allow the application to handle longer processing times and improve overall stability during data retrieval.

### **Value Retrieval**

The script captures item names and values from Traderie. It checks for the presence of a "no-items" message to determine if there are no more items to fetch. 

- **Consideration:** Ensure that the page structure on Traderie has not changed, as the script relies on specific class names to find and extract data. If there are updates to the page structure, you might need to adjust the class names in the script.

### **Dependencies and Environment**

- **Dependencies:** Ensure that all required packages listed in `requirements.txt` are installed. Use a virtual environment to manage these dependencies and avoid conflicts with other Python projects.

- **Playwright Management:** The script uses Playwright for browser automation. After installing the required packages, make sure to install the necessary browser binaries with `playwright install`.

### **Error Handling and Logging**

The script includes basic error handling and logging configurations. It is designed to handle common issues like network errors and timeouts, and to retry fetching pages if necessary.

- **Consideration:** Adjust logging levels and error handling according to your debugging needs. More granular error handling might be required based on specific use cases or to improve robustness.

## Attribution

If you use or modify this code, please include the following attribution in any related documentation or publicly accessible materials: "Powered by Anndromeda™ by Alina."

## License

This code is provided under the terms of the [LICENSE.txt](LICENSE.txt) file included in this distribution.
