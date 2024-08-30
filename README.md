# exercise-0.4
SequenceDiagram

    participant browser
    participant server
    participant person 

    Note : The page was already loaded previously, so previous requests are not represented.

    person-->> enter the data
    person-->> click "save"

    browser->>server: POST
    https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server 
    server-->>browser: GET
    /exampleapp/notes
    desactive server 

    browser->>server: GET 
    https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server
    
    browser->>server: GET 
    https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET 
    https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    browser->>server: GET 
    https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server
