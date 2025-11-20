```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Note over Browser: Käyttäjä siirtyy SPA-sovelluksen osoitteeseen

    Browser ->> Server: GET /spa
    Server -->> Browser: HTML document

    Browser ->> Server: GET /main.css
    Server -->> Browser: CSS file

    Browser ->> Server: GET /spa.js
    Server -->> Browser: JavaScript file

    Note right of Browser: Selain suorittaa JavaScript-koodin, joka vastaa SPA-sovelluksen toiminnasta

    Browser ->> Server: GET /data.json
    Server -->> Browser: Notes JSON data

    Note over Browser: Selain piirtää muistiinpanot sivulle ilman uutta sivulatausta
    ```