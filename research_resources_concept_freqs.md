# concept frequency table
- this code creates a fundamental structure TDSL commonly uses in OMOP databases to see the frequencies of concept_id's. 

~~~
SELECT a.*, concept_name FROM (
  SELECT 'condition' AS domain, condition_concept_id AS concept_id,
          COUNT(condition_concept_id) AS freq, COUNT(DISTINCT person_id) AS unique_person_count
  FROM condition_occurrence
  GROUP BY condition_concept_id
  UNION
  SELECT 'procedure' AS domain, procedure_concept_id AS concept_id,
          COUNT(procedure_concept_id) AS freq, COUNT(DISTINCT person_id) AS unique_person_count
  FROM procedure_occurrence
  GROUP BY procedure_concept_id
  UNION
  SELECT 'observation' AS domain, observation_concept_id AS concept_id,
          COUNT(observation_concept_id) AS freq, COUNT(DISTINCT person_id) AS unique_person_count
  FROM observation
  GROUP BY observation_concept_id
  UNION
  SELECT 'visit' AS domain, visit_concept_id AS concept_id,
          COUNT(visit_concept_id) AS freq, COUNT(DISTINCT person_id) AS unique_person_count
  FROM visit_occurrence
  GROUP BY visit_concept_id
  UNION
  SELECT 'drug' AS domain, drug_concept_id AS concept_id,
          COUNT(drug_concept_id) AS freq, COUNT(DISTINCT person_id) AS unique_person_count
  FROM drug_exposure
  GROUP BY drug_concept_id
  UNION
  SELECT 'measurement' AS domain, measurement_concept_id AS concept_id,
          COUNT(measurement_concept_id) AS freq, COUNT(DISTINCT person_id) AS unique_person_count
  FROM measurement
  GROUP BY measurement_concept_id
) AS a
LEFT JOIN concept
ON a.concept_id = concept.concept_id
~~~
