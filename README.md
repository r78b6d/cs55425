java c
INFOSYS 222 Database Systems (Exam)
SEMESTER TWO, 2022
Data Modelling - DRA
The Data Research Alliance (DRA) wishes to manage its membership using a database. They want their database to capture the following data and enforce the following business rules.
Member
The information to be stored about a member includes a member ID, first name, last name, address, email and mobile. Membership is usually recommended by another member. It is necessary to keep a record of which existing member recommends which new member.
Membership
There are four types of membership: student, associate, fellow and elite. The information to be stored about member type includes member type number and member type name. Over time the member type of a member could change. As such, it is necessary to store the details about when a member joins the DRA, which member type they start as; when they change their member type; and when they give up their membership and leave the DRA. The detail as to how a member upgrades the member type, say, from an associate to a fellow, or from a fellow to an elite, is outside the scope of this database.
In order to retain an upgraded member type with DRA, a member must accumulate a certain number of professional training points during a calendar year. These points are awarded for attending events organised by the DRA. The minimum number of points that a member must accumulate depends upon the member type. For example, student members and associate members do not have to accumulate any points; a fellow member must accumulate at least ten points; and an elite member must accumulate twenty points. The number of points to be accumulated per member type may change over time, but they will only change at the beginning of a calendar year. If insufficient points are accumulated at the one-year mark of a membership, the member will be downgraded to a lower membership type.
Event
The details to be stored about an event includes event ID, event name, event description, date of the event, start time and duration, and the number of points per member type awarded for attendance. One event may incorporate other events. For example, the Data Enthusiasts Conference which often lasts for four days will be recorded as one event, but it is made up of a number of smaller events.
Draw a logical ERD in crow’s foot notation for the case described above with stated design decisions and assumptions.
Please note: all important design decisions and / or assumptions made (3-5) must be clearly listed. No marks will be given if there is no design decision or assumption. All entity sets, attributes including primary and foreign keys, and relationships including cardinalities must be shown as appropriate. Following database design principles, the ERD should not contain redundant entity sets, relationships or attributes.
Normalisation - Purchase Order
Derive a set of relations in third normal form. (3NF) using the given document above. Show each step of normalisation clearly. Indicate primary keys and foreign keys with labels or solid/dashed lines. You must state your design decisions and / or assumptions made (1-2) for the normalisation.
No marks will be given if there is no design decision or assumption.
Lotto Database Schema
CREATE TABLE Combination
(combinationNo INTEGER PRIMARY KEY NOT NULL,
N1 INTEGER NOT NULL,
N2 INTEGER NOT NULL,
N3 INTEGER NOT NULL,
N4 INTEGER NOT NULL,
N5 INTEGER NOT NULL,
N6 INTEGER NOT NULL,
UNIQUE (N1, N2, N3, N4, N5, N6)
);
CREATE TABLE Draw
(drawNo INTEGER PRIMARY KEY NOT NULL,
drawDate DATE NOT NULL,
drawName TEXT,
winCombinationNo INTEGER,
FOREIGN KEY (w代 写INFOSYS 222 Database Systems (Exam) SEMESTER TWO, 2022SQL
代做程序编程语言inCombinationNo) REFERENCES Combination (combinationNo)
);
CREATE TABLE Ticket
(ticketNo INTEGER PRIMARY KEY NOT NULL,
drawNo INTEGER NOT NULL,
soldAt TEXT NOT NULL,
FOREIGN KEY (drawNo) REFERENCES Draw (drawNo)
);
CREATE TABLE Line
(ticketNo INTEGER NOT NULL,
lineID TEXT NOT NULL,
combinationNo INTEGER NOT NULL,
PRIMARY KEY (ticketNo, lineID),
FOREIGN KEY (ticketNo) REFERENCES Ticket (ticketNo),
FOREIGN KEY (combinationNo) REFERENCES Combination (combinationNo)
);
(a) SQL - Special Draw
Answer this question by referring to the Lotto Database Schema.
Write a single SQL statement to project three columns: drawNo, drawDate and drawName from the Draw table. Show only the rows where drawName ends with the word "special" regardless of the case used. You must provide a comment about your SQL statement in order to get any mark.
(b) SQL - Winning Numbers
Answer this question by referring to the Lotto Database Schema.
Write a single SQL statement without using a subquery to project six columns to show the six winning numbers of the latest draw of the lotto game. You must provide a comment about your SQL statement in order to get any mark.
(c) SQL - A New Line
Answer this question by referring to the Lotto Database Schema.
Write a single SQL statement to insert a new row containing the following information to the Line table. The ticketNo is 123454321, the lineID is 'A' and the six numbers are 2, 3, 11, 15, 23 and 25 respectively. You must provide a comment about your SQL statement in order to get any mark.
(d) SQL - Performance
Answer this question by referring to the Lotto Database Schema.
Write a single SQL statement to create a database artefact that could help improve the performance of point and range queries running against the Ticket table associated with soldAt. You must provide a comment about your SQL statement in order to get any mark.
(e) SQL - Winning
Answer this question by referring to the Lotto Database Schema.
Write a single SQL statement to create a view called Winning. It should have two columns: drawNo and number of tickets having the winning numbers. The view only includes draws within one year of time. The output of the view should be ordered with the latest draw on the top. You must provide a comment about your SQL statement in order to get any mark.
(f) SQL - Online vs Store
Answer this question by referring to the Lotto Database Schema.
Write a single SQL statement to project exactly two columns and two rows. The first column is soldAt and the second column is the number of tickets. The first and second rows correspond to the total number of tickets sold online and from physical stores. The column soldAt in the Draw table contains string values' Online' for tickets sold online; and values like 'Sylvia Park PaperPlus' or 'Parnell Road Hilltop Superette' for tickets sold at different physical stores. You must provide a comment about your SQL statement in order to get any mark.
The sales model captures a portion of the OLTP systems of Best Buy in the US. The company is interested in building an OLAP system to analyse their sales figures from the last ten years. The database has ten years' worth of daily data from 200 stores and around 500 products sold every day.
Data Warehouse - Star Schema
Draw a star schema of the data warehouse based on the information given. You must provide all relevant design decisions and / or assumptions made (2-3) as part of the answer for each feature defined in the star schema. No marks will be given if there is no design decision or assumption.





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
