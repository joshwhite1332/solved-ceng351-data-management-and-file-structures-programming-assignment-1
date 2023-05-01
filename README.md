Download Link: https://assignmentchef.com/product/solved-ceng351-data-management-and-file-structures-programming-assignment-1
<br>
<h1>1      Introduction</h1>

In the scope of this assignment, you are asked to create a system by designing queries and implementing pre-defined functions to administer a database for a digital music streaming service. For this, you have certain tasks and well-defined interfaces. What you will do is to implement the provided interfaces to accomplish the given tasks. All necessary data files, classes and the interface you will implement are provided as source files. Do not confuse interface with graphical user interface (GUI). You will not design any GUI in the scope of this assignment. You will be familiar with interface which is a data type like class and enum. The first thing you should do is implementing functions which create the necessary tables corresponding to the schema given in Section 3. Then, you should design queries to accomplish the given tasks. Lastly, you should implement the interface using the queries you have designed as they give the desired results when defined parameters are given. You will not implement Evaluation class. It will be implemented by me to manipulate the database through the pre-defined interface and evaluate your implementations. Your task is to build up classes which implement the provided interfaces.

<h1>2       Objectives</h1>

This assignment aims to help you get familiar with

<ul>

 <li>Java programming language basics,</li>

 <li>Object oriented programming concepts,</li>

 <li>Connecting and querying to MySQL Server using JDBC.</li>

</ul>

<h1>3      Schema</h1>

You will use (strictly) the schema given below in the scope of this assignment.

<strong>user</strong>(<u>userID:int</u>, userName:varchar(60), email:varchar(30), password:varchar(30)) <strong>song</strong>(songID:int, songName:varchar(60), genre:varchar(30), rating:double, artistID:int, albumID:int)

<strong>artist</strong>(<u>artistID:int</u>, artistName:varchar(60))

<strong>album</strong>(<u>albumID:int</u>, title:varchar(60), albumGenre:varchar(30), albumRating:double, releaseDate:date, artistID:int) <strong>listen</strong>(<u>userID:int</u>, songID:int, lastListenTime:timestamp, listenCount:int)

Your task is to generate a class named MUSICDB (should belong to package ceng.ceng351.musicdb) which implements IMUSICDB interface. You can create any additional classes if necessary. MUSICDB class should be able to accomplish the following tasks:

<ul>

 <li>Creating the database tables</li>

 <li>Inserting data into tables</li>

 <li>List songs which have the highest rating</li>

 <li>Find the most recent album for a given artist</li>

 <li>List songs that are listened by both users whose usernames are given</li>

 <li>List artists and number of times his/her songs have been listened by the given user</li>

 <li>List users who have listened all songs of a given artist</li>

 <li>List users and number of songs listened by this user such that none of these songs are listened by any other user</li>

 <li>List artists who have sung pop music at least once and whose average rating of all songs is greater than the given rating</li>

 <li>Retrieve songs with the lowest rating in pop category, in case of more than one song exist, retrieve the least listened ones</li>

 <li>Multiply rating of albums by 1.5 whose release dates are after for a given date</li>

 <li>Delete the song for the given song name</li>

 <li>Dropping the database tables</li>

</ul>

Tasks are explained in more detail below. For each task, there is a corresponding method in IMUSICDB interface. You need to implement them in MUSICDB class. Necessary data files (for populating the tables) to accomplish these tasks will be provided. In <strong>data </strong>folder there are 5 txt files corresponding to each table. You will use these tables when you are inserting data. Data files, interfaces and classes for fulfilling these tasks will be provided as source files. You can assume all information will be complete and consistent, i.e. all necessary data will be inserted before executing a query. You can find detailed description about the usage of the functions in provided source files. Do not forget to define <strong>foreign keys </strong>when you are creating tables. Please do not forget to use DISTINCT keyword when appropriate in your MySQL queries.

<h2>3.1       Creating the database tables (10 pts)</h2>

You will create all the tables according to the schema described above.

You can assume that tables will be created before executing any other database operation. Returns the number of tables that are created successfully.

<h2>3.2       Inserting data into tables (5 pts)</h2>

You will insert data into appropriate tables.

Returns the number of rows inserted successfully.

<h2>3.3        List songs which have the highest rating (5 pts)</h2>

List the artistName, songName, genre and rating of the songs which have the highest rating. (In tab delimited) Order the results by artistName in ascending order.

<strong>3.4         Find the most recent album of given artist (5 pts)</strong>

Return the title, releaseDate and rating of an album of an artist whose name is given.(In tab delimited)

<h2>3.5          List songs that are listened by both users whose usernames are given (10 pts)</h2>

List the artistName, songName, genre and rating of the songs that are listened by both users whose usernames are given. (In tab delimited)

Order by rating in descending order.

<h2>3.6 List artists and number of times his/her songs have been listened by the given user (10 pts)</h2>

