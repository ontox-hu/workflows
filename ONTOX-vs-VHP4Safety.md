```mermaid
flowchart TB

    cases-->KidneyCase
    cases-->LiverCase
    cases-->BrainCase
    cases-->ThyroidCase
    
    KidneyCase-->LiteratureSources
    LiverCase-->LiteratureSources
    BrainCase-->LiteratureSources
    ThyroidCase-->LiteratureSources
    LiteratureSources-->Sysrev[(Sysrev)]
    Sysrev[(Sysrev)]-->Phymdos
    Phymdos-->SBML
    SBML-->CellDesigner
    SBML-->MINERVA
    SBML-->RDF[(RDF)]
    CellDesigner-->PhysMaps
    MINERVA-->PhysMaps
    PhysMaps-->AOP
    VHP4SafetyServices-->GithubRepo
    ONTOXDev-->GithubRepo
    
 %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
 
    subgraph ONTOX
    
    ONTOXDev
    Phymdos-->MINERVA
    Phymdos-->CellDesigner
    CellDesigner-->PhysMaps
    MINERVA-->PhysMaps
    ASPIS4j[(ASPIS4j)]-->AI
    ExternalData-->CompoundData
    CompoundData-->ONTOX-HUB
    ONTOX-HUB-->ASPIS4j[(ASPIS4j)]
    end
 
 %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
 
    subgraph VHP4Safety
    
    ThyroidCase 
    Phymdos-->RDF[(RDF)]
    VHP4SafetyServices
    VHP4SafetyServices-->AI
    ONTOXDev-->AI

    end
    
 %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
 
    RDF[(RDF)]-->AOP
    AOP-->AOPWiki
    AOP-->qAOP
    LiteratureSources-->ExternalSoftware
    ExternalSoftware-->VHP4SafetyServices
    ExternalSoftware-->ONTOXDev
    ExternalData-->ASPIS4j[(ASPIS4j)]
    qAOP-->ASPIS4j[(ASPIS4j)]
    ASPIS4j[(ASPIS4j)]-->RDF[(RDF)]
    ExternalData-->RDF[(RDF)]
    
    
```
