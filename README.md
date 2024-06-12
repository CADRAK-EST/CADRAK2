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

## API Endpoints
### CADRAKWeb
- **`POST /upload`**: Uploads a DXF file. Inputs a DXF file. Outputs a filepath in the messenger.

- **`POST /parse`**: Parses a DXF file. Inputs a filepath in the messenger. Outputs parsed .json data.

### CADRAKMessenger
- **`POST /upload`**: Receives file upload requests. Inputs a DXF file. Outputs a filepath.
- **`POST /parse`**: Forwards file parsing requests to the CADRAK Engine. Inputs a filepath. Outputs parsed .json data.

### CADRAKEngine
- **`POST /parse`**: Parses a DXF file. Inputs a DXF files. Outputs parsed .json data.