List the artistName and number of times his/her songs have been listened by the given user. (In tab delimited) Order by artistName in ascending order.

<h2>3.7          List users who have listened all songs of a given artist (10 pts)</h2>

List the userID and userName, email and password of users who have listened all songs of an artist whose name is given. (In tab delimited)

Order by userID in ascending order.

<h2>3.8 List users and number of songs listened by this user such that none of these songs are listened by any other user (10 pts)</h2>

List the userID, userName and number of songs listened by this user such that none of these songs are listened by any other user. (In tab delimited)

Order by userID in ascending order.

<h2>3.9    List artists who have sung pop music at least once and whose average rating of all songs is greater than the given rating (10 pts)</h2>

List the artistID and artistName of artists who have sung pop music at least once and whose average rating of all songs is greater than the given rating. (In tab delimited) Order by artistID in ascending order.

<h2>3.10 Retrieve songs with the lowest rating in pop category, in case of more than one song exist, retrieve the least listened ones (10 pts)</h2>

Retrieve the song with the lowest rating in pop category. If there exists multiple songs that hold this condition, retrieve the ones that are listened the least number of times.

Return the songID, songName, rating, genre, artistID and albumID of these songs. (In tab delimited) Order by songID in ascending order.

<h2>3.11 Multiply rating of the albums by 1.5 whose release dates are after for a given date (5 pts)</h2>

Update the rating of the albums by multiplying 1.5 whose release dates are after for a given date. Return the number of rows affected.

<h2>3.12         Delete the song for the given song name (5 pts)</h2>

Delete the song for the given song name.

Return the songID, songName, rating, genre, artistID and albumID of these songs. (In tab delimited)

<h2>3.13       Dropping the database tables (5 pts)</h2>

You will drop all the tables (if they exist).

Returns the number of tables that are dropped successfully.

<h1>4       Regulations</h1>

<ol>

 <li>Programming Language: Java.</li>

 <li>Database: An account on the MySQL server on my office machine will be created for each of you and an e-mail including credentials and connection configuration will be sent to your ceng mail. You must use JDBC driver to connect to the database. Your final submission must connect to the MySQL server on my office machine. So, make sure that the connection information is correct before submitting your homework.</li>

 <li>Attachments: Necessary source files and JDBC driver is provided.</li>

 <li>Input: All strings will be case-sensitive and they will not include any non-English characters.</li>

 <li>Late Submission: Late submission policy is stated in the course syllabus.</li>

 <li>Cheating: We have zero tolerance policy for cheating. People involved in cheating will be punished according to the university regulations.</li>

 <li>Newsgroup: You must follow the newsgroup (news.ceng.metu.edu.tr) for discussions and possible updates on a daily basis.</li>

 <li>Evaluation: It is GUARANTEED that input files are correctly formatted and sample data will be given to you. There will be no surprises about the data, similar (and larger) data will be used while evaluating homeworks. Your program will be evaluated automatically using ”black-box” technique so make sure to obey the specifications. Please, be noticed that you have to accomplish tasks only within your sql queries not with any other Java programming facilities .</li>

</ol>

<h1>5      Submission</h1>

Submission will be done via COW. Create a compressed file named ceng.tar.gz that contains MUSICDB class and all other classes, created by you. You will not submit interface and class files provided by me. So, be sure you do not modify them during implementation. Because evaluation will be held with unmodified versions of them. The compressed file should contain a directory tree same as the package tree. That is, you should compress the directory named ’ceng’ which contains a directory named ’ceng351’ which contains a directory named ’musicdb’ which contains your source files.

musicdb

MUSICDB.java

AnotherClassIfYouNeed1.java

AnotherClassIfYouNeed2.java .. …

AnotherClassIfYouNeedN.java

<h1>6       Useful Links</h1>

<ul>

 <li>Java Documentation:</li>

</ul>

http://docs.oracle.com/javase/tutorial/java/index.html

<ul>

 <li>MySQL Reference Manual:</li>

</ul>

http://dev.mysql.com/doc/refman/8.0/en/

<ul>

 <li>Basic MySQL Tutorial:</li>

</ul>

<blockquote class="wp-embedded-content" data-secret="CAO8UctPWQ">

 <a href="https://www.mysqltutorial.org/basic-mysql-tutorial.aspx">Basic MySQL Tutorial</a>

</blockquote>

<iframe sandbox="allow-scripts" security="restricted" style="position: absolute; clip: rect(1px, 1px, 1px, 1px);" title="“Basic MySQL Tutorial” — MySQL Tutorial" data-secret="CAO8UctPWQ" width="600" height="338" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" data-src="https://www.mysqltutorial.org/basic-mysql-tutorial.aspx/embed/#?secret=CAO8UctPWQ" class="wp-embedded-content lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw=="></iframe>