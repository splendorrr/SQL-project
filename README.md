# SQL-project

# Pregnancy-Tracking System

This is the main read me file which contains all the information about a school project I completed with 2 of my classmates. We created a pregnancy tracking system from scratch.

This readme.md file will act as an information file:

There is doc file attached to the repository which acts as a single file where you can find codes used for this project.


SQL Codes
* How to: create tables, insert into tables, join tables
* How to write queries


CREATE DATABASE IF NOT EXISTS Pregnancy_Tracker;
USE Pregnancy_Tracker;

CREATE TABLE IF NOT EXISTS DOCTOR (
DoctorID INT,            
F_Name VARCHAR(15) NOT NULL,
L_Name VARCHAR(15) NOT NULL,
Age INT NOT NULL,
	CONSTRAINT DOCTOR_pk PRIMARY KEY (DoctorID)
);

INSERT INTO DOCTOR (DoctorID,F_Name,L_Name,Age) VALUES (9001,"Diana","Briggs",53);
INSERT INTO DOCTOR (DoctorID,F_Name,L_Name,Age) VALUES (9002,"Ria","Holcomb",60);
INSERT INTO DOCTOR (DoctorID,F_Name,L_Name,Age) VALUES (9003,"Neil","England",40);
INSERT INTO DOCTOR (DoctorID,F_Name,L_Name,Age) VALUES (9004,"Xavier","Crane",44);
INSERT INTO DOCTOR (DoctorID,F_Name,L_Name,Age) VALUES (9005,"Marcia","Buckner",27);

CREATE TABLE IF NOT EXISTS PATIENT(
PatientID INT AUTO_INCREMENT,
First_Name VARCHAR(15) NOT NULL,
Last_Name VARCHAR(15) NOT NULL,
	CONSTRAINT PATIENT_pk PRIMARY KEY (PatientID)
);

INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1001,"Emma","Carson");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1002,"Lilah","Houston");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1003,"Rosalyn","Hopkins");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1004,"Stacy","Doyle");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1005,"Sharon","Hooper");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1006,"Iris","Swanson");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1007,"Emerald","Velez");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1008,"Yvonne","Donaldson");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1009,"Jada","Chase");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1010,"Kaden","Mason");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1011,"Macey","Norris");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1012,"Robin","Forbes");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1013,"Patience","Cardenas");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1014,"Sopoline","Ball");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1015,"Ella","Houston");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1016,"Wanda","Crane");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1017,"Hanae","Mccoy");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1018,"Dominique","Norris");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1019,"Barbara","Maxwell");
INSERT INTO PATIENT (PatientID,First_Name,Last_Name) VALUES (1020,"Danielle","Wallace");

CREATE TABLE IF NOT EXISTS MEDICATION(
MedID INT,
Med_Name VARCHAR(20) NOT NULL,
	CONSTRAINT MEDICATION_pk PRIMARY KEY (MedID)
);

INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8001,"Flovent HFA");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8002,"Endocet");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8003,"Meloxicam");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8004,"Venlafaxine HCl ER");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8005,"Lipitor");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8006,"Nexium");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8007,"Furosemide");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8008,"Hydrocodone");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8009,"Prednisone");
INSERT INTO MEDICATION (MedID,Med_Name) VALUES (8010,"Amoxicillin");

CREATE TABLE IF NOT EXISTS APPOINTMENT (
ApptID INT,
Appt_Date DATE NOT NULL,
Appt_Time TIME NOT NULL,
PatientID INT NOT NULL,
DoctorID INT NOT NULL,
Summary TEXT,
	CONSTRAINT APPT_pk PRIMARY KEY (ApptID),
	CONSTRAINT APPT_PatientID_fk FOREIGN KEY (PatientID)
		REFERENCES PATIENT (PatientID),
	CONSTRAINT APPT_DoctorID_fk FOREIGN KEY (DoctorID)
		REFERENCES DOCTOR (DoctorID)
);

INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5001,"19-02-23","10:00",1001,9002,"Fusce dolor quam, elementum at, egestas a, scelerisque sed, sapien. Nunc pulvinar arcu et");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5002,"19-04-29","10:00",1006,9005,"dapibus id, blandit at, nisi. Cum sociis natoque");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5003,"18-04-25","8:00",1003,9004,"per conubia nostra, per inceptos hymenaeos. Mauris ut quam vel sapien");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5004,"19-10-19","4:00",1016,9005,"ut dolor dapibus gravida. Aliquam tincidunt, nunc ac mattis ornare, lectus ante dictum mi, ac");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5005,"17-10-21","4:00",1010,9001,"amet, consectetuer adipiscing elit. Curabitur sed tortor. Integer aliquam adipiscing lacus. Ut");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5006,"18-12-03","4:00",1004,9004,"vel, mauris. Integer sem elit, pharetra ut, pharetra sed, hendrerit");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5007,"18-02-11","2:00",1009,9005,"nec, mollis vitae, posuere at, velit. Cras");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5008,"18-06-15","10:00",1009,9003,"cursus. Nunc mauris elit, dictum eu, eleifend nec, malesuada ut, sem.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5009,"18-03-04","4:00",1001,9001,"diam nunc, ullamcorper eu, euismod ac, fermentum vel, mauris. Integer sem elit, pharetra");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5010,"21-03-06","4:00",1015,9002,"Maecenas malesuada fringilla est. Mauris eu");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5011,"21-01-14","10:00",1017,9004,"ac turpis egestas. Fusce aliquet magna a neque. Nullam ut");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5012,"21-03-27","10:00",1020,9004,"dolor. Fusce feugiat. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aliquam auctor, velit eget");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5013,"18-07-18","10:00",1015,9001,"eu, eleifend nec, malesuada ut, sem. Nulla interdum. Curabitur dictum. Phasellus");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5014,"21-06-16","4:00",1009,9001,"nulla. Integer urna. Vivamus molestie dapibus");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5015,"18-10-02","8:00",1014,9002,"sem molestie sodales. Mauris blandit enim consequat purus. Maecenas");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5016,"18-08-18","4:00",1001,9001,"dolor. Nulla semper tellus id nunc interdum feugiat.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5017,"19-01-23","8:00",1016,9002,"ridiculus mus. Proin vel arcu eu odio tristique pharetra.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5018,"20-03-25","8:00",1005,9004,"neque. Nullam ut nisi a odio semper cursus. Integer mollis.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5019,"21-02-23","10:00",1008,9003,"arcu. Nunc mauris. Morbi non sapien molestie orci tincidunt adipiscing. Mauris molestie pharetra nibh.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5020,"20-12-31","8:00",1009,9003,"Nam interdum enim non nisi. Aenean");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5021,"18-11-12","8:00",1010,9003,"dui. Fusce diam nunc, ullamcorper eu,");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5022,"21-09-08","10:00",1015,9002,"Quisque varius. Nam porttitor scelerisque neque. Nullam nisl.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5023,"17-10-24","4:00",1020,9005,"justo nec ante. Maecenas mi felis,");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5024,"21-02-24","2:00",1010,9002,"ipsum non arcu. Vivamus sit amet risus. Donec egestas. Aliquam nec enim.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5025,"18-03-08","2:00",1004,9004,"consectetuer euismod est arcu ac orci. Ut semper pretium neque. Morbi quis urna. Nunc quis");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5026,"20-08-07","10:00",1014,9005,"nisi sem semper erat, in consectetuer ipsum nunc id enim. Curabitur massa. Vestibulum accumsan");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5027,"19-04-09","8:00",1018,9003,"dictum eleifend, nunc risus varius orci, in consequat enim diam");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5028,"20-06-19","2:00",1016,9001,"sed, hendrerit a, arcu. Sed et libero. Proin mi.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5029,"20-01-06","10:00",1004,9003,"dolor elit, pellentesque a, facilisis non, bibendum sed, est.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5030,"18-01-04","10:00",1002,9001,"sit amet lorem semper auctor.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5031,"18-08-26","4:00",1005,9002,"pulvinar arcu et pede. Nunc sed orci lobortis augue scelerisque mollis. Phasellus libero mauris, aliquam");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5032,"18-09-27","8:00",1003,9004,"mauris a nunc. In at");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5033,"17-11-28","10:00",1003,9003,"molestie pharetra nibh. Aliquam ornare,");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5034,"19-03-25","2:00",1020,9004,"luctus. Curabitur egestas nunc sed libero. Proin");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5035,"17-10-11","4:00",1017,9001,"euismod in, dolor. Fusce feugiat. Lorem ipsum");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5036,"20-01-02","2:00",1016,9003,"in, dolor. Fusce feugiat. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aliquam");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5037,"20-09-10","8:00",1010,9005,"amet massa. Quisque porttitor eros nec tellus. Nunc lectus pede, ultrices");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5038,"19-09-25","4:00",1009,9001,"Aliquam adipiscing lobortis risus. In");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5039,"21-01-09","10:00",1006,9005,"egestas, urna justo faucibus lectus, a sollicitudin orci sem eget massa. Suspendisse eleifend. Cras sed");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5040,"21-08-24","10:00",1005,9004,"magna et ipsum cursus vestibulum.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5041,"19-02-09","8:00",1008,9005,"nulla vulputate dui, nec tempus mauris erat eget ipsum. Suspendisse sagittis.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5042,"21-05-29","4:00",1012,9001,"diam nunc, ullamcorper eu, euismod ac, fermentum vel, mauris. Integer sem elit, pharetra ut, pharetra");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5043,"21-07-08","8:00",1006,9005,"vitae, orci. Phasellus dapibus quam quis diam.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5044,"21-08-30","2:00",1009,9002,"aliquet. Phasellus fermentum convallis ligula. Donec luctus");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5045,"19-10-08","8:00",1005,9004,"Nullam scelerisque neque sed sem egestas blandit. Nam nulla magna, malesuada vel, convallis in, cursus");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5046,"21-07-30","2:00",1019,9001,"ultrices a, auctor non, feugiat nec, diam. Duis");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5047,"21-08-26","4:00",1015,9003,"Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Phasellus");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5048,"18-08-02","10:00",1010,9003,"neque. Nullam nisl. Maecenas malesuada fringilla est. Mauris eu");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5049,"18-07-02","2:00",1014,9002,"lacinia orci, consectetuer euismod est arcu ac orci.");
INSERT INTO APPOINTMENT (ApptID,Appt_Date,Appt_Time,PatientID,DoctorID,Summary) VALUES (5050,"18-05-24","2:00",1007,9002,"ridiculus mus. Proin vel nisl. Quisque fringilla");

