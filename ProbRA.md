
```mermaid
flowchart TD


  subgraph Exposure_Scenarios
  
  Intended_Use?-->|yes| Exposure_Ext(Exposure_Ext _/\_ )
  Intended_Use?-->|no| No_Risk_Assessment{No_Risk_Assessment}
  Chemical_Spill?-->|yes| No_Risk_Assessment{No_Risk_Assessment}
  No_Risk_Assessment{No_Risk_Assessment}--> |Clinical_Case_Available?| Case_Study_Data(Case_Study_data)
  Case_Study_Data(Case_Study_data)-->Exposure_Ext(Exposure_Ext _/\_ )
  
  
  end

  %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

  subgraph AI

  Artificial_Intelligence-->Data_Extraction
  Data_Extraction-->NAMS
  Artificial_Intelligence-->Data_Integration
  
  end
  
  %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
  
  subgraph animal_data
  
  Exposure_Ext(Exposure_Ext _/\_)-->Absortion(Absorption _/\_)
  Absortion(Absorption _/\_)-->Systemic_Circulation(Systemic_Circulation _/\_)
  Systemic_Circulation(Systemic_Circulation _/\_)-->Tissue(Tissue _/\_)
  Tissue(Tissue _/\_)-->Exposure_Int(Exposure_Int _/\_)
  
  end
  
  %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
  
  subgraph nams_data
  
  NAMS-->Exposure_InVitro(Exposure_InVitro _/\_)
  Data_Integration-->NAMS
  Exposure_InVitro-->QIVIVE
  QIVIVE-->Exposure_Int(Exposure_Int _/\_)
  
  end
  
  %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
  
  subgraph TTC
  
  Exposure_Int(Exposure_Int _/\_)-->History_of_Safe_Use{History_of_Safe_Use}
  History_of_Safe_Use{History_of_Safe_Use}-->|yes| TTC(TTC)
  History_of_Safe_Use{History_of_Safe_Use}-->|no| TTC(TTC)
  
  end
  
  
  
```






