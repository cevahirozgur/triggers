# triggers
(This study about triggers for Log Process)

Firstly, create a database named LOGDB. Then, take the script of the [ITEMS] table for the [ETRADE_RDMS] database, create the ITEMS table in the LOGDB database and put new variables related to the Log process.

![image](https://user-images.githubusercontent.com/89588465/228674757-dd7b9457-87b1-43ac-9f19-7b22a4f75482.png)

Create an UPDATE TRIGGER to keep logs.

![image](https://user-images.githubusercontent.com/89588465/228675022-7df5390d-4363-4c0b-a993-382cb955ee93.png)

Let's see what happens when we do UPDATE with the help of this trigger!

![image](https://user-images.githubusercontent.com/89588465/228675296-a5bb9787-e3b2-4ee6-95b0-9579fff85644.png)

![image](https://user-images.githubusercontent.com/89588465/228675339-d5b1e574-2e3d-43be-8ad0-3daad9f1dcad.png)

With the UPDATE we made, we were able to observe this pre-process value and LOG records.
