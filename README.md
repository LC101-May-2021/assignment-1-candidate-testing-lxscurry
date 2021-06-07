const input = require('readline-sync');

 let candidateName = "";
  candidateName = input.question ("Enter your name? ") ;
 console.log ("Hello, " + candidateName + "!" );
console.log()

let question1 = "1) Who was the first American woman in space? ";

let question2 = "2) True or false: 5 kilometer = 5000 meters? ";
let question3 = "3) (5 + 3)/2 * 10 = ? ";
let question4 = "4) Given the array [8, 'Orbit', 'Trajectory', '45'], what entry is at index 2? ";
let question5 = "5) What is the minimum crew size for the ISS? ";
 
let questionsArr = [ question1, question2,question3, question4, question5];
//console.log (questionsArr);


let correctAnswer1 = "Sally Ride";
let correctAnswer2 = "True";
let correctAnswer3 ="40";
let correctAnswer4 = "Trajectory";
let correctAnswer5 = "3";

let correctAnswerArr = [correctAnswer1 ,correctAnswer2,correctAnswer3,correctAnswer4, 
 correctAnswer5];
let candidateAnswer = ["", "", "", "", ""];

 for (let i = 0; i < questionsArr.length; i++) {
candidateAnswer[i] = input.question (questionsArr[i]);

console.log (`Your answer: ${candidateAnswer[i]}`);
console.log (`Correct ansewer: ${ correctAnswerArr[i]}`);
console.log();
  }

 let grade = ["", "", "", "", ""];
 
for (let i = 0; i < candidateAnswer.length; i++) 
{
if (candidateAnswer[i] === correctAnswerArr[i]) {
  grade[i] = 1;}
else if ( candidateAnswer[i] === "sally ride" || candidateAnswer[i] === "true" || candidateAnswer[i] === "trajectory" )
 { grade[i] = 1;
 }
 else {
   grade[i] = 0};
};
//console.log (grade);
let sum = grade[0] + grade[1] + grade[2] + grade[3] + grade[4];
 console.log (`>>> Overall Grade: ${sum/candidateAnswer.length*100} % (${sum} of ${candidateAnswer.length} responses correct) <<<`)

if (sum < 4)  {
console.log (">>> Status: FAILED <<<")
}
else {console.log (">>> Status: PASSED <<<")};