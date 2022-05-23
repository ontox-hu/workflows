```mermaid
graph TD
  Cases-->LiverTox
  Cases-->KidneyTox
  Cases-->BrainDevTox
  LiverTox-->SystematicReview
  KidneyTox-->SystematicReview
  
  SelectionOfLiterature-->Systema
  SelectionOfExternalDataSources-->experimentalData
  invitroData-->Transcriptomics
  invitroData-->ToxCast
  invitroData-->NCI60
  SelectionOfExternalDataSources-->patientData
  SelectionOfExternalDataSources-->exposureData
  experimentalData-->animalData
  experimentalData-->invitroData
  animalData-->VHPRepository
  patientData-->VHPRepository
  Transcriptomics-->VHPRepository
  exposureData-->VHPRepository
  VHPRepository-->Models
  VHPRepository-->EndUsers
  VHPRepository-->FAIRsharing
  VHPRepository-->Bio.tools
```
