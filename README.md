# module3-challenge1
// Assignment Code

var generateBtn = document.querySelector("#generate");

// genratepassword function

function generatePassword() {
    const chars = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz@#$%^&*()_+?<>:{}[]''";
    let passwordlength = 8;
    let password = ' ';
    for (let i = 0; i < passwordlength; i++) {
        let randomNumber = Math.floor(Math.random() * chars.length);
        password += chars.substring(randomNumber,randomNumber + 1);
        }
        return password;
}

//Write password to the #password input

function writePassword() {
    var password = generatePassword();
    var passwordText = document.querySelector("#password");
    passwordText.value = password;    
}

// Add event listener to generate button

generateBtn.addEventListener("click", writePassword);

