# FRONTEND_README.md

This document describes the frontend components of the Agent505 project and how to use feedback loops with them.


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

# Session_test.tsx
This file serves as a example dashboard for the backend communication and recommendation system.

## ChatInterface Component

The `ChatInterface` component provides the following features:

- **Chat Window:** Displays the conversation between the user and the AI agent. This window displays messages exchanged between the user and the agent, with timestamps for each message.

- **User Info & Tools:** Allows the user to provide information about themselves and access various tools. This section includes tabs for preferences, user data, search results, search context, virtual try-on, and plan.

- **Preferences Tab:** Allows the user to set preferences for the AI agent's behavior. This tab includes the following filters:
    - **Outfits Filter:** Enables or disables the display of outfits.
    - **Shoes Filter:** Enables or disables the display of shoes.
    - **Trousers Filter:** Enables or disables the display of trousers.
    - **Shirts Filter:** Enables or disables the display of shirts.
    - **Jackets Filter:** Enables or disables the display of jackets.
    - **Bags Filter:** Enables or disables the display of bags.
    - **Accessories Filter:** Enables or disables the display of accessories.
    - **Hats Filter:** Enables or disables the display of hats.
    - **Skirts Filter:** Enables or disables the display of skirts.
    - **User Info Filter:** Enables or disables the display of user info.
    - **User Images Filter:** Enables or disables the display of user images.
    - **User Style Filter:** Enables or disables the display of user style.
    - **User Prompt Filter:** Enables or disables the display of user prompts.
    - **User Modifiers Filter:** Enables or disables the display of user modifiers.
    - **User Input Prompt:** Allows the user to enter a prompt for the AI agent.
    - **User Modifiers:** Allows the user to modify various aspects of the AI agent's behavior, such as sexy, casual, formal, sporty, trendy, party, vintage, elegant, minimal, bohemian, romantic, and chic.

- **User Data Tab:** Allows the user to provide data about themselves, such as images, style preferences, and personal information. This tab includes the following fields:
    - **Image Links:** Allows the user to add or remove image links.
    - **About Me:** Allows the user to enter information about themselves.
    - **My Style:** Allows the user to enter information about their style preferences.

- **Search Results Tab:** Displays search results from the AI agent.

- **Search Context Tab:** Displays the context used by the AI agent for search.

- **Virtual Try-On Tab:** Provides a virtual try-on experience.

- **Plan Tab:** Displays the plan generated by the AI agent.

## Feedback Loops

Feedback loops are an important part of the Agent505 project. They allow the AI agent to learn from user interactions and improve its performance over time.

The `ChatInterface` component provides several ways for users to provide feedback to the AI agent:

- **Chat Window:** Users can provide feedback by simply chatting with the AI agent. The agent can learn from the user's messages and adapt its responses accordingly.
- **Preferences Tab:** Users can set preferences for the AI agent's behavior, such as the level of detail in its responses. The agent can use these preferences to tailor its responses to the user's needs.
- **User Data Tab:** Users can provide data about themselves, such as images, style preferences, and personal information. The agent can use this data to personalize its responses and provide more relevant recommendations.


## Communication with the Backend

The `ChatInterface` component communicates with the Agent505 backend using websockets. The following functions are responsible for communicating with the backend:

- **useEffect hook:** This hook sets up the websocket connection when the component mounts. It also handles incoming messages from the backend. When a message is received, it updates the `messages` state variable, which causes the chat window to re-render.
- **handleSubmit function:** This function is called when the user submits a message in the chat window. It sends the user's input to the Agent505 backend via the websocket connection.

The Agent505 backend processes the user's input and returns a response. The response is then displayed in the chat window.

## How to use with feedback loops

The `ChatInterface` component is designed to be used with feedback loops. The component sends user input to the Agent505 backend, which processes the input and returns a response. The component then displays the response to the user.

The Agent505 backend can use the user's input and the agent's response to learn and improve its performance over time. For example, the backend can use the user's input to train a machine learning model to generate more relevant responses.

The `ChatInterface` component also provides a way for users to provide explicit feedback to the agent. Users can rate the agent's responses or provide comments on the agent's performance. This explicit feedback can be used to further improve the agent's performance.
