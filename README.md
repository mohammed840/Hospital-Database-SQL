# Hospital-Database-SQL
![image](https://user-images.githubusercontent.com/71986409/179974564-b038eb2e-a7d0-4238-90fc-d2323a31a7dd.png)
Tables-

Position- Has basic position information which includes the following attributes: a. idposition – INT (PRIMARY KEY) b. position_type – VARCHAR

Hospital- Has basic position Hospital which includes the following attributes: a. idhospital – INT (PRIMARY KEY) b. hospitalName – VARCHAR c. address – VARCHAR d. telephoneNumber – DECIMAL

Skills-includes a variety of talents and is related to position and candidate tables on a many-to-many basis. In other words, an applicant may possess a variety of talents, and several candidates may possess the same skill.Foe example Skills: Teamwork, Nursing skills. position: A Nurse job might require having both Teamwork and Nursing skills. candidate: A candidate applying for the above position might have both Teamwork, nursing skills in addition to many more skills This table has the following attributes: a. idskills – int (PRIMARY KEY) b. skillname – VARCHAR

candidate-Has basic candidate information which includes the following attributes: a. idcandidate – INT (PRIMARY KEY) b. firstname – VARCHAR c. surname – VARCHAR d. address – VARCHAR e. telephone_number – DECIMAL

interview-Position is the strong entity that this weak thing should be compared against. Because there won't be an interview if a position doesn't exist. With the use of this, the hospital was able to request numerous interviews for a given post. In this case, the interviewdate and idposition serve as the main keys as stated below: Interview date:  DATE (PRIMARY KEY) c. idposition – INT (PRIMARY KEY) – FOREIGN KEY referencing idposition in the position table.


invite-A potential employee may or may not hire a candidate who has been invited to an interview. The invitation table contains this data. This table, which has its own characteristic called ishired, is a link between the interview and the candidate tables. In order to create this new table, the primary keys from the candidate and interview tables were combined, as seen below: a. candidatesid – INT (PRIMARY KEY) – FOREIGN KEY referencing idcandidate in the candidate table. b. Interviewforposition – INT (PRIMARY KEY) – FOREIGN KEY referencing idposition in the interview table. c. Dateofinterview – DATE (PRIMARY KEY) – FOREIGN KEY referencing interviewdate in the interview table. d. Ishired – VARCHAR – VALUES: YES or NO.


positionofferedbyhospital-This table was produced as a result of a position-to-hospital-table interaction on a large scale. i.e., various hospitals may offer a post, and various hospitals may offer various positions. Case in point: Many hospitals, including Tallaght Hospital, Dundrum Hospital, and others, provide nursing positions: A hospital may have a variety of job openings. As a result, the positionofferedbyhospital table's primary key is formed by the primary keys of these two tables, as illustrated below.a. positionsid – INT (PRIMARY KEY) – FOREIGN KEY referencing idposition in the position table. b. hospitalsid – INT (PRIMARY KEY) – FOREIGN KEY referencing idhospital in the hospital table.


positionskills-The skills and position tables were linked several times over to get this table. Therefore, as illustrated below, the primary key of the position skills table is formed by the main keys of these two tables combined:a. positionid – INT (PRIMARY KEY) – FOREIGN KEY referencing idposition in the position table. b. Skillsid – INT (PRIMARY KEY) – FOREIGN KEY referencing idskills in the skills table


candidateskills-This table represents the outcomes of a many-to-many link between the applicant and skill tables. Therefore, as illustrated below, the primary key of the candidate skills table is formed by the primary keys of these tables:a. candidateid – INT (PRIMARY KEY) – FOREIGN KEY referencing idcandidate in the candidate table. b. Skillid – INT (PRIMARY KEY) – FOREIGN KEY referencing idskills in the skills table.
