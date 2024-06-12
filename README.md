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
- **`POST /upload`**: Uploads a DXF file.
  - **Request**:
    ```json
    {
      "file": "path/to/file.dxf"
    }
    ```
  - **Response**:
    ```json
    {
      "message": "File uploaded successfully",
      "file_path": "uploads/file.dxf"
    }
    ```

- **`POST /parse`**: Parses a DXF file.
  - **Request**:
    ```json
    {
      "file_path": "uploads/file.dxf"
    }
    ```
  - **Response**:
    ```json
    {
      "message": "File parsed successfully",
      "parsed_data": { ... }
    }
    ```

#### Messenger
- **`POST /api/upload`**: Receives and forwards file upload requests.
- **`POST /api/parse`**: Forwards file parsing requests to the CADRAK Engine.