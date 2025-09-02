	FOSM-27: Create GET API for Retrieving All Failed Transactions
•	FOSM-36: Create GET API for Retrieving Cases Related to Transactions
•	FOSM-26: Create GET API for Retrieving All Transactions for a Given Case

        1) it is in case service management application;
        2) in service management application, it has case-reader and case writer modules;
        3) these 3 user stories are used to retrieve case. transaction and failed transaction, and their controllers are created in reader    module.

        4)  Failed Transactions, Cases and transactions has independent controllers, also it has independent services. it has mapper class to map dto and entity class.

        5) dto and entity are organized in dto and model modules.

        6) for these user stories, I create unit test cases and testing coverage reach 100%.



•	FOSM-41: Create GET API for Managing SysPrin Details for a Client
•	FOSM-34: Create GET API for Retrieving Client Details by Client ID
•	FOSM-42: Create GET API for Finding SysPrin by Client ID and SysPrin Name
	FOSM-29: Create GET API for Retrieving Clients Based on Page Number (Paging)

•	FOSM-33: Create PUT API for Updating a Client

      1) these 5 user stories is in client-sysprin application. for get api, it is in reader module. for different types of api, they have independent controller. also it has mapper, dto and models classes are organized in different modules.


 

•	FOSM-90: Create GET API for Retrieving Clients Based on Wildcards


last user story has used lucene technology, i organize it in a new module in search-integration module.

i have tested all the user stories in dev environment. i have documented all the testing process. once after i format this document, i will share with terry to review.
