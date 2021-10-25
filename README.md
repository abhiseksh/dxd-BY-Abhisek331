##CONTACT
••¤(`×  🎀  - [𝒳] 𝒯𝑒𝓁𝑒𝑔𝓇𝒶𝓂  🎀  ×`(¤•• --- 9732390526

##CONTACT INSTAGRAM
-USE THIS LINK TO 📞 [INSTA LINK](https://www.instagram.com/abhisekmajumder331/)

[![Priiiiyo](https://www.linkpicture.com/q/@HUNTER-GAMING.png)

# Priiiiyo Mirror Bot
![GitHub Repo stars](https://img.shields.io/github/stars/PriiiiyoDevs/priiiiyo-mirrorbot?color=blue&style=flat)
![GitHub forks](https://img.shields.io/github/forks/PriiiiyoDevs/priiiiyo-mirrorbot?color=green&style=flat)
![GitHub contributors](https://img.shields.io/github/contributors/PriiiiyoDevs/priiiiyo-mirrorbot?style=flat)
![GitHub watchers](https://img.shields.io/github/watchers/PriiiiyoDevs/priiiiyo-mirrorbot)
![Docker Pulls](https://img.shields.io/docker/pulls/priiiiyo/mega-sdk-python?label=Docker%20Pull)
[![Channel](https://img.shields.io/badge/Join%20Channel-!-red)](https://t.me/PriiiiyoMirrorUpdates)

</details>

**NOTE**: If you want to use port other than 80, change it in [docker-compose.yml](https://github.com/SlamDevs/slam-mirrorbot/blob/master/docker-compose.yml)

- Using Docker-compose, you can edit and build your image in seconds:
```
sudo apt install docker-compose
```
- Build and run Docker image:
```
sudo docker-compose up
```
- After editing files with nano for example (nano start.sh):
```
sudo docker-compose build
sudo docker-compose up
```
OR
```
sudo docker-compose up --build
```
- To stop Docker: 
```
sudo docker ps
```
```
sudo docker stop id
```
- To clear the container (this will not affect the image):
```
sudo docker container prune
```
- To delete the image:
```
sudo docker image prune -a
```
- Tutorial video from Tortoolkit repo
<p><a href="https://youtu.be/c8_TU1sPK08"> <img src="https://img.shields.io/badge/See%20Video-black?style=for-the-badge&logo=YouTube" width="160""/></a></p>

## Deploying on Heroku
- Deploying on Heroku with Github Workflow
<p><a href="https://github.com/PriiiiyoDevs/priiiiyo-mirrorbot/wiki/Deploying-priiiiyo-mirrorbot-on-Heroku-with-Github-Workflows"> <img src="https://img.shields.io/badge/Deploy%20Guide-blueviolet?style=for-the-badge&logo=heroku" width="170""/></a></p>

- Deploying on Heroku with heroku-cli and Goorm IDE
<p><a href="https://telegra.ph/How-to-Deploy-a-Mirror-Bot-to-Heroku-with-CLI-05-06"> <img src="https://img.shields.io/badge/Deploy%20Guide-grey?style=for-the-badge&logo=telegraph" width="170""/></a></p>

# Using Service Accounts for uploading to avoid user rate limit
For Service Account to work, you must set `USE_SERVICE_ACCOUNTS` = "True" in config file or environment variables.
**NOTE**: Using Service Accounts is only recommended while uploading to a Team Drive.

## Generate Service Accounts. [What is Service Account](https://cloud.google.com/iam/docs/service-accounts)
<details>
    <summary><b>Click Here For More Details</b></summary>

Let us create only the Service Accounts that we need. 
**Warning**: abuse of this feature is not the aim of this project and we do **NOT** recommend that you make a lot of projects, just one project and 100 SAs allow you plenty of use, its also possible that over abuse might get your projects banned by Google. 

**NOTE:** 1 Service Account can copy around 750 GB a day, 1 project can make 100 Service Accounts so that's 75 TB a day, for most users this should easily suffice.
```
python3 gen_sa_accounts.py --quick-setup 1 --new-only
```
A folder named accounts will be created which will contain keys for the Service Accounts.

Or you can create Service Accounts to current project, no need to create new one

- List your projects ids
```
python3 gen_sa_accounts.py --list-projects
```
- Enable services automatically by this command
```
python3 gen_sa_accounts.py --enable-services $PROJECTID
```
- Create Sevice Accounts to current project
```
python3 gen_sa_accounts.py --create-sas $PROJECTID
```
- Download Sevice Accounts as accounts folder
```
python3 gen_sa_accounts.py --download-keys $PROJECTID
```
If you want to add Service Accounts to Google Group, follow these steps

- Mount accounts folder
```
cd accounts
```
- Grab emails form all accounts to emails.txt file that would be created in accounts folder
```
grep -oPh '"client_email": "\K[^"]+' *.json > emails.txt
```
- Unmount acounts folder
```
cd -
```
Then add emails from emails.txt to Google Group, after that add Google Group to your Shared Drive and promote it to manager.

**NOTE**: If you have created SAs in past from this script, you can also just re download the keys by running:
```
python3 gen_sa_accounts.py --download-keys project_id
```

</details>

## Add all the Service Accounts to the Team Drive
- Run:
```
python3 add_to_team_drive.py -d SharedTeamDriveSrcID
```

# Youtube-dl authentication using [.netrc](https://github.com/SlamDevs/slam-mirrorbot/blob/master/.netrc) file
For using your premium accounts in Youtube-dl or for protected Index Links, edit the netrc file according to following format:
```
machine host login username password my_youtube_password
```
For Index Link with only password without username, even http auth will not work, so this is the solution.
```
machine example.workers.dev password index_password
```
Where host is the name of extractor (eg. Youtube, Twitch). Multiple accounts of different hosts can be added each separated by a new line.

# Credits

Thanks to:
