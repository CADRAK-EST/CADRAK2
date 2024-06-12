# CADRAK Project Documentation

## Component Descriptions
- **CADRAKWeb**: User interface for uploading and viewing DXF files using Three.js for visualization.
- **CADRAKMessenger**: Acts as an intermediary between the webpage, and the engine.
- **CADRAKEngine**: Parses DXF files and returns structured data.
- **CADRAKDatabase**: (Planned) Stores user data, uploaded DXFs and parsed DXF data.

## Prerequisites
- Node.js
- npm
- Python 3.11
- pip

## Interaction
### User Authentication:
1. **Step 1**: User sends authentication request to the Messenger.
2. **Step 2**: Messenger interacts with the Database to verify user credentials.
3. **Step 3**: Messenger responds to the user with success or failure.

### File Upload:
1. **Step 1**: User uploads a DXF file via the Webpage Frontend.
2. **Step 2**: Webpage Backend sends the file to the Messenger.
3. **Step 3**: Messenger saves the file to the Database and stores metadata (e.g., file name, upload time).
4. **Step 4**: Messenger responds to the Webpage Backend with confirmation and metadata.

### File Selection and Parsing:

#### Option 1: Direct Engine Access
1. **Step 1**: User selects a file from the Webpage Frontend.
2. **Step 2**: Webpage Backend sends the selected file's metadata to the Messenger.
3. **Step 3**: Messenger notifies the Engine about the file to parse, providing the database file identifier.
4. **Step 4**: Engine retrieves the file directly from the Database, parses it, and sends the parsed data back to the Messenger.
5. **Step 5**: Messenger forwards the parsed data to the Webpage Backend, which updates the Frontend.

#### Option 2: Messenger as an Intermediary
1. **Step 1**: User selects a file from the Webpage Frontend.
2. **Step 2**: Webpage Backend sends the selected file's metadata to the Messenger.
3. **Step 3**: Messenger retrieves the file from the Database and sends it to the Engine for parsing.
4. **Step 4**: Engine parses the file and sends the parsed data back to the Messenger.
5. **Step 5**: Messenger forwards the parsed data to the Webpage Backend, which updates the Frontend.


## API Endpoints
### CADRAKWeb
- **`POST /upload`**: Uploads a DXF file. Inputs a DXF file. Outputs a filepath in the messenger.

- **`POST /parse`**: Parses a DXF file. Inputs a filepath in the messenger. Outputs parsed .json data.

### CADRAKMessenger
- **`POST /upload`**: Receives file upload requests. Inputs a DXF file. Outputs a filepath.
- **`POST /parse`**: Forwards file parsing requests to the CADRAK Engine. Inputs a filepath. Outputs parsed .json data.

### CADRAKEngine
- **`POST /parse`**: Parses a DXF file. Inputs a DXF files. Outputs parsed .json data.