# De voordelen van gRPC in microservice-architecturen

## Inleiding
In de wereld van softwareontwikkeling zijn microservices een populaire architecturale stijl geworden. Deze aanpak maakt het mogelijk om complexe applicaties te bouwen door ze op te splitsen in kleinere, onafhankelijke diensten. Maar hoe communiceren deze microservices met elkaar? Hier komt gRPC om de hoek kijken. Deze blog verkent de voordelen van gRPC binnen microservice-architecturen in vergelijking met andere communicatiestandaarden, zoals REST.


## gRPC
gRPC, ontwikkeld door Google, is een open-source framework voor Remote Procedure Calls (RPC). Het is ontworpen voor efficiënte communicatie tussen gedistribueerde systemen en maakt gebruik van Protocol Buffers (protobuf) als interface-definitietaal. Protobuf is een lichtgewicht en efficiënt gegevensserialisatieformaat dat de structuur van gegevens definieert in een eenvoudig leesbaar formaat, waardoor gegevens snel kunnen worden verzonden en ontvangen. Dit maakt gRPC een veelzijdige keuze voor ontwikkelaars, omdat het ondersteunt datacommunicatie in meerdere programmeertalen.

Steeds meer bedrijven stappen over op gRPC. Organisaties zoals Square en Netflix hebben de voordelen van deze technologie al omarmd en hun systemen aangepast. Ze benadrukken de verbeterde prestaties, de eenvoud van integratie en de mogelijkheid om complexe systemen te beheren.

![netflix-logo](./plaatjes/netflix-logo.png)

Figuur 1: <ins>Netflix gebruikt gRPC in hun architectuur</ins>.

Een van de grootste voordelen van gRPC is de hoge prestaties. Dit wordt mede mogelijk gemaakt door het gebruik van HTTP/2, een modern transportprotocol dat aanzienlijke verbeteringen biedt ten opzichte van zijn voorganger, HTTP/1.1. HTTP/2 ondersteunt multiplexing, wat betekent dat meerdere verzoeken gelijktijdig over dezelfde verbinding kunnen worden verzonden. Dit vermindert de latentie en verhoogt de efficiëntie van de communicatie. Daarnaast biedt HTTP/2 server push-functionaliteit, wat het mogelijk maakt om data vooraf te verzenden voordat de client erom vraagt, waardoor de snelheid verder toeneemt.

![http2](./plaatjes/http2.png)

Figuur 2: <ins>Overzicht van de werking van http2</ins>.

Daarnaast ondersteunt gRPC verschillende communicatiestijlen, waaronder eenvoudige aanroepen en bidirectionele streaming. Dit maakt het bijzonder geschikt voor microservices-architecturen, waar verschillende diensten effectief met elkaar moeten communiceren. gRPC biedt niet alleen lage latentie, maar ook een hoge doorvoer, wat cruciaal is voor toepassingen die real-time gegevensuitwisseling vereisen.

![gprc-flow](./plaatjes/grpc-flow.png)

Figuur 3: <ins>Voorbeeld gebruik van gRPC in een microservice</ins>.


## gRPC vs. REST
Om de voordelen van gRPC volledig te begrijpen, is het belangrijk om de traditionele REST-architectuur te bekijken. REST (Representational State Transfer) is een populaire stijl voor netwerkgebaseerde applicaties die gebruikmaakt van standaard HTTP-methoden. RESTful API's zijn stateless, wat betekent dat elke aanvraag onafhankelijk is en alle benodigde informatie bevat.

REST heeft voordelen zoals eenvoud en brede toepassing. Het is resource-gebaseerd en ondersteunt verschillende dataformaten zoals JSON en XML. In microservices-architecturen kan gRPC echter vaak betere prestaties leveren, vooral waar snelheid en efficiëntie cruciaal zijn.

REST is de meest gebruikte architecturale stijl voor API's. In een RESTful architectuur worden resources geïdentificeerd door URI's (Uniform Resource Identifiers) en operaties uitgevoerd met een standaardset van HTTP-methoden. Resources worden vertegenwoordigd in JSON of XML, die tussen client en server worden overgedragen via HTTP-verzoeken en -antwoorden.

GRPC en REST delen enkele belangrijke overeenkomsten. Beide volgen de client-serverarchitectuur, waarbij clients verzoeken verzenden en servers reageren. Ze gebruiken HTTP als onderliggend transportprotocol, waarbij REST HTTP/1.1 en gRPC HTTP/2 gebruikt. Beide zijn taalagnostisch, wat betekent dat ze in verschillende programmeertalen kunnen worden geïmplementeerd. Verder zijn ze ontworpen om stateless te zijn, zodat elke aanvraag alle informatie bevat die nodig is voor verwerking.

Ondanks deze overeenkomsten verschillen gRPC en REST sterk in architectonisch ontwerp en implementatiedetails. De belangrijkste verschillen zijn:

1. **Gegevensformaat:** REST gebruikt meestal tekstgebaseerde formaten zoals JSON en XML, terwijl gRPC Protobuf hanteert om gegevens in binair formaat te coderen, wat efficiënter is.

