# Urinary Tract Infection  
-this code attempts to create a concept set for UTI based on simple occurrence of a condition that is descendant to concept 81902 - urinary tract infectious disease  

```
select * from omop.condition_occurrence where condition_concept_id in ( 
 select distinct descendant_concept_id from research_resources.concept_ancestor_freq where  ancestor_concept_id = 81902
                )  
```


- ancestor code 81902 = urinary tract infectious disease
  
- descendant code 37167393 = Urinary tract infection following molar pregnancy
- descendant code 607157 = Infection of urachal remnant
- descendant code 606935 = Bacterial pyuria
- descendant code 37311936 = Infection of urinary tract caused by Herpes simplex
- descendant code 35610224 = Uncomplicated urinary tract infection
- descendant code 764968 = Urinary tract infection following procedure
- descendant code 46269809 = Urinary tract infection due to ectopic pregnancy
- descendant code 46269813 = Urinary tract infection due to incomplete miscarriage
- descendant code 45770841 = Febrile urinary tract infection
- descendant code 43530945 = Induced termination of pregnancy complicated by urinary tract infection
- descendant code 765742 = Infected urachal cyst
- descendant code 4331815 = Acute urinary tract infection
- descendant code 4311853 = Upper urinary tract infection
- descendant code 4146482 = Urinary tract infection in pregnancy
- descendant code 4056621 = Recurrent urinary tract infection
- descendant code 4056622 = Chronic urinary tract infection
- descendant code 4281684 = Failed attempted termination of pregnancy with urinary tract infection
- descendant code 4208664 = Bacterial urinary infection
- descendant code 4033096 = Miscarriage with urinary tract infection
- descendant code 4080456 = Renal tract candidiasis
- descendant code 4047937 = Neonatal urinary tract infection
- descendant code 4220328 = Lower urinary tract infectious disease
- descendant code 4032450 = Urinary schistosomiasis



