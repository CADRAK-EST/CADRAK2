# CADRAK2

## Overview
The primary goal of this project is to create a web-based DXF file viewer that can parse and display DXF files. Initially, the project will focus on the ability to open local DXF files, parse them using a Python-based parser, and visualize them on a web page using Node.js. Future iterations will include functionality to detect and highlight mistakes such as missing dimension lines and missing information from the information box.

## Features

### Must-Have
- **Local DXF File Upload**: Users must be able to upload local DXF files to the web application.
- **DXF File Parsing**: The system must parse the DXF files using a Python-based parser.
- **DXF File Visualization**: The system must visualize the parsed DXF files on a web page using Node.js.

### Should-Have
- **Basic UI for File Management**: A user-friendly interface for uploading and viewing files.

### Will-Have (Future Iterations)
- **Error Highlighting**: Highlight areas where mistakes might be detected.

### Won't-Have (Yet)
- **Database Integration**: Initially, the application will not include database functionality.
- **Mistake Detection**: The mistake detection module will be implemented in future iterations.

## Architecture Overview

### Webpage Backend (Node.js)
- **Handles the user interface and interactions**
- **Manages file uploads and communicates with the DXF parser**

### DXF Parser (Python)
- **Parses the uploaded DXF files**
- **Sends parsed data back to Node.js for visualization**

### Webpage UI
- **File Upload Component**
- **Uploaded Files List**
- **DXF Content Visualizer**: Renders DXF content on the screen
