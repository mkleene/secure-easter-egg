# secure-easter-egg


```mermaid
C4Context
      title Easter Egg Context Diagram
      Enterprise_Boundary(b0, "System") {
        
        Person(reader, "Browser", "Someone who is surfing the web")
        Person(publisher, "Publisher", "Someone that wants to add secure content to existing web pages")
      
        System_Boundary(frontend, "Frontend") {
        System(plugin, "Browser Plugin", "")
        }

        System_Boundary(backend, "Backend") {
        System(idp, "IDP", "Issues access tokens containing attributes")
 
        System(discovery_server, "Discovery Server", "Given a user auth token containing user attributes and a web page returns relevant decrypted TDFs")
}


        Rel(reader, idp, "gets access token")
        Rel(publisher, idp, "Assigns attributes to users")
        Rel(publisher, discovery_server, "Registers TDFs with URLs")
        Rel(plugin, discovery_server, "Sends access token and webpage to get relevant TDFs")
        Rel(plugin, reader, "shows user decrypted content")
}

      
```
