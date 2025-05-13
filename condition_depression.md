# depressive episode  
 - this approach uses a high level ancestor code of depressive disorder

~~~
where condition_concept_id IN
(select distinct descendant_concept_id from concept_ancestors where ancestor_concept_id=440383)
~~~