2. **Gegevensvalidatie:** Bij gRPC definieert de ontwikkelaar service- en berichttypes met Protobuf, wat automatische validatie van berichten mogelijk maakt. REST vereist extra validatiestappen, wat meer verwerkingstijd kost.

3. **Communicatiepatroon:** REST volgt een eenmalige aanvraag/antwoord-cyclus, terwijl gRPC verschillende communicatiepatronen ondersteunt, zoals serverstreaming, clientstreaming en bidirectionele streaming dankzij HTTP/2.

4. **Ontwerppatroon:** gRPC APIs definiëren oproepbare functies op de server, terwijl REST APIs een resource-georiënteerd ontwerp hebben dat gebruikmaakt van standaard HTTP-methoden.

5. **Codegeneratie:** gRPC's gebruik van Protobuf ondersteunt codegeneratie in verschillende programmeertalen, wat het ontwikkelproces versnelt. REST biedt deze ondersteuning niet standaard.

REST is momenteel de meest gebruikte API-architectuur. Het is eenvoudiger te leren en compatibel met de meeste programmeertalen en platforms, waardoor het ideaal is voor openbare API's. gRPC is beter geschikt voor microservices-architecturen, waar hoge efficiëntie, lage latentie en ondersteuning voor verschillende programmeertalen vereist zijn. Het is de betere keuze voor toepassingen die real-time interacties vereisen, zoals chat- en video-applicaties, vanwege de bidirectionele streamingcapaciteiten en efficiënte gegevensverwerking.

Met deze inzichten in de verschillen en overeenkomsten tussen gRPC en REST kun je een weloverwogen keuze maken over welke technologie het beste past bij jouw specifieke gebruiksscenario's en vereisten.


## Waarom gRPC voor Microservices Communicatie?
Om de beperkingen die vaak worden aangetroffen in RESTful diensten aan te pakken, is er een groeiende behoefte aan een modern inter-process communicatiesysteem dat schaalbaarheid en superieure efficiëntie biedt. Hier komt gRPC om de hoek kijken, een geavanceerd open-source RPC-framework. Dit framework maakt gebruik van een binair coderingsformaat genaamd Protocol Buffers en opereert bovenop HTTP/2. Het biedt sterke typing, ondersteunt meerdere programmeertalen en faciliteert bidirectionele streaming voor zowel client- als serverzijde. Hierdoor is gRPC bijzonder geschikt voor het bouwen van robuuste microservice-architecturen die hoge prestaties en schaalbaarheid vereisen.

De combinatie van hoge prestaties, lage latentie en krachtige communicatiemogelijkheden maakt gRPC een uitstekende keuze voor moderne microservices. Door over te stappen naar gRPC kunnen organisaties profiteren van snellere en schaalbare systemen die beter zijn afgestemd op de eisen van hedendaagse applicaties. Nu we een basisbegrip hebben van gRPC en REST, laten we kijken naar de specifieke voordelen die gRPC biedt in microservice-architecturen. gRPC maakt gebruik van multiplexing, waardoor meerdere verzoeken en antwoorden gelijktijdig over dezelfde verbinding kunnen worden verzonden. Dit vermindert de overhead van het openen en sluiten van verbindingen, wat resulteert in snellere communicatie, vooral in omgevingen waar veel microservices met elkaar moeten samenwerken.

Bovendien is gRPC geoptimaliseerd voor lage latentie, wat het bijzonder geschikt maakt voor toepassingen die real-time interacties vereisen, zoals in cloud-gebaseerde architecturen. In een microservices-architectuur is inter-process communicatie essentieel voor het uitwisselen van informatie. Microservices kunnen met elkaar communiceren via twee primaire mechanismen: Synchronous Communication (Request-Reply), waarbij één service de communicatie initieert door een API aan te roepen die door een andere service wordt aangeboden en wacht op een antwoord; en Asynchronous Communication, waarbij een service een bericht verzendt zonder een onmiddellijke reactie te verwachten. Meerdere services kunnen deze berichten potentieel afhandelen en verwerken.


## Stapsgewijze implementatie van gRPC



## Conclusie
gRPC biedt aanzienlijke voordelen binnen microservice-architecturen, met name op het gebied van prestaties en efficiëntie. Dankzij de ondersteuning voor binaire communicatie via Protocol Buffers, en de voordelen van HTTP/2 zoals multiplexing en bidirectionele streaming, stelt gRPC ontwikkelaars in staat om systemen te bouwen die sneller en schaalbaarder zijn dan traditionele REST-oplossingen. Hoewel REST een bewezen en populaire keuze blijft, laat gRPC zien dat het, vooral in omgevingen waar lage latentie en hoge doorvoer essentieel zijn, een krachtig alternatief biedt. Voor moderne microservices-architecturen, waar snelle en efficiënte communicatie cruciaal is, is gRPC vaak de betere keuze.## gRPC versus REST


Voor wie geïnteresseerd is in de technische details en meer over gRPC wil leren, is de [gRPC: get started](https://grpc.io/docs/what-is-grpc/introduction/) een uitstekende bron.

Als je meer wilt weten over de specifieke toepassingen van gRPC in microservices, bekijk dan deze [link](https://www.linkedin.com/pulse/microservices-communication-using-grpc-protocol-prabhat-pankaj).    

