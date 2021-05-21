## Welcome to my github page. 

I am a solutions architect, focused on implementing cutting edge technology to make creating content faster and easier. Currently I'm the manager of post-production technology for Spotify Studios. This is my code repository for apps and scripts I've created in Python. I am not a programmer by trade, although I did have ~2 years of computer science classes in college, including C++/C#, Visual Basic, and MYSQL, before focusing on my degree of information systems. I'm most interested in building apps that connect systems to automate media and entertainment workflows. 

### IconikCloudFunctions
These are event-driven serverless applications I've written in Python to automate processes inside Iconik.io, a hybrid-cloud asset management system that has a REST API. I run these in Google Cloud as cloud functions. My learning goal this year is to learn Flask and Docker and containerize these. 

#### Iconik Share Slack Log
This script is based on code that Mike Szumlinski wrote for a livestream hackathon. Shoutout to Mike for inspiring me to try my hand at programming again. This is the first Python app I wrote!
This script recieves a webhook from Iconik, triggered anytime any user shares out an asset. It will gather information on who created the share, who the share was sent to, any recipient email addresses if they exist, and whether or not it was a generated shortlink. T

#### Build Podcast Folderstructure

At my current job, we have a specific folder structure we use to keep everything in a podcast project organized. Interestingly, Iconik's storage gateway will replicate a folder structure that it indexes on on-premise storage like a NAS share. Those collections that get made are 'mapped' and if something changes on the local storage, that will be reflected in Iconik. So sometimes we want to build that folder structure without having it be mapped. 

This app recieves a JSON payload from Iconik that contains a podcast name, project code, budget code, season number, episode count, and some other ancillary information. It also asks for a choice of internal or external podcast folder structure. It will then go off and build the folder structure as a set of collections in Iconik. 

If it's an external structure, the user is also required to input what master assets are expected to be delivered by the external production company. The app will then build 'placeholder' asset records for each of those required deliverables, and tag those assets with the metadata that was input by the user. 

#### Bulk Update Collection Metadata
For some reason in Iconik there's a way to bulk update asset metadata, but not collection metadata. This is likely because of design intent with the platform. Regardless we needed a quick way to tag lots of folders with metadata. This small app does that by reciving a JSON payload 

#### Collection Recursive Metadata Purge
This is a big undo button for Iconik. It will recursively delete all metadata from all assets and collections that are hierarchicaly beneath a submitted collection ID. I wrote this because sometimes our users (or me) will make a mistake, and we needed a quick way to fix. 


