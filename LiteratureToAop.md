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
  
  
  SystematicReview((SystematicReview))-->Phase1AbstractScreen((Phase1AbstractScreen))
  ((Phase1AbstractScreen))-->Phase2FullTextDataExtraction((Phase2FullTextDataExtraction))
  Sysrev[(Sysrev)]-->NLP
  NLP-->|en-tox| NER
  NER-->|CREW| CausalRelations
  CausalRelations-->ASPIS4j[(ASPIS4j)]
  CausalRelations-->PhysMaps((PhysMaps))
  
  
  Phase2FullTextDataExtraction((Phase2FullTextDataExtraction))-->patientData{patientData}
  Phase2FullTextDataExtraction((Phase2FullTextDataExtraction))-->clinicalChemistryData{clinicalChemistryData}
  Phase2FullTextDataExtraction((Phase2FullTextDataExtraction))-->exposureData{exposureData}
  Phase2FullTextDataExtraction((Phase2FullTextDataExtraction))-->invitroData{invitroData}
  Phase2FullTextDataExtraction((Phase2FullTextDataExtraction))-->Models(Models)
  Phase2FullTextDataExtraction((Phase2FullTextDataExtraction))-->geneExpressionData{geneExpressionData}
  Phase2FullTextDataExtraction((Phase2FullTextDataExtraction))-->animalData{animalData}
  
  clinicalChemistryData{clinicalChemistryData}-->PhysMaps((PhysMaps))
  invitroData{invitroData}-->PhysMaps((PhysMaps))
  geneExpressionData{geneExpressionData}-->PhysMaps((PhysMaps))
  animalData{animalData}-->PhysMaps((PhysMaps))
  exposureData{exposureData}-->qAOP
  clinicalChemistryData{clinicalChemistryData}-->qAOP
  patientData{patientData}-->qAOP
  animalData{animalData}-->qAOP
  
  PhysMaps((PhysMaps))-->AOP-->qAOP
  qAOP-->ASPIS4j[(ASPIS4j)]
  PhysMaps((PhysMaps))-->ASPIS4j[(ASPIS4j)]
  
```