CREATE TABLE IF NOT EXISTS PRESCRIPTION (
ApptID INT NOT NULL,
MedID INT NOT NULL,
	CONSTRAINT PRESCRIPTION_pk PRIMARY KEY (ApptID, MedID),
     CONSTRAINT PRESCRIPTION_ApptID_fk FOREIGN KEY (ApptID)
		REFERENCES APPOINTMENT (ApptID),
	CONSTRAINT PRESCRIPTION_MedID_fk FOREIGN KEY (MedID)
		REFERENCES MEDICATION (MedID)
);

INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5030,8003);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5046,8001);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5005,8008);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5024,8008);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5010,8006);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5040,8010);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5048,8006);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5035,8001);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5015,8004);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5005,8004);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5012,8006);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5003,8005);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5006,8005);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5007,8005);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5046,8009);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5044,8006);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5039,8006);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5016,8009);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5014,8010);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5017,8007);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5038,8001);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5035,8007);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5023,8004);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5003,8007);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5017,8002);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5049,8009);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5021,8001);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5031,8001);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5042,8009);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5002,8008);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5016,8008);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5007,8004);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5039,8007);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5027,8002);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5031,8007);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5047,8001);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5035,8002);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5040,8001);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5013,8001);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5014,8002);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5048,8010);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5044,8008);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5046,8004);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5024,8006);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5023,8008);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5002,8002);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5001,8006);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5007,8007);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5024,8009);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5030,8008);
INSERT INTO PRESCRIPTION (ApptID,MedID) VALUES (5011,8001);

