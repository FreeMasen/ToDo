Views
======
#### main view

* Display the actionable messages
* Display the user's score

#### messages view

* Display messages sent
* Display messages recieved

#### message view

* Display the sender
* Display the reiver
* Display the emoji
* Display the response 
  * If responding as a txtbox
  * If reviewing as a label
* Display the score
  * If scoreing a switch
  * If reviwing a label

#### profile/settings view

* Display the username
* Display the logout button
* Display the user setting
  * Number of archives to keep locally
  * Color scheme
* Display the message count
  * Sent
  * Recieved

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
