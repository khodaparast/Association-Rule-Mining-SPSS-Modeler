# Association-Rule-Mining-SPSS-Modeler
IBM SPSS Modeler had Apriori node for extract association rule mining 
so for data like this:
QuestinId tag
150 java
150 swing
255 android
390 php
...
we can extract rules by mentioned node but there is a limitation! Maximum different category for Nominal or Categorical Type is 250. also we have more than 250 tags in SOF, so we should first select 250 TOP tags and then continue with returned records
//SQL node Query
select * from tags where Tags in (select top 250 Tags from tags group by Tags 
order by count (Tags) DESC)
order by Id
