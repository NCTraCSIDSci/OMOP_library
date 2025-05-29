# concept relationship freq table
- this code creates a fundamental structure TDSL commonly uses in OMOP databases to navigate and use the OMOP ontology when building concept sets
- specifically this creates a form of the concept relationship table that shows ancestor->descendant concept relationships with the frequencies of those concepts from tables where 'concept_freqs' was calculated
- note this codes requires another research_resource table structure 'concept_freqs' to already be created
~~~
CREATE TABLE concept_relationship_freq AS
SELECT DISTINCT
  c1.domain_id AS ancestor_domain,
  ca.ancestor_concept_id,
  c1.concept_name AS ancestor,
  cf1.freq AS ancestor_freq,
  '---------------' AS buffer,
  c2.domain_id AS descendant_domain,
  ca.descendant_concept_id,
  c2.concept_name AS descendant,
  cf2.freq AS descendant_freq,
  ca.min_levels_of_separation,
  ca.max_levels_of_separation
FROM concept_ancestor ca
LEFT JOIN concept c1 ON ca.ancestor_concept_id = c1.concept_id
LEFT JOIN concept c2 ON ca.descendant_concept_id = c2.concept_id
LEFT JOIN concept_freqs cf1 ON ca.ancestor_concept_id = cf1.concept_id
LEFT JOIN concept_freqs cf2 ON ca.descendant_concept_id = cf2.concept_id
WHERE ca.ancestor_concept_id != ca.descendant_concept_id
~~~
