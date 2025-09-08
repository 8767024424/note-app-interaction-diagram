# Single-Page App Interaction Diagram

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Opens https://studies.cs.helsinki.fi/exampleapp/spa
    Browser->>Server: GET /spa (loads SPA shell)
    Server-->>Browser: Sends index.html + JS + CSS
    Browser-->>User: Displays empty SPA UI

    Note over Browser: SPA now handles all interactions without full page reloads

    User->>Browser: Types a new note in text field
    User->>Browser: Clicks Save button
    Browser->>Server: POST /api/notes (AJAX request with note data)
    Server-->>Browser: 200 OK (note saved)
    Browser-->>User: Dynamically updates notes list
