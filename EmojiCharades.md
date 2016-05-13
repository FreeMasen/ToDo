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



#### messages
id | sender | emoji | reciever | resonse | pointTo
----|----------|----------|---------|-----|------
autoInt | nvarchar(50) | nvarchar(1000) | nvarchar(50) | nvarchar(1000) | bit
