sequenceDiagram

  participant browser
  participant server

  browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
  activate server
  server-->browser: Status Code 201
  deactivate server

  Note right of browser: selain suorittaa JavaScript koodia, joka määrittää datan tyypiksi JSON ja lähettää se JSON-merkkijonona palvelimelle tallennettavaksi ja 
  lisää uuden muistiinpanon listalle, piirtämällä listan uudeeleen
  Note right of server: palvelin vastaa koodilla 201 created, joka tarkoittaa, että uusi muistiinpano on tallennettu, eikä pyydä uudeeleenohjausta,
  jolloin sivun uudeelleenkäynnistystä ei tapahtu
