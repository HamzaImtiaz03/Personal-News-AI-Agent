# NewsNinja - Stealthy News Aggregator

**NewsNinja** is a sophisticated, AI-driven news aggregation platform designed to deliver curated headlines and real-time social media insights with seamless audio briefings. Harnessing cutting-edge web scraping and text-to-speech technologies, NewsNinja provides a streamlined, distraction-free news experience for professionals and enthusiasts alike.

> *No scroll, just soul.*

---

## Features

- 🗞️ **Advanced News Scraping**: Effortlessly extracts headlines from premium news websites, bypassing paywalls for comprehensive coverage.
- 🕵️‍♂️ **Real-Time Social Insights**: Captures live reactions from Reddit, including content from JavaScript-heavy threads, for authentic sentiment analysis.
- 🔊 **AI-Powered Audio Summaries**: Converts news summaries into natural, high-quality audio briefings using ElevenLabs' text-to-speech technology.
- ⚡ **Real-Time Updates**: Leverages Bright Data's Managed Cloud Proxy (MCP) for fast, reliable, and uninterrupted data retrieval.

---

## Prerequisites

To run NewsNinja, ensure you have the following:

- **Python 3.13**: Ensure Python 3.13 is installed.
- **UV**: Used for managing virtual environments and dependencies.
- **Bright Data Account**: Required for web scraping capabilities ([Sign up](https://brightdata.com)).
- **ElevenLabs Account**: Required for text-to-speech functionality ([Sign up](https://elevenlabs.io)).
- **Anthropic API Key**: Required for AI-driven content processing.

---

## Installation

Follow these steps to set up NewsNinja on your local machine:

1. **Clone the Repository**
   ```bash
   git clone https://github.com/AIwithhassan/newsninja.git
   cd newsninja
   ```

2. **Set Up Virtual Environment with UV**
   ```bash
   uv venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   uv pip install -r requirements.txt
   ```

   The project relies on the following dependencies:
   - `streamlit`: For the interactive web interface.
   - `langchain-anthropic`: For AI-powered content processing.
   - `fastapi`: For robust API development.
   - `python-dotenv`: For environment variable management.
   - `beautifulsoup4`: For HTML parsing.
   - `lxml`: For efficient XML/HTML processing.
   - `ollama`: For local AI model integration.
   - `elevenlabs`: For high-quality text-to-speech.
   - `aiolimiter`: For rate-limiting API requests.
   - `langgraph`: For building complex AI workflows.
   - `mcp`: For Bright Data's Managed Cloud Proxy integration.
   - `langchain-mcp-adapters`: For seamless MCP integration with LangChain.
   - `gtts`: For fallback text-to-speech functionality.

4. **Configure Environment Variables**
   
   Create `.env` to include your API keys and credentials:
   ```env
   # Bright Data
   BRIGHTDATA_MCP_KEY="your_mcp_api_key"
   BROWSER_AUTH="your_browser_auth_token"

   # ElevenLabs
   ELEVENLABS_API_KEY="your_text_to_speech_key"

   # Anthropic
   ANTHROPIC_API_KEY="your_anthropic_api_key"
   ```

5. **Set Up Bright Data**
   - Log in to your Bright Data account: [Bright Data Dashboard](https://brightdata.com/cp/zones).
   - Create an MCP zone and enable browser authentication.
   - Copy the generated credentials to your `.env` file.

---

## Running NewsNinja

1. **Start the Backend**
   In a terminal, activate the virtual environment and run:
   ```bash
   source .venv/bin/activate
   uv run python backend.py
   ```

2. **Start the Frontend**
   In a second terminal, activate the virtual environment and run:
   ```bash
   source .venv/bin/activate
   uv run streamlit run frontend.py
   ```

3. **Access the Application**
   Open your browser and navigate to `http://localhost:8501` to interact with the Streamlit interface.

---

## Project Structure

```
newsninja/
├── frontend.py          # Streamlit-based user interface
├── backend.py          # FastAPI backend and data processing logic
├── utils.py            # Utility functions for reusable logic
├── news_scraper.py     # Web scraper for news websites
├── reddit_scraper.py   # Web scraper for Reddit reactions
├── models.py           # Pydantic models for data validation
├── requirements.txt     # Project dependencies
├── .env.example        # Template for environment variables
└── README.md           # Project documentation
```

---

## Usage Notes

- **Initial Scrape Delay**: The first scrape may take 15-20 seconds due to browser emulation and proxy initialization.
- **Reddit Scraping**: Utilizes Bright Data's MCP for real browser emulation to handle JavaScript-heavy threads.
- **Security**: Keep your `.env` file secure and never commit it to version control.
- **Rate Limiting**: Configured via `aiolimiter` to ensure compliance with API usage limits.

---

## Troubleshooting

- **API Key Issues**: Verify that your Bright Data, ElevenLabs, and Anthropic API keys are correctly configured in the `.env` file.
- **Dependency Errors**: Ensure all dependencies are installed using `uv pip install -r requirements.txt`.
- **Connection Issues**: Check your Bright Data MCP zone settings and network connectivity.

For additional support:
- Open an issue on GitHub: [NewsNinja Issues](https://github.com/AIwithhassan/newsninja/issues)
- Contact Bright Data support: [Bright Data Support](https://brightdata.com/support)
- Contact ElevenLabs support: [ElevenLabs Support](https://elevenlabs.io/support)

---

## Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

*"In the darkness of information overload, be the ninja."* 🌑