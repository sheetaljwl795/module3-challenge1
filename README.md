# module3-challenge1
// Assignment Code

<img width="586" alt="image" src="https://user-images.githubusercontent.com/107803903/180934594-dd72fb91-04cb-412d-b767-983314b6650e.png">
var generateBtn = document.querySelector("#generate");
var numberBase = "0123456789"
var specialBase = "@#$%^&*()_+?<>:{}[]"
var upperBase = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
var lowerBase = "abcdefghijklmnopqrstuvwxyz"
var passwordBase = ""

// function to generate passsword

function generatePassword() {
    // ask for lenghth of the password between 8 and 128
    let passwordLength = prompt("Please choose a password length between 8 and 128 characters", "Please enter a digit");
    
    // first if statement for password length validation
        if (!passwordLength)  {
        alert("Please enter password lenght");        
    }  else if (passwordLength < 8 || passwordLength > 128) {
        passwordLength = prompt("Your must enter between 8 and 128")
    } else {
        //confirm whether or not to include lowercase, uppercase, numeric, and/or special characters
        confirmnumberBase = confirm("will your password contain numbers?");
        confirmspecialBase = confirm("will your password contain special charaters?");
        confirmnupperBase = confirm("will your password contain Uppercase letters?");
        confirmlowerBase = confirm("will your password contain Lowercase letters?");
    };

    // for none criteria selected
    if (!confirmnumberBase && !confirmspecialBase && !confirmnupperBase && !confirmlowerBase) {
        passwordBase = alert("You must choose password criteria");
    }
    // for all four crietria selected
    else if (confirmnumberBase && confirmspecialBase && confirmnupperBase && confirmlowerBase) {
        passwordBase = numberBase.concat(specialBase, upperBase, lowerBase);
    }
    // for selection of three critria: special character, numbers and uppercase
    else if (confirmnumberBase && confirmspecialBase && confirmnupperBase) {
        passwordBase = numberBase.concat(specialBase, upperBase);
    }
     // for selection of three criteria: special character, numbers and lowercase
     else if (confirmnumberBase && confirmspecialBase && confirmlowerBase) {
        passwordBase = numberBase.concat(specialBase, lowerBase);
     }
     // for selection of three crietria: special character, uppercase, and lowercase
     else if (confirmspecialBase && confirmlowerBase && confirmupperBase) {
        passwordBase = specialBase.concat(lowerBase, upperBase);
     }
    // for selection of three crietria: numbers, uppercase, and lowercase
    else if (confirmnumberBase && confirmlowerBase && confirmupperBase) {
        passwordBase = numberBase.concat(lowerBase, upperBase);
     }
    
     // for selection of two crietria
     else if (confirmspecialBase && confirmnumberBase) {
        passwordBase = specialBase.concat(numberBase);

    } else if (confirmspecialBase && confirmlowerBase) {
        passwordBase = specialBase.concat(lowerBase);

    } else if (confirmspecialBase && confirmupperBase) {
        passwordBase = specialBase.concat(upperBase);
    }
    else if (confirmlowerBase && confirmnumberBase) {
        passwordBase = lowerBase.concat(numberBase);

    } else if (confirmlowerBase && confirmnupperBase) {
        passwordBase = lowerBase.concat(upperBase);

    } else if (confirmnupperBase && confirmnupperBase) {
        passwordBase = numberBase.concat(upperBase);
    }

    // for selection of one crietria
    else if (confirmspecialBase) {
        passwordBase = specialBase;
    }
    else if (confirmnumberBase) {
        passwordBase = numberBase;
    }
    else if (confirmlowerBase) {
        passwordBase = lowerBase;
    }
    else if (confirmupperBase) {
        passwordBase = upperBase;
    };

   console.log(passwordBase.length);

    let password = ' ';
 
    for (let i = 0; i < passwordLength; i++) {
        let randomNumber = Math.floor(Math.random() * passwordBase.length);
        password += passwordBase.substring(randomNumber,randomNumber + 1);}
      
        return password;
    
        }
               
// returns a string


//Write password to the #password input

function writePassword() {
    var password = generatePassword();
    var passwordText = document.querySelector("#password");
    passwordText.value = password;    
}

// Add event listener to generate button

generateBtn.addEventListener("click", writePassword);
