# tabletop-keeper
Organise and keep track of your TTRPG campaigns, character sheets, party loot, and more

# Software Requirements Specification
This README serves as the SRS for the project. It includes the functional and non-functional requirements, system architecture, database designed, and technology stack.

## 1. Functional Requirements
- User Management: Users should be able to create accounts, log in, and manage profiles.
- Character Management: Allow users to create, update, and delete characters, customize stats, skills, abilities, and track level progression.
- Inventory Management: Users can manage character inventories, add/remove items, and track equipment.
- Campaign Notes: Game Masters (GMs) should be able to create campaigns and store detailed session notes, NPCs, locations, quests, etc.
- Dice Roller: Include a built-in dice roller with customizable settings for different games (D&D, Starfinder, etc.).
- Multiplayer Support: Players and GMs should be able to share campaigns and characters with each other and collaborate.
- Rulebook Integration: Integrate or link to rule sets for different games.
- Offline Access: Allow users to access their data even when offline, with data syncing when they reconnect.

## 2. Non-functional Requirements
- Performance: Ensure quick response times for accessing and updating character sheets, inventory, and campaign notes.
- Scalability: The app should handle multiple campaigns, users, and shared assets efficiently.
- Security: Implement authentication, authorization, and encryption to protect user data.
- Usability: The interface should be user-friendly, especially for non-technical users.
- Cross-Platform: Ensure the app works across different platforms (web, mobile, desktop).
- Data Syncing: Handle data synchronization when users switch between online and offline modes.

## 3. System Architecture
The architecture can be divided into the following layers:

  Presentation Layer (Frontend):
        This will consist of the user interface for character creation, inventory management, campaign notes, etc.
        Frameworks/Tools: React Native (for cross-platform mobile and web apps), Flutter, or Angular with Ionic for hybrid apps.

  Business Logic Layer (Backend):
        The backend handles user requests, processes game logic (e.g., level progression), manages data validation, and provides data to the frontend.
        Frameworks/Tools: Node.js with Express, Django (Python), or ASP.NET for server-side logic.

  Data Layer (Database and Storage):
        Store user accounts, characters, inventory, campaign notes, etc. Ensure it's optimized for fast retrieval.
        Technology: A relational database like PostgreSQL or MySQL can handle structured data, while a NoSQL option like MongoDB might be suitable for more flexible game-related data.

  APIs:
        Use RESTful or GraphQL APIs for communication between the frontend and backend.
        Third-party integration for rulebook API (if available), authentication, or even dice rolling services.

  Cloud Storage:
        For storing larger assets like images or PDFs (campaign maps, character sheets, etc.), use cloud storage services.
        Technology: AWS S3, Google Cloud Storage, or Firebase.

## 4. Database Design
  Users Table:
    - ID (PK)
    - Username
    - Email
    - Password Hash
    - Role (Player/GM)
  Characters Table:
    - ID (PK)
    - UserID (FK)
    - Name
    - Class (FK)
    - Race (FK)
    - Level
