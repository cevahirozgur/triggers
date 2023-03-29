# triggers

### How to create triggers on SQL and how to use triggers?

#### (This study about update tiggers)

![240_F_400609414_VYT4smbkyONjzb60buwMvO05oGFxeWT0](https://user-images.githubusercontent.com/89588465/228642497-d1ea56d5-ae9d-4ca9-b6af-5c089e3c21fb.jpg)

### Firstly, create a database and give it a name like TRG. Then create an ITEMS table and enter 1000 line record.

![image](https://user-images.githubusercontent.com/89588465/228642706-a682234c-2ae5-4f87-8290-21cc6b5c8135.png)

![image](https://user-images.githubusercontent.com/89588465/228642829-187a84eb-02ad-4161-9b6e-965ea3c8e86f.png)

![Untitled](https://user-images.githubusercontent.com/89588465/228643052-ac86632c-b79e-453b-8994-15413e898008.png)


### Create a table named ITEMTRANSACTION for input/output operations. Then enter records (1000 line)

![image](https://user-images.githubusercontent.com/89588465/228643209-e5228ede-2b17-4100-b9ea-2952223db43b.png)

![image](https://user-images.githubusercontent.com/89588465/228643355-5861a3a4-c12d-4669-824e-b540b0014610.png)


### Create a dataset with a sub query to view the stock movement in the ITEMS table according to the input and output in the ITEMTRANSACTION table.

![image](https://user-images.githubusercontent.com/89588465/228643518-9035ed9f-550b-49ab-9745-1d88eb84536b.png)

![Untitled (1)](https://user-images.githubusercontent.com/89588465/228643593-9375fee6-5014-4b80-8a26-e9de33d336f3.png)

### But writing this way is costly. We can find the cost of this operation to SQL Server by typing SET STATISTICS IO ON before SELECT:

![image](https://user-images.githubusercontent.com/89588465/228643704-201797dd-c826-44a1-be9c-fbfd83a6d447.png)

### logical reads= 748 (in the other words, 748 page is reading)

## NOW IT'S TRIGGER TIME !!!

### Firstly, create an ITEMSTOCK table. Enter records into this table but first clean the inside of the ITEMTRANSACTION table 

TRUNCATE TABLE ITEMTRANSACTION 

![image](https://user-images.githubusercontent.com/89588465/228644208-d424d2e2-a1ff-4f77-a527-ec75c7f71644.png)

![image](https://user-images.githubusercontent.com/89588465/228644314-7804e8b0-d5dd-438c-a426-c95625c9bbd6.png)

### Then CREATE TRIGGER (INSERTED TRIGGER)

![image](https://user-images.githubusercontent.com/89588465/228645609-ebd0faf5-8f0b-4775-b99e-4158dce3a4ac.png)

### Every time we perform an INSERT operation, there will be a change first in ITEMTRANSACTION and then in ITEMSTOCK. 

![image](https://user-images.githubusercontent.com/89588465/228645696-c0c9370d-9d1b-4d2e-9ce6-270b296886d1.png)

### Run the code again, which will randomly enter 10,000 records into ITEMTRANSACTION at once.

![image](https://user-images.githubusercontent.com/89588465/228645824-71e842ff-d303-4547-a9a6-69f5e6487150.png)

# In the other words, ITEMSTOCK table will automatically update itself when an INSERT entry is made every cycle.


# At the end of the day, the reading from ITEMSTACK will be 5 and SQL's costs will be reduced.









