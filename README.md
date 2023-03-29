# triggers

# How to create triggers on SQL and how to use triggers?

# Firstly, create a database and give it a name like TRG. Then create an ITEMS table and enter 1000 line record.

![image](https://user-images.githubusercontent.com/89588465/228600858-64793b1c-c29b-46e7-86d6-cc2a27bdb6cc.png)

DECLARE @I AS INT=1
WHILE @I<=1000
BEGIN
DECLARE @ITEMCODE AS VARCHAR(100)
DECLARE @ITEMNAME AS VARCHAR(100)
SET @ITEMCODE='ITEM000'+CONVERT(VARCHAR,@I)
SET @ITEMNAME='MALZEME'+CONVERT(VARCHAR,@I)

INSERT INTO ITEMS (ITEMCODE,ITEMNAME)
VALUES (@ITEMCODE,@ITEMNAME)

SET @I=@I+1
END

SELECT * FROM ITEMS
