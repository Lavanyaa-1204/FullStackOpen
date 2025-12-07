sequenceDiagram
    participant browser
    participant server
    Note right of browser: User clicks Save button
    Note right of browser: The browser executes the event handler, creates a new notes object and adds it to the existing notes.<br/> Finally it renders it on the browser without reloading it.
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    Note left of server: Note saved to database
    server-->>browser: Http 201 created
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes