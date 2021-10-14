# A Server Side Container for Google Tag Manager deployable to Heroku

It is now possible to create a Server Side Container for Google Tag Manager. The problem is that using Google Cloud to host it is very expensive, approximately $120 USD/month. The automatic deploy instructions at GTM creates a robust infrastructure that is scalable but is not cost-effective for small businesses.

Fortunately Google provided instructions for manual deploy of the server side container and the following docker image: `gcr.io/cloud-tagging-10302018/gtm-cloud-image:stable`. 

I created this repository to help creating GTM server side containers using Heroku **essentially for free***.

*the down-side of using Heroku's free tier is that after a period of inactivity your dyno/container will sleep. The next request will have to wait for the container startup and will take longer to complete.   


## Deploy to Heroku

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/ivanmonteiro/google-tag-manager-server-side-container)


## Instructions

First [create a Tag Manager server side container](https://developers.google.com/tag-manager/serverside#create_a_new_tag_manager_server-side_container) and selecet "Manual install" option to get your container key.

Create one preview container using the "Deploy to Heroku" button above. Fill your `CONTAINER_CONFIG` key, set `RUN_AS_PREVIEW_SERVER` to false and leave `PREVIEW_SERVER_URL` empty.

After the deploy is complete, copy the url of the preview server and create a new container using the "Deploy to Heroku" button above. Fill your `CONTAINER_CONFIG` key. Set `RUN_AS_PREVIEW_SERVER` to false and fill the `PREVIEW_SERVER_URL`. 


## Further Reading
https://developers.google.com/tag-manager/serverside/manual-setup-guide
https://developers.google.com/tag-manager/serverside#create_a_new_tag_manager_server-side_container
