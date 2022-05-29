```mermaid
flowchart TB
    literatureSources-->Sysrev
    subgraph ONTOX
    Sysrev-->Phymdos
    Phymdos-->MINERVA
    Phympdos-->CellDesigner
    end
    subgraph VHP4Safety
    Sysrev-->Phymdos
    Phymdos-->[(RDF)]
    end
    
```
