create table Participant
( Participant_id number(20) Primary key , 
  user_name varchar2(30) NOT NULL ,
  Password varchar2(30) NOT NULL
)  ;
  
  Create table Conference
  (
  Conference_id number (20) primary key  , 
  Description   long not null  ,
  start_date    DATE  not null , 
  end_date date not null ) ;
  
  create table Participant_Conference
  (
   Participant_id number(20) not NULL,
   Conference_id  number (20) not null,
   Constraint FK_Participant_id FOREIGN KEY (Participant_id) REFERENCES Participant(Participant_id) , 
    Constraint FK_Conference_id FOREIGN KEY (Conference_id) REFERENCES Conference(Conference_id) 
  );

  create table topics 
  (
   Conference_id  number (20) not null,
   Num number(20) not null , 
  title varchar2(4000) not null  ,
  Constraint FK_topic_conference FOREIGN KEY (Conference_id) REFERENCES Conference(Conference_id) 
  );

create table post 
(
post_id number(20) primary key , 
title  varchar2(4000) not null  ,
Post_content long not null , 
post_date Date not null  
);

create table Author 
(
Author_id number (20) primary key , 
Age number(4) not null , 
sex varchar2(1) not null , 
user_name varchar2(30) not null , 
password varchar2(30) not null , 
email varchar2(100) not null 
);

create table Publishing 
(
   Conference_id  number (20) not null,
   Author_id number (20) not null  , 
  post_id number(20) NOT NULL ,
  Constraint FK_Conf_id FOREIGN KEY (Conference_id) REFERENCES Conference(Conference_id)  , 
  Constraint FK_Author_id FOREIGN KEY (Author_id) REFERENCES Author(Author_id)  ,   
  Constraint FK_post_id FOREIGN KEY (post_id) REFERENCES post(post_id)  
) ;

create table speaker 
(
speaker_id number(20) primary key , 
company varchar2(200) not null , 
Age number(4) not null , 
sex varchar2(1) not null , 
user_name varchar2(30) not null , 
password varchar2(30) not null , 
email varchar2(100) not null 
) ;

create table conference_has_speaker
(
speaker_id number(20) not null, 
Conference_id  number (20) not null,
Constraint FK_Confe_id FOREIGN KEY (Conference_id) REFERENCES Conference(Conference_id)  , 
constraint FK_speaker_id foreign key (speaker_id) references speaker(speaker_id)
) ;

--drop table conference_has_speaker ;
--drop table speaker ;
--drop table Publishing ;
--drop table Author  ;
--drop table topics  ;
--drop table Participant_Conference;
--drop table  Conference ;
--drop table post  ;


-- author table 
-- Insert the first row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (1, 35, 'M', 'John Smith', 'password1', 'john.smith@gmail.com');

-- Insert the second row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (2, 28, 'F', 'Jane Doe', 'password2', 'jane.doe@outlook.com');

-- Insert the third row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (3, 45, 'M', 'Bob Johnson', 'password3', 'bob.johnson@hotmail.com');

-- Insert the fourth row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (4, 32, 'F', 'Alice Williams', 'password4', 'alice.williams@yahoo.com');

-- Insert the fifth row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (5, 38, 'M', 'Mike Thompson', 'password5', 'mike.thompson@gmail.com');

-- Insert the sixth row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (6, 41, 'F', 'Sara Brown', 'password6', 'sara.brown@outlook.com');

-- Insert the seventh row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (7, 29, 'M', 'Chris Davis', 'password7', 'chris.davis@aol.com');

-- Insert the eighth row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (8, 40, 'F', 'Emma Rodriguez', 'password8', 'emma.rodriguez@icloud.com');

-- Insert the ninth row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (9, 36, 'M', 'William Jackson', 'password9', 'william.jackson@gmail.com');