CREATE TABLE IF NOT EXISTS CURRENT_PREGNANCY (
C_PatientID INT,
Due_Date DATE NOT NULL,
	CONSTRAINT CURRENT_PREGN_pk PRIMARY KEY (C_PatientID, Due_Date),
     CONSTRAINT CURRENT_CPatientID_fk FOREIGN KEY (C_PatientID)
		REFERENCES PATIENT (PatientID)
);

INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1001,"21-05-28");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1002,"21-06-27");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1004,"20-12-24");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1005,"21-03-14");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1006,"21-02-06");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1007,"20-12-31");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1008,"21-01-08");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1010,"21-03-05");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1011,"21-04-28");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1012,"21-05-20");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1013,"21-07-03");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1014,"21-01-03");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1016,"21-03-18");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1017,"20-12-24");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1018,"21-01-11");
INSERT INTO CURRENT_PREGNANCY (C_PatientID,Due_Date) VALUES (1020,"21-03-21");

CREATE TABLE IF NOT EXISTS PAST_PREGNANCY (
P_PatientID INT,
Delivery_Date DATE NOT NULL,
Delivery_Info TEXT NOT NULL,
	CONSTRAINT PAST_PREGN_pk PRIMARY KEY (P_PatientID, Delivery_Date),
     CONSTRAINT PAST_P_PatientID_fk FOREIGN KEY (P_PatientID)
		REFERENCES PATIENT (PatientID)
);

INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1001,"20-02-08","Ut tincidunt vehicula risus. Nulla eget metus eu erat semper");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1003,"17-09-20","Suspendisse sagittis. Nullam vitae diam. Proin dolor. Nulla semper tellus id nunc interdum feugiat.");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1004,"18-01-11","posuere, enim nisl elementum purus, accumsan interdum");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1005,"19-01-18","condimentum. Donec at arcu. Vestibulum ante ipsum primis");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1007,"20-01-04","Aenean eget metus. In nec orci. Donec nibh. Quisque nonummy ipsum non arcu.");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1008,"20-06-08","aliquet libero. Integer in magna. Phasellus dolor elit, pellentesque a, facilisis");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1009,"18-01-06","leo. Vivamus nibh dolor, nonummy ac, feugiat");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1010,"20-06-22","est. Nunc ullamcorper, velit in aliquet lobortis, nisi nibh lacinia orci, consectetuer euismod est arcu");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1011,"18-12-18","risus varius orci, in consequat enim diam vel arcu. Curabitur ut odio vel est");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1013,"20-04-06","eu, odio. Phasellus at augue id");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1014,"19-04-15","Praesent interdum ligula eu enim. Etiam");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1015,"20-01-19","In at pede. Cras vulputate velit eu sem. Pellentesque");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1016,"19-05-30","sit amet, dapibus id, blandit at, nisi. Cum sociis natoque");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1017,"18-08-06","Curabitur dictum. Phasellus in felis. Nulla tempor augue ac ipsum. Phasellus vitae mauris");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1019,"20-01-23","lacus. Cras interdum. Nunc sollicitudin");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1020,"19-05-21","dapibus gravida. Aliquam tincidunt, nunc ac mattis ornare, lectus ante dictum mi,");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1001,"19-03-09","Nunc sollicitudin Aliquam tincidunt, nunc ac mattis ornare");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1010,"18-04-02","nisi nibh lacinia orci, consectetuer euismod est arcuest. Nunc ullamcorper, velit in aliquet lobortis");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1020,"17-07-25","nunc ac mattis ornare, lectus ante dictum mi,dapibus gravida. Aliquam tincidunt, ");
INSERT INTO PAST_PREGNANCY (P_PatientID,DELIVERY_Date,Delivery_Info) VALUES (1004,"20-04-16","accumsan interdumposuere, enim nisl elementum purus");

