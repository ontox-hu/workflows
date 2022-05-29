```mermaid
flowchart TB
    literatureSources-->Sysrev[(Sysrev)]
    
    subgraph ONTOX
    Sysrev[(Sysrev)]-->Phymdos
    Phymdos-->MINERVA
    Phymdos-->CellDesigner
    ExternalData-->ASPIS4j[(ASPIS4j)]
    CellDesigner-->ASPIS4j[(ASPIS4j)]
    MINERVA-->ASPIS4j[(ASPIS4j)]
    
    end
    
    subgraph VHP4Safety
    Sysrev[(Sysrev)]-->Phymdos
    Phymdos-->RDF[(RDF)]
    RDF[(RDF)]-->AOPWiki
    ExternalData-->RDF[(RDF)]
    end
    
```
