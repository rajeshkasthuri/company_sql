### Following command give you the all mandals under district
(this will include the unneccessary places)
	
  ```sql
  select * from location_association where parent_location_id = district_id; 
  ```
  
  ```sql
	select * from location_type_map as l join  (select child_location_id  from location_association where parent_location_id = district_id) as k
 where l.location_type_md_id = 4 and l.location_id = k.child_location_id ;
```
 ### Following commnad give you the all village in a mandal
```sql
select * from location_association where parent_location_id = child_location_id;
```    
	
###  For knowing the name use location table 
```sql
select * from location where location_id = id;
```
#### for getting the grids under the village 
  use the entity_intersection table to get the uuid of the grid
```sql  
  select * from entity_intersection where entity_uuid = 'Village UUID';
```  
  from this you will get `associated_entity_uuid` 