-- Insert the tenth row into the Author table
INSERT INTO Author (author_id, age, sex, user_name, password, email)
VALUES (10, 31, 'F', 'Ashley Taylor', 'password10', 'ashley.taylor@outlook.com');
--------------------------------------------------------------------------------------
-- conference table 
INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (1, 'International Conference on Computer Science', TO_DATE('01-01-22', 'dd-mm-yy'), TO_DATE('05-01-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (2, 'International Conference on Artificial Intelligence', TO_DATE('15-02-22', 'dd-mm-yy'), TO_DATE('20-02-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (3, 'International Conference on Data Science', TO_DATE('01-03-22', 'dd-mm-yy'), TO_DATE('05-03-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (4, 'International Conference on Machine Learning', TO_DATE('01-04-22', 'dd-mm-yy'), TO_DATE('05-04-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (5, 'International Conference on Robotics', TO_DATE('01-05-22', 'dd-mm-yy'), TO_DATE('05-05-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (6, 'International Conference on Cybersecurity', TO_DATE('01-06-22', 'dd-mm-yy'), TO_DATE('05-06-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (7, 'International Conference on Human-Computer Interaction', TO_DATE('01-07-22', 'dd-mm-yy'), TO_DATE('05-07-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (8, 'International Conference on Software Engineering', TO_DATE('01-08-22', 'dd-mm-yy'), TO_DATE('05-08-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (9, 'International Conference on Computer Graphics', TO_DATE('01-09-22', 'dd-mm-yy'), TO_DATE('05-09-22', 'dd-mm-yy'));

INSERT INTO conference (conference_id, description, start_date, end_date)
VALUES (10, 'International Conference on Computer Networks', TO_DATE('01-10-22', 'dd-mm-yy'), TO_DATE('05-10-22', 'dd-mm-yy'));


----------------------------------------------------------------------------------------------------------------------------------------
-- post table 
INSERT INTO post (post_id, title, post_content, post_date)
VALUES (1, 'The Impact of COVID-19 on Mental Health', 'In this paper, we explore the ways in which the COVID-19 pandemic has impacted mental health, including increased rates of anxiety, depression, and other mental health conditions. We also discuss some of the potential long-term effects of the pandemic on mental health and the importance of addressing these issues.', to_date('01-01-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (2, 'Exploring the Benefits of Plant-Based Diets', 'This paper examines the potential health benefits of plant-based diets, including improved cardiovascular health, reduced risk of certain cancers, and weight management. We also discuss the environmental and ethical considerations of plant-based diets and the role they may play in sustainable food systems.', to_date('01-02-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (3, 'The Future of Renewable Energy: Opportunities and Challenges', 'In this paper, we explore the current state and future prospects of renewable energy sources, including solar, wind, and hydroelectric power. We discuss the potential for these technologies to play a larger role in meeting global energy needs and the challenges that must be overcome in order to achieve this goal.', to_date('01-03-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (4, 'Understanding the Role of Social Media in Political Discourse', 'This paper investigates the ways in which social media platforms have influenced political discourse, including the spread of misinformation, the amplification of extremist views, and the erosion of traditional news sources. We also discuss potential solutions for addressing these issues and promoting more constructive online dialogue.', to_date('01-04-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (5, 'The Impact of Artificial Intelligence on the Workforce', 'In this paper, we examine the ways in which artificial intelligence (AI) is impacting the workforce, including the potential for automation to replace certain jobs and the need for workers to adapt to new technologies. We also discuss the ethical implications of AI and the role of government and industry in shaping its development and deployment.', to_date('01-05-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (6, 'Exploring the Link Between Sleep and Mental Health', 'This paper investigates the relationship between sleep and mental health, including the ways in which sleep disturbance can affect mood, cognition, and overall well-being. We also discuss some of the potential causes of sleep problems and strategies for improving sleep quality.', to_date('01-06-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (7, 'The Role of Education in Promoting Social Justice', 'In this paper, we explore the ways in which education can be used as a tool for promoting social justice and reducing inequality. We discuss the importance of inclusive, equitable education systems and the ways in which education can empower marginalized communities. We also consider the challenges and opportunities for implementing these ideals in practice.', to_date('01-07-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (8, 'Examining the Connection Between Physical Activity and Cognitive Function', 'This paper investigates the link between physical activity and cognitive function, including the ways in which regular exercise can improve brain health and reduce the risk of cognitive decline. We also discuss the potential mechanisms by which physical activity may influence brain function and the role of exercise in maintaining brain health throughout the lifespan.', to_date('01-08-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (9, 'The Role of Technology in Addressing Climate Change', 'In this paper, we examine the ways in which technology can be leveraged to address climate change, including the use of renewable energy sources, energy efficiency measures, and carbon capture technologies. We also discuss the challenges and limitations of these approaches and the need for a holistic, multi-faceted approach to addressing this global crisis.', to_date('01-09-2022', 'dd-mm-yy'));

INSERT INTO post (post_id, title, post_content, post_date)
VALUES (10, 'The Future of Transportation: Trends and Predictions', 'In this paper, we take a look at some of the latest trends and predictions for the future of transportation, including the increasing adoption of electric and autonomous vehicles, the potential for alternative modes of transportation such as hyperloop, and the role of technology in shaping the way we move. We also consider the potential impacts of these trends on the environment, the economy, and society as a whole.', to_date('01-10-2022', 'dd-mm-yy'));
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- publishing table 
INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (1, 1, 1);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (2, 2, 2);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (3, 3, 3);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (4, 4, 4);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (5, 5, 5);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (6, 6, 6);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (7, 7, 7);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (8, 8, 8);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (9, 9, 9);

INSERT INTO publishing (conference_id, author_id, post_id)
VALUES (10, 10, 10);
---------------------------------------------------------------------
-- speaker table 
INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (1, 'Acme Corporation', 35, 'M', 'John Smith', 'password123', 'john.smith@gmail.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (2, 'XYZ Inc.', 29, 'F', 'Jane Doe', 'password456', 'jane.doe@yahoo.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (3, 'ABC Company', 41, 'M', 'Bob Johnson', 'password789', 'bob.johnson@outlook.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (4, 'DefTech', 33, 'F', 'Alice Williams', 'password123', 'alice.williams@gmail.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (5, 'TechCorp', 27, 'M', 'Mike Thompson', 'password456', 'mike.thompson@yahoo.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (6, 'Ghi Company', 38, 'F', 'Sara Johnson', 'password789', 'sara.johnson@outlook.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (7, 'Jkl Inc.', 30, 'M', 'Tom Smith', 'password123', 'tom.smith@gmail.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (8, 'Mno Corporation', 25, 'F', 'Emily Williams', 'password456', 'emily.williams@yahoo.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (9, 'Pqr Company', 39, 'M', 'David Johnson', 'password789', 'david.johnson@outlook.com');

INSERT INTO speaker (speaker_id, company, age, sex, user_name, password, email)
VALUES (10, 'Stu Inc.', 32, 'F', 'Jessica Thompson', 'password789', 'jessica.thompson@outlook.com');

-------------------------------------------------------------------------------------------------------
-- topics table 
INSERT INTO topics (conference_id, num, title)
VALUES (1, 1, 'The Future of Artificial Intelligence');

INSERT INTO topics (conference_id, num, title)
VALUES (2, 2, 'Exploring the Link Between Sleep and Mental Health');

INSERT INTO topics (conference_id, num, title)
VALUES (3, 3, 'The Impact of COVID-19 on Mental Health');

INSERT INTO topics (conference_id, num, title)
VALUES (4, 4, 'The Future of Renewable Energy: Opportunities and Challenges');

INSERT INTO topics (conference_id, num, title)
VALUES (5, 5, 'Understanding the Role of Social Media in Political Discourse');

INSERT INTO topics (conference_id, num, title)
VALUES (6, 6, 'Exploring the Benefits of Plant-Based Diets');

INSERT INTO topics (conference_id, num, title)
VALUES (7, 7, 'The Role of Education in Promoting Social Justice');

INSERT INTO topics (conference_id, num, title)
VALUES (8, 8, 'Examining the Connection Between Physical Activity and Cognitive Function');

INSERT INTO topics (conference_id, num, title)
VALUES (9, 9, 'The Role of Technology in Addressing Climate Change');

INSERT INTO topics (conference_id, num, title)
VALUES (10, 10, 'The Future of Transportation: Trends and Predictions');



-----------------------------------------------------------------------------
-- participant table 
INSERT INTO participant (participant_id, user_name, password)
VALUES (1, 'John Smith', 'password123');

INSERT INTO participant (participant_id, user_name, password)
VALUES (2, 'Jane Doe', 'password456');

INSERT INTO participant (participant_id, user_name, password)
VALUES (3, 'Bob Johnson', 'password789');

INSERT INTO participant (participant_id, user_name, password)
VALUES (4, 'Alice Williams', 'password123');

INSERT INTO participant (participant_id, user_name, password)
VALUES (5, 'Mike Thompson', 'password456');

INSERT INTO participant (participant_id, user_name, password)
VALUES (6, 'Sara Johnson', 'password789');

INSERT INTO participant (participant_id, user_name, password)
VALUES (7, 'Tom Smith', 'password123');

INSERT INTO participant (participant_id, user_name, password)
VALUES (8, 'Emily Williams', 'password456');

INSERT INTO participant (participant_id, user_name, password)
VALUES (9, 'David Johnson', 'password789');

INSERT INTO participant (participant_id, user_name, password)
VALUES (10, 'Jessica Thompson', 'password123');


------------------------------------------------------------
-- conference has speaker 
INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (1, 1);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (2, 2);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (3, 3);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (4, 4);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (5, 5);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (6, 6);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (7, 7);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (8, 8);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (9, 9);

INSERT INTO conference_has_speaker (speaker_id, conference_id)
VALUES (10, 10);


----------------------------------------------------------------
-- participant_conference table 

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (1, 1);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (2, 2);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (3, 3);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (4, 4);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (5, 5);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (6, 6);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (7, 7);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (8, 8);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (9, 9);

INSERT INTO participant_conference (participant_id, conference_id)
VALUES (10, 10);



---------------------------------------------------------------------