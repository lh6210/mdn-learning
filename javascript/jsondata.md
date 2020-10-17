<<<<<<< HEAD

MDN: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Test_your_skills:_JSON
Learn web developmentSee JavaScript — Dynamic client-side scriptingSee Introducing JavaScript objectsTest your skills: JSON
Test your skills: JSON

=======
>>>>>>> 00035eb75794138249251428233c3db29e1f410a
const section = document.querySelector('section');

let para1 = document.createElement('p');
let para2 = document.createElement('p');

let motherInfo = 'The mother cats are called ';
let kittenInfo;

fetch('sample.json')
.then(response => response.text())
.then(text => displayCatInfo(text))

function displayCatInfo(catString) {
  let total = 0;
  let male = 0;

  // Add your code here
      const catJson = JSON.parse(catString);

      for (let i = 0; i < catJson.length; i++)
      {
        // mother cat info
        if (i != catJson.length - 1) 
        {
          motherInfo = motherInfo + catJson[i].name + ", "; 
        } else {
          motherInfo = motherInfo + " and " + catJson[i].name + ".";
        }

        // for every mother-kitten record, record the total number of kittens and the number of male kittens
        const kts = catJson[i].kittens;
        // total number of kittens
        total += kts.length;
        // number of male kittens
        for (let j = 0; j < kts.length; j++)
        {
          if (kts[j].gender === "m") {male += 1;}
        } 
      }
       
            kittenInfo = "total: " + total + " male: " + male + " female: " + (total-male);
   
      //kittenInfo = {"total": total, "male": male, "female": total - male};



// Don't edit the code below here!

  para1.textContent = motherInfo;
  para2.textContent = kittenInfo;
}

section.appendChild(para1);
section.appendChild(para2);
    
