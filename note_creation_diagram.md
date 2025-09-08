# Note Creation Process Diagram

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Opens https://studies.cs.helsinki.fi/exampleapp/notes
    Browser->>Server: GET /notes (loads notes page)
    Server-->>Browser: Sends HTML page
    Browser-->>User: Displays Notes UI

    User->>Browser: Types a new note in text field
    User->>Browser: Clicks "Save" button
    Browser->>Server: POST /notes (with new note content)
    Server-->>Browser: 200 OK (note saved)
    Browser-->>User: Displays updated notes list
