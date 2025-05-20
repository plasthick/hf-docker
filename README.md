First of all I want to thank you for this solution for DaddyLive channels.

My solution is for rebuild automatically the space in Huggingface.If you made changes in your repository we'll get it with this way without using manual factory rebuild trigger on HF.

I created a new repository in here to make this idea work.

Then added 3 files which are for the huggingface space, included (replaced some necessary codes) with your Dockerfile.
Important: I added timestamp to Dockerfile and yaml file to make it force to Factory Rebuild. Made it with Turkish timezone so you can change it by your preferences.

Also created a workflow to make it push and commit to huggingface space area by cloning all files from Github repository to Huggingface Space.

Just need 2 github action secrets value. (This is for hiding our secret tokens and space names from public)

Create an Access Token from huggingface in Settings. Add it to github repository action secret with name HF_TOKEN
Your space-name in huggingface which you use created before. Add it to github repository action secret with name HF_SPACE_NAME
hf-docker << This is my repository to do it.

Everyone who needs to automatically Factory Rebuild the space on HF can fork it.

In Summary for all who wants to do it:


Fork my repository. hf-docker

Create your Access Token in Huggingface settings

Go to your repository's settings in here (Github) which you forked from my hf-docker. In left menu click Secrets and variables and then Actions. Click New repository secret and add your huggingface secret token with HF_TOKEN and your huggingface username/space name (YourUserName/space-name for example: pigzillaaaaa/dproxy) with HF_SPACE_NAME

For manual trigger go to Actions tab in your forked Github repository and trigger Rebuild HF workflow or wait it about 2 hours to auto run if you didn't change it in rebuild_hf.yml codes.
