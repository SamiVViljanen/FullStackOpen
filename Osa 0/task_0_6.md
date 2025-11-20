```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Note over Browser: Käyttäjä kirjoittaa muistiinpanon ja painaa 'Tallenna'

    Note right of Browser: JavaScript käsittelee lomakkeen eikä lataa sivua uudelleen

    Browser ->> Server: POST /new_note_spa <br> (note content in JSON)
    activate Server
    Server -->> Browser: JSON response (uusi muistiinpano tallennettu)
    deactivate Server

    Note over Browser: Selain päivittää muistiinpanolistan suoraan JavaScriptillä ilman sivun uudelleenlataamista
