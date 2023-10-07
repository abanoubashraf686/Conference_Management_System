# Conference_Management_System
Database SQL forms and reports


There are five entities: participant, conference, speaker, author, and post.

In the participant entity, we store an account which consists of an email, user-name, password, and a unique ID.

In the conference entity, we store topics which consist of a number and a title, dates which consist of a start and an end date, a description, and a unique ID.

In the speaker entity, we store company, age, sex, a unique ID, and an account which consists of an email, user-name, and password.

In the author entity, we store age, sex, a unique ID, and an account which consists of a password, email, and user-name.

In the post entity, we store a title, content, date, and post ID.

Each conference must have one or more speakers, and each speaker must speak at least once in one conference.

Each conference must have more than one participant attending, and each participant can attend more than one conference.

There may be one or more authors who may publish one or more posts in the conference.

All posts must be published by authors within the conference.


![erd](https://github.com/abanoubashraf686/Conference_Management_System/assets/92957180/15eb05ee-da87-4f06-aee7-ebe249575a3b)


![image](https://github.com/abanoubashraf686/Conference_Management_System/assets/92957180/1c792adf-28cb-4d98-9f4e-ba40b88d8e87)