# This updates appointment data to remove summary on those with dates > today.#
# This is just to fix data generated for assignment#.
# Safe Mode must be disabled and then reconnect to DBMS in order to run below Update and Delete queries#

UPDATE appointment SET Summary = ' ' WHERE Appt_Date > now();

# Cleans up Data for assignment purpose by removing the prescription data that has assigned meds to future appointments.#

DELETE FROM prescription WHERE ApptID = ANY(SELECT ApptID FROM appointment WHERE Appt_Date > now());



QUERIES:

# Currently pregnant list patient Id and due date
SELECT * FROM current_pregnancy;

# This will list first/last name along with due date by joining
SELECT concat(First_Name,' ',Last_Name) AS 'NAME', Due_Date 
FROM PATIENT P, CURRENT_PREGNANCY C WHERE
P.PatientID = C.C_PatientID;		

# Delivered - Past Pregnancies list Patient ID,  Delivery_Date and a Summary
SELECT * FROM past_pregnancy;

# This will list by name and delivery dates.
SELECT concat(First_Name,' ',Last_Name) AS 'NAME', Delivery_Date 
FROM PATIENT P, PAST_PREGNANCY H WHERE
P.PatientID = H.P_PatientID;

# All Patients
SELECT * FROM patient;

# OR This gives list of every patient incident 
SELECT * FROM PATIENT P, current_pregnancy C, past_pregnancy H 
WHERE P.PatientID = C.C_PatientID 
AND P.PatientID = H.P_PatientID;

# Search a patient by name to view if they are currently pregnant or not.
# Example for patient Sharon Hooper
select concat(First_Name,' ',Last_Name) as 'Fullname'
from patient join current_pregnancy on current_pregnancy.C_PatientID=patient.PatientID
where (concat(First_Name,' ',Last_Name) like '%Sharon%Hooper%'
    or concat(Last_Name,' ',First_Name) like '%Hooper%Sharon%');
#If they appear then they are current pregnancy patients

#This also works...
SELECT concat(First_Name, ' ', Last_Name) AS 'Name', Due_Date
FROM PATIENT P LEFT JOIN CURRENT_PREGNANCY C 
ON P.PatientID = C.C_PatientID   
WHERE concat(First_Name, ' ',Last_Name) = 'Emma Carson';

# Search by doctor name or patient name to see upcoming appointments. 
# You will need two queries for this.
# Patient Name:  Example Robin Forbes
select concat(First_Name,' ',Last_Name) as 'Fullname', appointment.appt_date, appointment.appt_time
from patient join appointment on appointment.PatientID=patient.PatientID
where appt_date>now()
and concat(First_Name,' ',Last_Name) like '%Robin%Forbes%';


# Same as above using aliasing
SELECT concat(First_Name,' ',Last_Name) AS 'Fullname', A.Appt_Date, A.Appt_Time
FROM PATIENT P JOIN APPOINTMENT A ON P.PatientID = A.PatientID
WHERE Appt_Date > now()
AND concat(First_Name,' ',Last_Name) like '%Robin%Forbes%';
 
# Doctor’s Name: Upcoming appointments for doctor Ria
select concat(F_Name,' ',L_Name) as 'Fullname', appointment.appt_date, appointment.appt_time
from doctor join appointment on doctor.DoctorID=appointment.DoctorID
where appt_date>now()
and concat(F_Name,' ',L_Name) like '%Ria%Holcomb%';

# Same as above but uses aliasing and adds patients name to appointment
SELECT concat(F_Name,' ',L_Name) AS 'Doctor', concat(First_Name,' ',Last_Name) 
AS 'Patient', A.Appt_Date, A.Appt_Time
FROM DOCTOR D, PATIENT P, APPOINTMENT A 
WHERE D.DoctorID = A.DoctorID
AND P.PatientID = A.PatientID
AND Appt_Date > now()
AND concat(F_Name,' ',L_Name) like '%Ria%Holcomb%';

