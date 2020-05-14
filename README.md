<h1>Shell-data-processing</h1>

While creating this project , the first thing which I did was I have created a folder called 44517. The reason why I have named it as 44517 is because the course currently we are taking is Big-Data and it has the course number as 44517, so it would be easy for our reference.

<h2> Creation of Project </h2>
We have started a new project in that folder by opening that folder using the following steps:

- I have opened the folder by right clicking on the folder and choosing "Open PowerShell window here as administrator" option.

- After opening the folder, I have created a subfolder named as "shell-data-processing" using the command:
```
"mkdir shell-data-processing" - this command is used for creating the directory called shell-data-processing in the Powershell.
```
- In the next step, I have changed the directory(44517) into my subfolder(shell-data-processing) using the command:
```
"cd shell-data-processing" - this command is used for changing the current directory into the directory named as shell-data-processing in the Powershell.
```

- Later, I have created a new item called "README.md" in my subfolder using the command as:
```
"ni README.md" - this command is used for creating a newitem called README.md in my sub folder.
```

- I have used the same command as of the above to create another new item in my subfolder called ".gitignore", for this I have used the command as :
```
"ni .gitignore"
```

- In orderr to verify the items in the list and to view all the items in the list , I have used the command as:
```
"ls"
```

NOTE: For all the above commands we should not place them in the double quotes in Powershell, if we do it shows the error messages.

<h2> Curl Commands </h2>
After completing the above process, I have started working with retrieval of text with curl, in order to perform this action , I have followed the below steps:

- I have choosed the topic as "TikTok" and I have opened that in the wikipedia website. I have got a URL for the topic "TikTok" as "https://en.wikipedia.org/wiki/TikTok" and I have copied the URL.

- I have used curl to return the page text, the command which I have used is 
```
curl "https://en.wikipedia.org/wiki/TikTok" - This is the command used for returning the page text and in place of "URL" we need to paste the URL which we have copied in the above step and paste in between the quotes.
```

NOTE: While performing this step I have encountered an exception called "WebCmdletWebResponseException" and inorder to overcome that error, I have used the command as "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12" and then followed the above step, and this worked.

- Later, I have used curl to return the page text and to copy the output to a file , the command which I used is:
```
curl "https://en.wikipedia.org/wiki/TikTok" -O data.txt - this command is used for creatig a text file named as data.txt and copies the text into that file.
```

- In order to exit from the Powershell , I have used the command as:
```
"ALT+SPACE+C" - Used for exiting from the powershell.
```

<h2> Bash Commands </h2>

I have used some of the bash commands to process the text, the commands which I have used are as following:

- In order to transform each space into a return character, I have used the command as
```
tr ' ' '\12' < data.txt
```

- In the second step , I tried to sort the output and also to send the results of one command as input into another command, I have used 
```
tr ' ' '\12' < data.txt | sort
```

- In the third step, I have sorted based on the count , in order to perform that I used the command as 
```
tr ' ' '\12' < data.txt | sort | uniq -c
```

- In the fourth step , in order to pipe the reduced output to sort with -nr flag I used the command as
```
tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr
```

- Later, in order to redirect the result or the output to the result.txt file, I have used the command as
```
tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr > result.txt
```
