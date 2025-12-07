n8n :Docker Installation Method

1. Make a folder for your custom n8n setup.

Type: mkdir n8n-custom && cd n8n-custom
This folder will hold your npm packages.

2. Create a package.json file.

Type: npm init -y
This file stores all npm packages you want.

3. Install any npm package you need.

Type: npm install package-name --save
Your package will now appear inside package.json.

4. Create a Dockerfile to build a custom image.

Use: nano Dockerfile
This file tells Docker what to include inside your new n8n container.

5. Add the required text into the Dockerfile.

Copy the lines I gave earlier.
These lines install your npm packages into the image.

6. Build your custom n8n Docker image.

Type: docker build -t my-n8n:custom .
This creates a new n8n image with npm packages included.

7. Run the new image.

Type:
docker run my-n8n:custom
This starts your n8n with all npm packages you added.

8. Check your logs to confirm it is working.

Type: docker logs -f n8n
This shows if n8n started without errors.

9. If you want more npm packages later…

Install them into your folder using npm install again.
Then rebuild your Docker image using the same build command.

10. Always rebuild instead of installing inside container.

Do NOT run npm install inside the running Docker container.
It disappears when the container restarts, so rebuild always.
