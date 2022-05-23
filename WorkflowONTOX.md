```mermaid
graph TD
  
  ONTOX-->Cases

  Cases-->LiverTox
  Cases-->KidneyTox
  Cases-->BrainDevTox
  
  LiverTox-->SystematicReview-->Sysrev
  KidneyTox-->SystematicReview-->Sysrev
  BrainDevTox-->SystematicReview-->Sysrev
  
  Sysrev: SBtabLabels-->>rsr: SBMLConverter-->>Phymdos: SBML-->ASPIS4j
  
  SystematicReview-->Phase1AbstractScreen
  Phase1AbstractScreen-->Phase2FullTextDataExtraction
  
  Phase2FullTextDataExtraction-->patientData
  Phase2FullTextDataExtraction-->clinicalChemistryData
  Phase2FullTextDataExtraction-->exposureData
  Phase2FullTextDataExtraction-->invitroData
  Phase2FullTextDataExtraction-->Models
  Phase2FullTextDataExtraction-->geneExpressionData
  Phase2FullTextDataExtraction-->animalData
  
  SelectionOfExternalDataSources-->patientData
  SelectionOfExternalDataSources-->clinicalChemistryData
  SelectionOfExternalDataSources-->exposureData
  SelectionOfExternalDataSources-->invitroData
  SelectionOfExternalDataSources-->Models
  
  LiverToxLab-->LabExperiments
  KidneyTox-->LabExperiments
  BrainDevTox-->LabExperiments
  
  SlectionOfChemicals-->LabExperiments
  
  invitroData-->ComparativeToxicogenomicsDatabase
  ComparativeToxicogenomicsDatabase-->ASPIS4j
  invitroData-->Tox21
  invitroData-->EPAADashboard
  invitroData-->ToxCast
  invitroData-->NCI60
  
  clinicalChemistryData-->LiverToxBookshelfBook
 
  Tox21-->ASPIS4j[(ASPIS4j)]
  ToxCast-->ASPIS4j[(ASPIS4j)]
  NCI60-->ASPIS4j[(ASPIS4j)]
  EPAADashboard-->ASPIS4j[(ASPIS4j)]
  animalData-->ASPIS4j[(ASPIS4j)]
  patientData-->ASPIS4j[(ASPIS4j)]
  invitroData-->ASPIS4j[(ASPIS4j)]
  exposureData-->ASPIS4j[(ASPIS4j)]
  ASPIS4j[(ASPIS4j)]-->Models
  ASPIS4j[(ASPIS4j)]-->EndUsers
  ASPIS4j[(ASPIS4j)]-->FAIRsharing
  ASPIS4j[(ASPIS4j)]-->RDF
  RDF[(RDF)]-->ASPIS4j[(ASPIS4j)]
  
  ASPIS4j[(ASPIS4j)]-->RASAR
  ASPIS4j[(ASPIS4j)]-->BNN
  RASAR-->AI
  BNN-->AI
  AI-->ProbRA
  
  
```
