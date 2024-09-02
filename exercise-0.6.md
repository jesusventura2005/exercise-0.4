# exercise-0.6
SequenceDiagram

    participant browser
    participant server
    participant person 

    Note : The page was already loaded previously, so previous requests are not represented(exercise0.5).

    person-->> enter the data
    person-->> click "save"

    browser->>server: POST
    https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server 
    server-->>browser: {content: "ass", date: "2024-09-02T21:05:39.145Z"}
    desactive server 

   
