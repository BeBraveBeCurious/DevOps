# Assignment 3



Problem Statement: 

1. Create an array of random Alphabets or characters and modify the original Alphabets/Characters of array by sorting. Replace the first 5 contents of array with some different Characters/Alphabets.



```powershell
# 8 Random characters
Write-Output "8 Random characters"
$array = @(97..122) | Get-Random -Count 8 | % {[char]$_}
Write-Output $array

#Blank line
Write-Output "`n"

# Sorting the characters
Write-Output "Sorting the characters"
$array = $array | sort
Write-Output $array

# Blank line
Write-Output "`n"

# Replacing the first 5 characters
Write-Output "Replaceing the first 5 characters"
for($i=0; $i -le 4; $i++){
    $array[$i] = Read-Host "Content $i"
}

# Blank line
Write-Output "`n"

# Modified array
Write-Output "Modified array"
Write-Output $array
```

![image-20211231144402166](https://s2.loli.net/2021/12/31/kqgWpymK5is6OYz.png)



2.Write a PowerShell Script to read and validate the user input. Ex: print what is your name? How old are you? What date are you taking this course? Your feedback on the instructor of this course. Good/Bad. Enter your secure password once user read the questions and answer them then print the data type of each variables used in this example.

```powershell
[string] $name = Read-Host "What is your name?"
[validateRange (1,100)][int] $age = Read-Host "How old are you?" 
[Datetime] $date = Read-Host "What date are you taking this course?"
[validateset("Good", "Bad", "good", "bad", "GOOD", "BAD")] [string] $feedback = Read-Host "Your feedback on the instructor of this course"
$pass = Read-Host "Enter your secure password" -AsSecureString
Write-Output $name.GetType()
Write-Output $age.GetType()
Write-Output $date.GetType()
Write-Output $feedback.GetType()
Write-Output $pass.GetType()

```



![image-20211231142626807](https://s2.loli.net/2021/12/31/fMWsZcrqedDhyit.png)



3.Write a PowerShell method and pass parameters/argument to the method in any order. Ex: Hello World! I am excited to meet you all! My name is (Your Name) I am (Your Age) years of old. My (Your profession) is.



```powershell
function Hello
{
param
(
[string] $name,
[int] $age, 
[string] $profession
)
Write-Output "Hello World! I am excited to meet you all! My name is $name I am $age years of old. I am a $profession."
}

Hello -name "Xiaomei Mi" -age 25 -profession "TA"
```

![image-20211231143249443](https://s2.loli.net/2021/12/31/r2CKcAqfHaix4NQ.png)



4.Write a PowerShell If Else statement that should prompt user to enter user's monthly house/office rent and if the rent is greater than 1400 and less than 1700 print Your rent is high and if your rent is **less than 900 and more than 1400** your rent is affordable.

the corner case 1400



```powershell
[int]$rent=Read-Host "enter your monthly house/office rent:"
if (($rent -gt 1400) -and ($rent -lt 1700))
{
Write-Host "Your rent is High"
}
elseif(($rent -gt 900) -and ($rent -lt 1400)){
Write-Host "Your rent is affordable"
}
else{
Write-Host "Your monthly house/office is not in the correct range"
}
```

![image-20211231141551190](https://s2.loli.net/2021/12/31/Rn4gMrXoVS8AvcO.png)
