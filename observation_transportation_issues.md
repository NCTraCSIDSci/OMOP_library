# transportation issues  
- identify patient self-report to the questions on patients issues with transportation
- this excludes responses that are clearly and definitively negative 

~~~
select b.concept_name, a.*
from observation a LEFT JOIN concept b on a.observation_concept_id = b.CONCEPT_ID
where observation_concept_id in (3964826, 37020730)
and value_as_string !='No'
~~~

- 3964826 = "has lack of transporation kept you from medical appointments, meetings, work, or from getting things needed for daily living during assessment period" [CMS Assessment]
- 37020730 = "has lack of transportation kept you from medical appointments, meetings, work or from getting things needed for daily living"
