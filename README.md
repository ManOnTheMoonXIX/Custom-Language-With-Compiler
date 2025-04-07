# QuickTix: Ticket Booking Terminal Interface

QuickTix is a terminal-style interface for booking and managing tickets, built with FastAPI and a custom command language called SadeScript.

## Features

- **Command Line Interface**: Intuitive terminal-style UI for booking and managing tickets
- **Custom Language**: Use SadeScript commands to interact with the system
- **Azure Cosmos DB**: Store events, tickets, and bookings in the cloud
- **Web Interface**: Access the system through a modern web interface

## Getting Started

### Prerequisites

- Python 3.7+
- Azure Cosmos DB account
- Required Python packages: `fastapi`, `uvicorn`, `python-dotenv`, `azure-cosmos`, `ply`

### Installation

1. Clone the repository:

   ```
   git clone https://github.com/yourusername/QuickTix-SadeScript.git
   cd QuickTix-SadeScript
   ```

2. Install required packages:

   ```
   pip install fastapi uvicorn python-dotenv azure-cosmos ply google-generativeai
   ```

3. Create a `.env` file with your credentials:
   ```
   COSMOS_ENDPOINT=your_cosmos_db_endpoint
   COSMOS_KEY=your_cosmos_db_key
   COSMOS_DATABASE=your_database_name
   COSMOS_CONTAINER=your_container_name
   GEMINI_API_KEY=your_gemini_api_key
   ```

### Running the Application

1. Start the web server:

   ```
   python -m uvicorn main:app --reload
   ```

2. Navigate to http://127.0.0.1:8000 in your browser

## SadeScript Commands

QuickTix uses a custom command language called SadeScript to interact with the system. The following commands are available:

### Listing Events

```
LIST EVENTS
LIST EVENTS IN "Kingston"
```

### Booking Tickets

```
BOOK "Event Name" ON 2024-12-31 FOR "Person Name"
BOOK "Event ID" 2
```

### Managing Bookings

```
CONFIRM "QTX-1234"
PAY "QTX-1234" 100
CANCEL "QTX-1234"
```

### Event Management

```
ADD EVENT "Title" "Venue" "Location" 2024-12-31 2024-12-31 50 100 100
UPDATE EVENT "Event Name" WITH 10 NEW TICKETS
```

## Command Completion

The system includes intelligent command completion:

- Type the beginning of a command and press TAB to complete it
- The suggestion system provides context-aware completions for faster input

## API Documentation

When the server is running, API documentation is available at:

- http://127.0.0.1:8000/docs (Swagger UI)
- http://127.0.0.1:8000/redoc (ReDoc)

## Project Structure

- `main.py` - FastAPI web application
- `cli.py` - Command-line interface implementation
- `parser.py` - SadeScript parser using PLY
- `lexer.py` - SadeScript lexer for tokenizing commands
- `gemini_utils.py` - Utilities for command suggestions using Google's Gemini AI
- `gemini_completer.py` - Command completion implementation
- `static/index.html` - Web interface

## Group Members

- Justin Alder 2007273
- Daryn Brown 2002414
- Marvis Haughton 1802529
- Peta Gaye Mundle 1403906
- Cassandra Powell 2005742

## License

This project is licensed under the MIT License - see the LICENSE file for details.
