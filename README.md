# Plivo Chatbot


## Requirements

- Python 3.10
- ngrok (for tunneling)
- Plivo Account

## Installation

1. **Set up a virtual environment** (optional but recommended):

   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

2. **Install dependencies**:

   ```sh
   pip install -r requirements.txt
   ```

3. **update env**:

   ```sh
   OPENAI_API_KEY=
   DEEPGRAM_API_KEY=
   PINECONE_API_KEY=
   ```
   

4. **Install ngrok**:
   Follow the instructions on the [ngrok website](https://ngrok.com/download) to download and install ngrok.

## Configure Plivo URLs

1. **Start ngrok**:
   In a new terminal, start ngrok to tunnel the local server:

   ```sh
   ngrok http 8765
   ```

2. **Update the Plivo Application**:

   - Go to your Plivo phone number's application configuration page
   - Under "Voice Configuration" section:
     - Enter your ngrok URL (e.g., http://<ngrok_url>) as the 'Answer URL'
     - Ensure "HTTP POST" is selected
   - Click Save at the bottom of the page


## Running the Application

Choose one of these two methods to run the application:

### Using Python (Option 1)

**Run the FastAPI application**:

```sh
# Make sure you’re in the project directory and your virtual environment is activated
python server.py
```

The server will start on port 8765. Keep this running while you test with Plivo.

## Usage

To start a call, simply make a call to your configured Plivo phone number. The webhook URL will direct the call to your FastAPI application, which will handle it accordingly.
