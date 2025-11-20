```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Note over Browser: Käyttäjä kirjoittaa muistiinpanon ja painaa 'Tallenna' 

    Browser ->> Server: POST /new_note <br> (note content)
    activate Server
    Server -->> Browser: HTTP 302 Redirect to /notes
    deactivate Server

    Note over Browser: Selain seuraa uudelleenohjausta ja lataa sivun uudelleen

    Browser ->> Server: GET /notes
    Server -->> Browser: HTML document

    Browser ->> Server: GET /main.css
    Server -->> Browser: CSS file

    Browser ->> Server: GET /main.js
    Server -->> Browser: JavaScript file

    Note right of Browser: JavaScript hakee palvelimelta päivitetyn muistiinpanodatan

    Browser ->> Server: GET /data.json
    Server -->> Browser: Updated notes JSON

    Note over Browser: Selain näyttää päivitetyn muistiinpanolistan
