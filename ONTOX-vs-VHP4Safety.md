```mermaid
flowchart TB
    literatureSources-->Sysrev[(Sysrev)]
    subgraph ONTOX
    Sysrev[(Sysrev)]-->Phymdos
    Phymdos-->MINERVA
    Phympdos-->CellDesigner
    end
    subgraph VHP4Safety
    Sysrev[(Sysrev)]-->Phymdos
    Phymdos-->RDF[(RDF)]
    end
    
```
