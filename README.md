# RAG-Gmail-Assistant

## Description
RAG-Gmail-Assistant is a Retrieval-Augmented Generation (RAG) system that leverages the Gmail API to fetch email data and uses OpenAI's GPT models to generate responses. This project is useful for generating context-aware email responses based on previous emails and improving interaction efficiency. The system uses Faiss for similarity search to improve email retrieval performance.

## Project Structure
- **`RAG_Gmail.ipynb`**: The main notebook that contains the project's code.
- **`.env`**: Stores your OpenAI API key.
- **`credentials.json`**: Stores your Gmail API credentials.
- **`requirements.txt`**: Lists the required Python packages.

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/RAG-Gmail-Assistant.git
cd RAG-Gmail-Assistant
```
### 2. Install Dependencies
Make sure you have Python 3.x installed. To install the required libraries, run the following command:
```bash
pip install -r requirements.txt
```

### 3. Set Up Environment Variables
Create a .env file in the root directory and add your OpenAI API key:
**`
OPENAI_API_KEY=your_openai_api_key_here
`**

### 4. Obtain Gmail API Credentials
You will need to create a Google Cloud project and obtain a credentials.json file to access the Gmail API. Follow these steps:

#### Go to the Google Cloud Console.
1. Create a new project.
2. Navigate to APIs & Services > Credentials.
3. Click Create Credentials and select OAuth 2.0 Client IDs.
4. Download the credentials.json file and place it in the root directory of the project.

#### Next, you must add yourself as a tester to use the app:
1. In the Google Cloud Console, go to OAuth consent screen.
2. If your app is still in "testing" mode, under Test users, add the email addresses of users (including your own) that you want to allow access to the app.
3. Save the settings.
This ensures that the added emails can use the app for testing purposes without needing full app verification.

### 5. Run the Notebook
Launch Jupyter Notebook or Jupyter Lab and run the RAG_Gmail.ipynb notebook:
```bash
jupyter notebook RAG_Gmail.ipynb
```
Follow the prompts to authenticate your Gmail API and interact with your emails using the OpenAI API.

### 6. User-Specific Files
The following files are generated dynamically when the program runs. These files are related to user-specific data and should not be included in the GitHub repository:

- **`token.json`**: Stores OAuth tokens for Gmail API authentication. This file is generated when you first authenticate with the Gmail API and is needed for subsequent API access without re-authentication.
- **`index_email_metadata.db`**: A database file storing metadata related to retrieved emails for fast access.
- **`index_email.index`**: Stores the Faiss index for email retrieval using similarity search.
- **`last_checked.txt`**: Records the timestamp of the last email retrieval, which helps in incremental fetching of new emails.
These files are essential for the program to function correctly but will be generated when the application is executed for the first time.

### 7. License
This project is licensed under the GNU General Public License v3.0. See the LICENSE file for more details.

