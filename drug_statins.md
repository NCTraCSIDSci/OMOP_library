# anti-hyperlipidemia medications  
- focuses on identifying statin-based drugs mainly intended for treating hyperlipidemia

~~~
select * from drug_exposure INNER JOIN concept_ancestor on drug_exposure.concept_id = concept_ancestor.concept_id
where concept_ancestor_id IN (1510813, 1545958, 1539403, 1551860, 1592085, 1549686, 40165636)
~~~
- 1510813 = rosuvastatin
- 1545958 = atorvastatin
- 1539403 = simvastatin
- 1551860 = pravastatin
- 1592085 = lovastatin
- 1549686 = fluvastatin
- 40165636 = pitavastatin
