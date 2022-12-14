

Ozotak API Docs

## AUTH

  

#### *Login*

* **POST** https://work.ozotak.se/api/v1/auth/login 
	* @PARAMS: 
		* email
		* password
	* @TEST:
		* karlis@brainagent.co 
		* asdasd123 

#### *Logout*

* **POST** https://work.ozotak.se/api/v1/auth/logout

#### *Renew expired token*

* **GET** https://work.ozotak.se/api/v1/auth/refresh

  

## LOGGED IN ROUTES

*All requests require header authorization with token got from login. Authorization: Bearer + @token*

#### *Get User data*

* **GET** https://work.ozotak.se/api/v1/auth/me

### Projects

  

 - #### *Get all Projects*
   
	 - **GET** https://work.ozotak.se/api/v1/project
 - #### Get Project by Id
   
	 - **GET** https://work.ozotak.se/api/v1/project/$project_id 
		 - @QUERY: 
			 - project_id
		- @TEST: 
			- 12

 - #### Create Project

	* **POST** https://work.ozotak.se/api/v1/project 
		* @PARAMS: 
			* project_name, 
			* project_code, 
			* project_summary

 - #### Upload Project File
   
	 - **POST** https://work.ozotak.se/api/v1/project_files/$project_id 
		 - @QUERY: 
			 - project_id
		 - @PARAMS: 
			 - file

 - #### Delete Project File
   
   - **POST** https://work.ozotak.se/api/v1/project_files/delete/$project_file_id `
		- @QUERY: 
			- project_file_id
			
### Timelogs

 - #### Get all Timelogs
   
   * **GET** https://work.ozotak.se/api/v1/timelog
	   * @PARAMS
		   * period (optional, default=this month) : @values = last_month | all 
- #### Create Timelog Data
	 * **POST** https://work.ozotak.se/api/v1/timelog
		 * @PARAMS
			 * project_id (required)
			 * start_date (required | format: d-m-Y) 
			 * start_time (required | format: i:s)
			 * end_time (required | format: i:s)
			 * lunch_break (in minutes) : @VALUES = 0 | 30 | 60 | 90 | 120
			 * memo (Main timelog comment)
			 * extra_time (format: i:s)
			 * extra_time_comment (required if extra time > 00:00)
- #### Update Timelog Data
	 * **POST** https://work.ozotak.se/api/v1/timelog/$id
		 * @QUERY
			 * id
		 * @PARAMS
			 * start_date (required | format: d-m-Y) 
			 * start_time (required | format: H:i - step 15min)
			 * end_time (required | format: H:i - step 15min)
			 * lunch_break (in minutes) : @VALUES = 0 | 30 | 60 | 90 | 120
			 * memo (Main timelog comment)
			 * extra_time (required | format: H:i - step 15min)
			 * extra_time_comment (required if extra time > 00:00)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg5ODI0OTcxOCwtMTM0MjE3Mjg2NSwtND
U3OTg5OTI5LC00NTk4MTAzMiwtNzc2NDEyNzAsLTE2MjA4Nzgx
NTIsLTE2MTU1MTI1OTQsMTg4MzczNTE3XX0=
-->