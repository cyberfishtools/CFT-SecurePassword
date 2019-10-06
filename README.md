
Console Application that takes 3 strings and creates a secure password.
 This will generate a password based on the first name(s), last name and Random ID of a person.

# PasswordGenerator

**PasswordGenerator()** method, by using this you can generate random passwords with uppercase letters, also numbers.
- **generatePassword()** method uses **RNGCryptoServiceProvider class**.

```C#
 var workString = "1207." + firstNames.ToLower() + " " + lastName.ToUpper() + "." + bankID.ToLower() + ".0105";
                var workBytes = System.Text.Encoding.UTF8.GetBytes(workString);
                using (var sha = System.Security.Cryptography.SHA256.Create())
                {
                    // use only a 3rd of the hash for the password
                    var passwordLength = (sha.HashSize / 8) / 3;
                    var hashPart = new byte[passwordLength];
                    System.Array.Copy(sha.ComputeHash(workBytes), 2, hashPart, 0, passwordLength);
                    // remove the dashes
                    return BitConverter.ToString(hashPart).Replace("-", "");
                }
              
```

Using **GeneratePassword class** you can execute the program, simply enter the 3 strings and  program uses SHA 256 to generate password. 

```C# 
Console.WriteLine(Generator.PasswordGenerator(10));
```

#Keywords
Project Sdk="Microsoft.NET.Sdk"
C# , .Net Framework ,netcoreapp2.1, Microsoft Visual Studio.




 ## How to install: 
 1. Download -
  ``` 
  https://github.com/cyberfishtools/CFT-SecurePassword.git
  ```
  2. Open Folder - in Visual Studio
  ```
  Locate to project File : GeneratePassword.csproj
  
  ```
# Donate
Donate generously! [![Support](https://www.buymeacoffee.com/assets/img/custom_images/white_img.png)](https://www.buymeacoffee.com/maheshnama098)
