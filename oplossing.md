Vul onderstaande aan met de antwoorden op de vragen uit de readme.md file. Wil je de oplossingen file van opmaak voorzien? Gebruik dan [deze link](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) om informatie te krijgen over
opmaak met Markdown.

a) 
1) Toegang tot Docker commando's:
De jenkins gebruiker is toegevoegd aan de docker groep om Docker commando's te kunnen uitvoeren zonder dat daar root-rechten (sudo) voor nodig zijn. Dit hebben we gedaan via volgend commando:
"sudo usermod -aG docker jenkins"

b)
1) Toegang tot SSH:
Om toegang via ssh te krijgen hebben we een SSH-sleutel PROD_SERVER_KEY toegevoegd aan de Jenkins credentials en die aan de ubuntu gebruiker van de testserver gekoppeld. Dit zorgt ervoor dat Jenkins toegang krijgt tot de server.

2) Toegang tot Docker commando's:
De gebruiker "ubuntu" werd toegevoegd aan de docker groep, zodat die de docker commando's kan gebruiken. Jenkins gebruikt de login van de gebruiker "ubuntu" om SSH toegang te krijgen op de productie server. Bij deze kan hij dus op de productie server docker commando's uitvoeren.
 "sudo usermod -aG docker $USER"
Deze commando wordt uitgevoerd op de remote productie server, ingelogd als "ubuntu".
(tijdens een userscript die ook docker installeert en hierna dit uitvoert)
