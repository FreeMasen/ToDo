Views
======
#### main view

#### messages view

#### message view

#### profile/settings view

Models
=======

#### user

#### message


Tables
=======

#### users
id | firstName | lastName | emailAddress | score
----|----------|----------|--------------|-----------
autoInt | nvarchar(50) | nvarchar(50) | nvarchar(100) | integer
Primary Key | | | | 


#### messages
id | sender | emoji | reciever | resonse | pointTo
----|----------|----------|---------|-----|------
autoInt | integer | nvarchar(1000) | integer | nvarchar(1000) | bit
Primary Key | Foreign Key | | Foreign Key | | 0=sender, 1=reciever
