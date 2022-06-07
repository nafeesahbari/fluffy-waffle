# fluffy-waffle

import mysql.connector 

mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    password="ENTER YOURS"
)

mycursor = mydb.cursor()

mycursor.execute("CREATE DATABASE menagerie ")


import mysql.connector 

mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    password="ENTER YOURS"
)

mycursor = mydb.cursor()

mycursor.execute("CREATE TABLE pets (name VARCHAR(20), owner VARCHAR(20), species VARCHAR(20), sex CHAR(1), birth DATE, death Date")


import mysql.connector 

mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    password="ENTER YOURS"
)

mycursor = mydb.cursor()

mycursor.execute("DESCRIBE pets")

for x in mycursor:
    print(x)

import mysql.connector 

mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    password="ENTER YOURS"
)

mycursor = mydb.cursor()

sql = "INSERT INTO pet ( name, owner, species, sex, birth, death)
val = [
    ('Fluffy', 'Harold', 'cat', 'f', '1993-02-04', None),
    ('Claws', 'Gwen', 'cat', 'm', '1993-02-04', None),
    ('Buffy', 'Harold', 'dog', 'f', '1993-02-04', None),
    ('Fang', 'Benny', 'dog', 'm', '1993-02-04', None),
    ('Bowser', 'Diane', 'dog', 'm', '1993-02-04', '1995-07-29'),
    ('Chirpy', 'Gwen', 'bird', 'f', '1993-02-04', None),
    ('Whistler', 'Gwen', 'cat', None, '1993-02-04', None),
    ('Slim', 'Benny', 'snake', 'm', '1993-02-04', None)
]

mycursor.executemany(sql, val)

mydb.commit()

print(mycursor.rowcount, "was inserted. ")

import mysql.connector 

mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    password="ENTER YOURS"
)

mycursor = mydb.cursor()

sql = "SELECT * FROM pet WHERE sex ='f'"

mycursor.execute(sql)

myresult = mycursor.fetchall()

for x in myresult:
   print(x)

import mysql.connector 

mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    password="ENTER YOURS"
)

mycursor = mydb.cursor()

mycursor.execute("SELECT name, birth FROM pets")

myresult = mycursor.fetchall()

for x in myresult:
    print(x)


import mysql.connector 

mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    password="ENTER YOURS"
)

mycursor = mydb.cursor()

mycursor.execute("SELECT owner, COUNT(*) FROM pets GROUP BY owner")

myresult = mycursor.fetchall()

for x in myresult:
    print (x)


import mysql.connector 

mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    password="ENTER YOURS"
)

mycursor = mydb.cursor()

mycursor.execute("SELECT name, birth, MONTH(birth)FROM pets ")

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
