```mermaid
flowchart TD
  
  ONTOX-->Cases

  Cases-->LiverTox
  Cases-->KidneyTox
  Cases-->BrainDevTox
  
  LiverTox-->SystematicReview((SystematicReview))
  KidneyTox-->SystematicReview((SystematicReview))
  BrainDevTox-->SystematicReview((SystematicReview))
  
  SystematicReview((SystematicReview))-->Sysrev[(Sysrev)]
  
  Sysrev[(Sysrev)]-->|SBtabLabels| rsr
  rsr-->|SysrevAPI| Phymdos
  Phymdos-->|SBMLConverter| CellDesigner
  Phymdos-->|SBMLConverter| MINERVA
  Phymdos-->|GraphQL| ASPIS4j
  CellDesigner(CellDesigner)-->PhysMaps((PhysMaps))
  MINERVA(MINERVA)-->PhysMaps((PhysMaps))
  
  
  SystematicReview((SystematicReview))-->Phase1AbstractScreen
  Phase1AbstractScreen-->Phase2FullTextDataExtraction
  Sysrev[(Sysrev)]-->NLP
  NLP-->|en-tox| NER
  NER-->|CREW| CausalRelations
  CausalRelations-->ASPIS4j[(ASPIS4j)]
  CausalRelations-->PhysMaps((PhysMaps))
  
  
  Phase2FullTextDataExtraction-->patientData
  Phase2FullTextDataExtraction-->clinicalChemistryData
  Phase2FullTextDataExtraction-->exposureData
  Phase2FullTextDataExtraction-->invitroData
  Phase2FullTextDataExtraction-->Models
  Phase2FullTextDataExtraction-->geneExpressionData
  Phase2FullTextDataExtraction-->animalData
  
  clinicalChemistryData-->PhysMaps((PhysMaps))
  invitroData-->PhysMaps((PhysMaps))
  geneExpressionData-->PhysMaps((PhysMaps))
  animalData-->PhysMaps((PhysMaps))
  exposureData-->qAOP
  clinicalChemistryData-->qAOP
  patientData-->qAOP
  animalData-->qAOP
  
  PhysMaps((PhysMaps))-->AOP-->qAOP
  qAOP-->ASPIS4j[(ASPIS4j)]
  PhysMaps((PhysMaps))-->ASPIS4j[(ASPIS4j)]
  
```
