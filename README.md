# Mongodbtask2

useZenclassprogramme
db.createCollection("users");
db.createCollection("attendance");
db.createCollection("topics");
db.createCollection("tasks");
db.createCollection("company_drives");
db.createCollection("mentors");

db.users.insertMany([
{name:"Ben",codekataProblemsSolved:10},
{name:"Dan",codekataProblemsSolved:20},
{name:"Ed",codekataProblemsSolved:30},
{name:"Max",codekataProblemsSolved:40},
{name:"Frank",codekataProblemsSolved:50},
{name:"Roy",codekataProblemsSolved:10},
{name:"Sam",codekataProblemsSolved:20},
{name:"Tom",codekataProblemsSolved:30},
{name:"Tim",codekataProblemsSolved:40},
{name:"Ace",codekataProblemsSolved:50},
{name:"Beck",codekataProblemsSolved:10},
{name:"Cole",codekataProblemsSolved:20},
{name:"Dean",codekataProblemsSolved:30},
{name:"Fox",codekataProblemsSolved:40},
{name:"Guy",codekataProblemsSolved:50},
{name:"Jay",codekataProblemsSolved:10},
{name:"Kai",codekataProblemsSolved:20},
{name:"Kim",codekataProblemsSolved:30},
{name:"Max",codekataProblemsSolved:40},
{name:"Ari",codekataProblemsSolved:50},
{name:"Cole",codekataProblemsSolved:10},
{name:"Finn",codekataProblemsSolved:20},
{name:"Kai",codekataProblemsSolved:30},
{name:"Leo",codekataProblemsSolved:40},
{name:"Nash",codekataProblemsSolved:50},
{name:"Sage",codekataProblemsSolved:10},
{name:"Skye",codekataProblemsSolved:20},
{name:"Wren",codekataProblemsSolved:30},
{name:"Zane",codekataProblemsSolved:40},
{name:"Alexi",codekataProblemsSolved:50},
{name:"Jamie",codekataProblemsSolved:10},
{name:"Riley",codekataProblemsSolved:20}
]);

db.users.updateMany({name:{$in:["Ben","Dan","Ed","Max","Frank","Roy","Sam","Tom","Tim"]}},{$set:{batch:1}});
db.users.updateMany({name:{$in:["Ace","Beck","Cole","Dean","Fox","Guy","Jay","Kai"]}},{$set:{batch:2}});
db.users.updateMany({name:{$in:["Kim","Max","Ari","Cole","Finn","Kai","Leo","Nash","Sage","Skye","Wren","Zane","Alexi","Jamie","Riley"]}},{$set:{batch:3}});

db.attendance.insertMany([
{name:"Ben",absentDaysCount:1,taskNotSubmitted:"10/16/2020"},
{name:"Dan",absentDaysCount:0,taskNotSubmitted:null},
{name:"Ed",absentDaysCount:0,taskNotSubmitted:null},
{name:"Max",absentDaysCount:0,taskNotSubmitted:null},
{name:"Frank",absentDaysCount:0,taskNotSubmitted:null},
{name:"Roy",absentDaysCount:0,taskNotSubmitted:null},
{name:"Sam",absentDaysCount:0,taskNotSubmitted:null},
{name:"Tom",absentDaysCount:0,taskNotSubmitted:null},
{name:"Tim",absentDaysCount:0,taskNotSubmitted:null},
{name:"Ace",absentDaysCount:0,taskNotSubmitted:null},
{name:"Beck",absentDaysCount:0,taskNotSubmitted:null},
{name:"Cole",absentDaysCount:0,taskNotSubmitted:null},
{name:"Dean",absentDaysCount:0,taskNotSubmitted:null},
{name:"Fox",absentDaysCount:0,taskNotSubmitted:null},
{name:"Guy",absentDaysCount:0,taskNotSubmitted:null},
{name:"Jay",absentDaysCount:0,taskNotSubmitted:null},
{name:"Kai",absentDaysCount:2,taskNotSubmitted:"10/16/2020"},
{name:"Kim",absentDaysCount:0,taskNotSubmitted:null},
{name:"Max",absentDaysCount:0,taskNotSubmitted:null},
{name:"Ari",absentDaysCount:0,taskNotSubmitted:null},
{name:"Cole",absentDaysCount:0,taskNotSubmitted:null},
{name:"Finn",absentDaysCount:0,taskNotSubmitted:null},
{name:"Leo",absentDaysCount:0,taskNotSubmitted:null},
{name:"Nash",absentDaysCount:0,taskNotSubmitted:null},
{name:"Sage",absentDaysCount:0,taskNotSubmitted:null},
{name:"Skye",absentDaysCount:0,taskNotSubmitted:null},
{name:"Wren",absentDaysCount:0,taskNotSubmitted:null},
{name:"Zane",absentDaysCount:0,taskNotSubmitted:null},
{name:"Alexi",absentDaysCount:0,taskNotSubmitted:null},
{name:"Jamie",absentDaysCount:0,taskNotSubmitted:null},
{name:"Riley",absentDaysCount:0,taskNotSubmitted:null},
]);


db.createCollection("Topics")

db.Topics.insertMany([
{date:"15-oct-2020",task:"task1",topic:"Frontend"},
{date:"16-oct-2020",task:"task2",topic:"Backend"},
{date:"21-oct-2020",task:"task3",topic:"Devops"},
{date:"22-oct-2020",task:"task4",topic:"Cloud"}
])

db.createCollection("Tasks")

db.Tasks.insertMany([
{date:"15-oct-2020",task:"task1",topic:"Frontend"},
{date:"16-oct-2020",task:"task2",topic:"Backend"},
{date:"21-oct-2020",task:"task3",topic:"Devops"},
{date:"22-oct-2020",task:"task4",topic:"Cloud"}
])

db.createCollection("Company_drive")
db.Company_drive.insertMany([{ date: "29-oct-2020", location: "Chennai" },{ date: "01-nov-2020", location: "Bangalore" }])

db.createCollection("Mentors")

db.Mentors.insertMany([{ name: "Mentor X", batch: "batch1", usersCount: 17 },{ name: "Mentor Y", batch: "batch2", usersCount: 14 },{ name: "Mentor Z", batch: "batch3", usersCount: 13 }])

1. Find all the topics and tasks which are thought in the month of October

db.Topics.find({date: { $gte: "01-oct-2020", $lte: "31-oct-2020" }}).pretty();
db.Tasks.find({date: { $gte: "01-oct-2020", $lte: "31-oct-2020" }}).pretty();

2. Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020

db.Company_drive.find({date: { $gte: "15-oct-2020", $lte: "31-oct-2020" }}).pretty();

3. Find all the company drives and students who are appeared for the placement.

db.Company_drive.find().pretty();

4. Find the number of problems solved by the user in codekata
db.users.findOne({ name: "Ed" }, { _id: 0, codekataProblemsSolved: 1 });

5. Find all the mentors with who has the mentee's count more than 15
db.Mentors.find({usersCount: { $gt: 15 }}).pretty();

6. Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020

db.attendance.find({date: { $gte: "2020-10-15", $lte: "2020-10-31" },absentDaysCount: { $gt: 0 },taskNotSubmitted: { $gte: "10/15/2020", $lte: "10/31/2020" }}).pretty();


