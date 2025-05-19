# docs
The style-genie docs.


# Style-Genie 
Style Genie is a fashion recommendation system. It uses a combination of machine learning and natural language processing to generate personalized fashion recommendations based on user input.

## Style-Genie File Structure

- repo  https://github.com/style-genie/
- overview https://github.com/style-genie/style-genie
```
├── backend/
│   ├── postgres/               # PostgreSQL database configuration
│   ├── server/                 # Backend server application
│   │   ├── src/                # Source code
│   │   │   ├── agent/          # Agent logic and workflows
│   │   │   ├── __init__.py
│   │   │   ├── session.py      # Session management
│   │   │   ├── tools.py        # Agent tools
│   │   │   ├── workflows/      # Agent workflows
│   │   ├── main.py             # Main application entry point
│   │   ├── pyproject.toml      # Project configuration (Poetry)
│   │   ├── README.md
│   │   ├── Dockerfile          # Docker configuration
│   │   └── .env.sample         # Example environment variables
├── data/                       # Data storage
│   ├── data.json               # Main data file
│   ├── raw_data/               # Raw data files
├── frontend/
│   ├── stylectai/              # Stylectai frontend application
│   │   ├── components/         # React components
│   │   │   ├── image-uploader.tsx
│   │   │   ├── user-form.tsx
│   │   │   ├── UserModal.tsx
│   │   │   ├── icons/          # Icons
│   │   │   ├── ui/             # UI components
│   │   ├── lib/                # Utility functions
│   │   ├── pages/              # Next.js pages
│   │   │   ├── api/            # API routes
│   │   │   ├── _app.tsx        # Custom App component
│   │   │   ├── _document.tsx   # Custom Document component
│   │   │   ├── index.tsx       # Home page
│   │   │   ├── landing.tsx     # Landing page
│   │   │   ├── session_test.tsx # Session test page
│   │   ├── public/             # Public assets
│   │   ├── resources/          # Resources (images, data)
│   │   ├── styles/             # Styles (CSS)
│   │   ├── types/              # TypeScript types
│   │   ├── components.json
│   │   ├── README.md
├── media/                      # Media files
├── tools/                      # Utility scripts
│   ├── pinecone/               # Pinecone related scripts
│   ├── scraper/                # Scraper scripts
├── .gitignore
├── docker-compose.yml          # Docker Compose configuration
├── LICENSE
└── README.md
```
### Main Components:

1.  Backend (backend/server):
    *   AI Agent: Manages user sessions and workflows using AI models.
    *   API Endpoints: Handles requests from the frontend.
    *   Database Interaction: Interacts with the PostgreSQL database.

2.  Frontend (frontend/stylectai):
    *   React Components: Provides UI elements for user interaction.
    *   Next.js Pages: Defines application routes and page structure.
    *   Image Uploader: Handles image uploads.
    *   User Form: Collects user input.

3.  Frontend (frontend/streamlit):
    *   Streamlit App: Alternative frontend for data visualization and interaction.

4.  Database (backend/postgres):
    *   PostgreSQL: Stores user data, session information, and other application data.

5.  Tools (tools/):
    *   Scraper: Used for scraping data from external sources.
    *   Pinecone: Used for interacting with the Pinecone vector database.


# Agent505
- repo  https://github.com/style-genie/
- overview https://github.com/style-genie/style-genie

Agent505 is a platform for building and managing AI agents that can interact with users through websockets. It uses FastAPI, Pydantic, Uvicorn, and other libraries to provide a flexible and scalable environment for developing and deploying AI-powered applications.

## Agent505 File Structure

```
Agent505/
├── .env.sample
├── main.py
├── pyproject.toml
├── requirements.txt
├── setup.py
├── src/
│   ├── __init__.py
│   ├── server.py
│   └── session.py
└── stylegenie.egg-info/
    ├── dependency_links.txt
    ├── PKG-INFO
    ├── requires.txt
    ├── SOURCES.txt
    └── top_level.txt
```