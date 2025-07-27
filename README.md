# 📈 DataSage AI

An interactive web application for data analysis and visualization of CSV files, powered by Large Language Models (LLMs). Upload a dataset, submit a natural language query, and receive AI-generated insights and plots.

---

## ✨ Features

-   **Web Interface**: A browser-based UI built with Streamlit for interactive use.
-   **CSV Data Ingestion**: Supports direct upload and preview of `.csv` files.
-   **Natural Language Querying**: Utilizes LLMs to interpret user prompts and generate relevant analysis.
-   **Secure Code Execution**: Executes AI-generated code in a remote, sandboxed E2B environment.
-   **Multiple Output Formats**: Renders results as text, `pandas` DataFrames, and visualizations.

---

## 🛠️ Tech Stack

-   **Language**: Python
-   **Frontend**: Streamlit
-   **LLM Service**: Together AI
-   **Secure Sandbox**: E2B Code Interpreter
-   **Data Manipulation**: pandas
-   **Image Processing**: Pillow

---

## ⚙️ Architecture

The application's workflow is executed as follows:

1.  A user uploads a CSV file and submits a prompt through the **Streamlit** front end.
2.  The prompt and dataset path are sent to a selected **LLM** via the **Together AI** API.
3.  The LLM returns a Python script designed to perform the requested analysis.
4.  The script is executed within a secure **E2B Code Interpreter** sandbox.
5.  The execution artifacts (e.g., stdout, plots, DataFrames) are captured and rendered in the Streamlit UI.

---

## 🚀 Setup

### ### Prerequisites

-   Python 3.8+
-   🔑 An active API key from [Together AI](https://api.together.ai/signin)
-   🔑 An active API key from [E2B](https://e2b.dev/docs/legacy/getting-started/api-key)

### ### Installation

1.  Clone the repository and navigate into the project directory.

2.  Create a `requirements.txt` file with the following content:
    ```txt
    streamlit
    pandas
    together
    e2b-code-interpreter
    Pillow
    ```

3.  Install the dependencies using pip:
    ```bash
    pip install -r requirements.txt
    ```

---

## ▶️ Usage

1.  Run the Streamlit application from your terminal:
    ```bash
    streamlit run app.py
    ```

2.  Navigate to the local URL provided by Streamlit.

3.  In the web UI's sidebar, enter your Together AI and E2B API keys.

4.  Select your preferred LLM from the dropdown menu.

5.  Upload a CSV file and enter a query into the text area to begin analysis.

### ### Example Prompts

**Basic Queries:**
-   `Show the first 10 rows of the dataset.`
-   `Provide summary statistics for all numerical columns.`
-   `Plot a histogram of the 'age' column.`
-   `Create a scatter plot of 'column_A' vs 'column_B'.`

**Generating Multiple Plots:**
To generate multiple plots in a single output, structure your prompt to request all visualizations at once.

-   **Example 1 (Descriptive):** `Create a figure with two subplots. On the top, show a histogram of the 'age' column. On the bottom, show a box plot for the 'salary' column.`
-   **Example 2 (Grid Layout):** `Generate a 4x1 grid of plots showing the distribution for the four most relevant numerical columns.`