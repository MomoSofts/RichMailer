# RichMailer
RichMailer is a smtp mail sender program written in python which has complete functionalities like Sending Junk mails from multiple CSV files, adding attachment, add HTML content. It supports all kind of mail servers. It only requires to fill the config XML files with the paramaters. 
I used this program to set up notifications in my company and assigned a automatic execution every monday at 10 AM in linux OS.
NB: For security purpose I've hidden the username, the port and the password in the config file.

I- CONFIGURATION FILE 'config/config.xml'
Replace the parameters with your own parameters:

   a- CONTENT_FILE
      After referencing the filename in the <content_file></content_file> tag add this file in the "messages" folder.
   
   b- ATTACHMENT_FOLDER
      After referencing the folder name in the <attachment_folder></attachment_folder> tag create a folder with that name and add all your attachments.
      
   c- DESTINATION_FOLDER
      After referencing the folder name in the <destination_folder></destination_folder> tag create a folder with name and add all your csv files containing the receivers email adresse.
      
 II- EXECUTION
 Simply run the file "sender.py". For example: in Linux OS: python3 sender.py.
 The program a separate email to each address registered in the csv files. No matter the number of emails, no matter the number of csv files.
 
 III- CREATE AUTOMATIC NOTIFICATION ON LINUX. 
 1- register execution to batch file.
 cat your_running_file.sh
 cd /path/to/your/richMailer/folder/
 python3 sender.py
 cd /
 2- Set execution permission 
 chmod +x your_running_file.sh
 3- Move to /usr/bin 
 mv your_running_file.sh your_running_file
 
 Every Monday at 10 AM:
 1- crontab -e
 2- 30 10 * * 1 your_running_file

 