# Display a complete record of the patient including the pregnancy/ies with 
# their info, assigned doctor, medications and all appointments.

SELECT concat(First_Name,' ',Last_Name) AS 'Patient', Due_Date, Appt_Date, Appt_Time, Med_Name, 
L_Name AS 'Doctor', Summary AS 'Appt Summary', Delivery_Date AS 'Prior Delivery', Delivery_Info 
FROM APPOINTMENT A LEFT JOIN patient P ON A.PatientID = P.PatientID
LEFT JOIN CURRENT_PREGNANCY C ON A.PatientID = C.C_PatientID
LEFT JOIN PAST_PREGNANCY H ON A.PatientID = H.P_PatientID
LEFT JOIN  DOCTOR D ON A.DoctorID = D.DoctorID
LEFT JOIN PRESCRIPTION S ON A.ApptID = S.ApptID
LEFT JOIN medication M ON M.MedID = S.MedID
ORDER BY P.PatientID, A.Appt_Date DESC;



# Display list of patients assigned to each doctor
SELECT L_Name AS 'Doctor', concat(First_Name,' ', Last_Name) AS 'Patient' 
FROM doctor D, patient P, appointment A 
WHERE D.DoctorID = A.DoctorID
AND P.PatientID = A.PatientID;

# Display pre-delivery appointments by searching a patient’s name and birthdate.
# This gives us a list to pick from current pregnancies... 
SELECT concat(First_Name,' ',Last_Name) AS 'Patient', Due_Date 
FROM PATIENT P, CURRENT_PREGNANCY C WHERE
P.PatientID = C.C_PatientID;

# This displays appts by name before delivery : 'Emma Carson' '2021-05-28'
SELECT concat(First_Name,' ',Last_Name) AS 'Patient', A.Appt_Date, A.Appt_Time, Due_Date
FROM PATIENT P JOIN APPOINTMENT A ON P.PatientID = A.PatientID
JOIN CURRENT_PREGNANCY C ON P.PatientID = C.C_PatientID
WHERE concat(First_Name, ' ',Last_Name) = 'Emma Carson'
AND A.Appt_Date < C.Due_Date
AND C.Due_Date = '2021-05-28';

# Display post-delivery appointments by searching a patient’s name and birthdate.
# This gives us a list to pick from past deliveries...
SELECT concat(First_Name,' ',Last_Name) AS 'Patient', Delivery_Date 
FROM PATIENT P, PAST_PREGNANCY H WHERE
P.PatientID = H.P_PatientID;

# This displays appts by name after delivery : 'Rosalyn Hopkins' '2017-09-20'
SELECT concat(First_Name,' ',Last_Name) AS 'Patient', A.Appt_Date, A.Appt_Time, Delivery_Date
FROM PATIENT P JOIN APPOINTMENT A ON P.PatientID = A.PatientID
JOIN PAST_PREGNANCY H ON P.PatientID = H.P_PatientID 
WHERE concat(First_Name, ' ',Last_Name) = 'Rosalyn Hopkins'
AND A.Appt_Date > H.Delivery_Date
AND H.Delivery_Date = '2017-09-20';

# Display the medications prescribed to each patient, the date prescribed and the doctor
# who wrote the prescription. The search will be based on the patient’s name and birthdate.
SELECT concat(First_Name,' ',Last_Name) AS 'Patient', Med_Name, Appt_Date AS 'Date', L_Name AS 'Doctor'  
FROM APPOINTMENT A JOIN patient P ON A.PatientID = P.PatientID
JOIN current_pregnancy C on A.PatientID = C.C_PatientID
JOIN past_pregnancy H ON A.PatientID = H.P_PatientID
JOIN doctor D ON A.DoctorID = D.DoctorID
JOIN prescription S ON A.ApptID = S.ApptID
JOIN medication M ON M.MedID = S.MedID 
WHERE concat(First_Name, ' ',Last_Name) = 'Danielle Wallace'
AND H.Delivery_Date = '2019-05-21'; 

