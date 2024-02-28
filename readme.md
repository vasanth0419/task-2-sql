#### Design DB model for Guvi Zen class...


#### sql queries:


```

CREATE TABLE mentors (
    mentor_id INT PRIMARY KEY,
    mentor_name VARCHAR(50)
);

CREATE TABLE batches (
    batch_id INT PRIMARY KEY,
    batch_name VARCHAR(200)
);

CREATE TABLE course (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(200)
);


CREATE TABLE learners (
    learner_id INT PRIMARY KEY,
    learner_name VARCHAR(50),
    mentor_id INT,
    batch_id INT,
    course_id INT,
   
    FOREIGN KEY (mentor_id) REFERENCES mentors(mentor_id),
    FOREIGN KEY (batch_id) REFERENCES batches(batch_id),
    FOREIGN KEY (course_id) REFERENCES course(course_id)
);

CREATE TABLE marks (
    mark_id INT PRIMARY KEY,
    learner_id INT,
    marks INT,
    FOREIGN KEY (learner_id) REFERENCES learners(learner_id)
);

CREATE TABLE tasks (
    task_id INT PRIMARY KEY,
    task_name VARCHAR(200),
    course_id INT,
    learner_id INT,
    mark_id INT,
    FOREIGN KEY (course_id) REFERENCES course(course_id),
    FOREIGN KEY (learner_id) REFERENCES learners(learner_id),
    FOREIGN KEY (mark_id) REFERENCES marks(mark_id)
);


DESCRIBE learners;
DESCRIBE tasks;
DESCRIBE mentors;
DESCRIBE course;
DESCRIBE marks;
DESCRIBE batches;


```


#### Download my pdf file to view my day-2 task with diagram...