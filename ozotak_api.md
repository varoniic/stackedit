

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
		 - @PARAMS: 
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
		 - @PARAMS: 
			 - file

 - #### Delete Project File
   
   - **POST** https://work.ozotak.se/api/v1/project_files/delete/$project_file_id `
		- @PARAMS: 
			- project_file_id
			
### Timelogs

 - #### Get all Timelogs
   
   * **GET** https://work.ozotak.se/api/v1/timelog
	   * @PARAMS
		   * period (optional, default=this month) : @values = last_month | all 
- #### Create timelog
	 * **GET** https://work.ozotak.se/api/v1/timelog

<!--stackedit_data:
eyJoaXN0b3J5IjpbNDgwMTQyMDc2LC03NzY0MTI3MCwtMTYyMD
g3ODE1MiwtMTYxNTUxMjU5NCwxODgzNzM1MTddfQ==
-->