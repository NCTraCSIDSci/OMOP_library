# arsenic labs  
- identifying labs that are commonly clinically used to detect exposure to arsenic in patients

~~~
select * from measurement where measurement_concept_id in
(3000138,3042549,3023978,4244200,3000566,3013494,3017872,3033341,3038918)
~~~

- 3000138 = arsenic [mass/volume] in blood
- 3042549 = Arsenic.methylated [Mass/volume] in Urine
- 3023978 = Arsenic/Creatinine [Mass Ratio] in Urine
- 4244200 = arsenic measurement
- 3000566 = arsenic [mass/volume] in urine
- 3013494 = Arsenic.inorganic [Mass/volume] in Urine
- 3017872 = Arsenic [Mass/volume] in 24 hour Urine
- 3033341 = Arsenic [Mass/time] in 24 hour Urine
- 3038918 = Arsenic organic [Mass/volume] in Urine
