sequenceDiagram

participant browser
participant server

browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
activate server
server-->browser: Status Code 302
deactivate server

Note right of server: POST-pyynnön vastauksena palvelin lähettää uudeelleenohjauspyynnön, eli kehottaa selainta tekemään uuden HTTP Get -pyynnön osoitteeseen /exampleapp/notes

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
activate server
server-->browser: HTML document
deactivate server

Note rignt of browser: kun selain alkaa suorittamaan html-koodia, se lähettää palvelimelle uuden HTTP GET -pyynnön koodissa määritettyyn osoitteeseen /exampleapp/main.css

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server-->browser: CSS file
deactivate server

Note right of browser: selain jatkaa html-koodin suorittamista ja lähettää serverille HTTP GET -pyynnön koodissa määritettyyn osoitteeseen /exampleapp/main.js

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
activate server
server-->browser: JavaScript file
deactivate server

Note right of browser: kun selain suorittaa vastauksena saadun JavaScript tiedoston, se lähettää serverille HTTP GET -pyynnön koodissa määritettyyn osoitteeseen /exampleapp/data.json

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server-->browser: JSON file
deactivate server

Note right of browser: selain renderöi data.json -tiedoston sisältö näytölle
