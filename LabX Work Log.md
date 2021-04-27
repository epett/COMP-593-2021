# Evan's Lab X Work Log
In this file I will be going over step by step, what I did to make my script work from creating the powershell script, to the python script, to the final project!

## Day 1
Today I started working on my API connection using Python to connect to NASA's Image of the day API. 

### Establishing Connection to API
To start off, I opened up Lab 2 to reference what i needed to make the connection to the NASA API. I also used the response.status portion of the lab to make sure the connection was stable. After i got a positive response of 200 for the API i then went in to add in lines 15-16 to get the JSON response from my NASA API and show what information was in it. Then i used pprint to make the response more organized.

### Saving the Image of The Day
Here is where i was able to get the image of the day from my NASA API. What i first did to get the image to save in my folders was to save the image as an easy to find name. I made the variable `file_location` to be the name of the image. I then made the variable `saving_image` to tell the computer where to save the image of the day using this command, `urllib.request.urlretrieve(IOTD['url'], file_location)` so it would grab the images url and saving it under the name I gave it using the `file_location` variable.

### Retrieving File Size
This was one of the easier parts for me since I only had to use one line of code to get the information I needed. I used `file_size = os.stat('C:\\Users\\IEUSer\\ImageOfTheDay.jpg').st_size` to get the size of the image that was saved. I put this line after the `file_location` and the `saving_image` lines.

### Retireving File Hash
Using some lines of code i found at this site, `https://www.quickprogrammingtips.com/python/how-to-calculate-sha256-hash-of-a-file-in-python.html` I reworked them into my code by getting rid of the search of the file and using the image filename instead and getting rid of the input function then renaming the variable to a more fitting one to put with my code.

### Creating a Database
For creating my database with all the information i have gathered I referred back to lab 3 to see the template I should use for creating said database. I ran into a problem when it came to finishing the last bit of code when it came to creating the table. I was constantly getting a syntax error at the end of the creation portion of the table. I looked back at the template for the table in lab 3 and found out i had just added an extra ',' where there didn't need to be one.

### Getting data from Database
Here I was looking back at lab 3 and used the similar layout for being able to retrieve my data for the image of the day. I ran into a problem with getting the date and time to show up in my information then realized that in order to get the time to work in the first place i had to go up to the beginning of my code and use `from datetime import datetime` in order to use the `datetime.now()` function in my code.

### Viewing information from Database
I ran my code after completing my tables and was able to retirieve all the pieces i needes for my project, I then used the `pprint(mycursor.fetchall())` to split up the information to make it look nicer.

## Day 2
Today I will be working on getting a loop to work in my python script and working on my powershell script

### Making a cache in Python
I wanted to double check I had caching in my python script, turns out i didn't so I referred to `https://realpython.com/lru-cache-python/` to figure out how to cache and I used the code they had made, but made it so that it worked with my code. No errors occured meaning that my whole python script works.

### Making the PowerShell Script
I was stumped looking for how to make the wallpaper change in a script. I have found my saving grace, i found a website that has a way to make the wallpaper change using PowerShell. `https://www.joseespitia.com/2017/09/15/set-wallpaper-powershell-function/` This website gave me the script i needed to change the wallpaper, just had to change the destination of where the image was found. 

### Running Python Script in PowerShell
I believe this is the final step of my code. I used the `Start-Process` command to allow the python script to activate before the PowerShell script runs. It works perfectly now all I need to do is add a line at the bottom to set the wallpaper. Finally, I got the wallpaper to change. I used the command `Set-WallPaper -desktopImage "C:\Users\IEUser\Documents\ImageOfTheDay.jpg"` which goes to the image and sets it to the background.

## Day 3
Today i just ran my script again to make sure it worked. The background changed to a blue screen which means that the file is not a jpg or png which means it still works!

