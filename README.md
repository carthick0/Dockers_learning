🚢 Docker Basics - Up to Dockerfile
This guide introduces Docker and explains concepts up to writing and using a basic Dockerfile.

📋 Prerequisites
Before you start:

✅ Install Docker Desktop for Windows/Mac
✅ Make sure Docker is running
✅ Basic knowledge of Node.js (optional, but helpful)
✅ Folder structure:
project-folder/ ├── Dockerfile ├── index.js └── package.json

📦 What is Docker?
Docker is a tool that lets you package applications with all their dependencies into a container, so that it runs consistently across different environments.

🧱 Key Concepts
1. Image
A read-only template used to create containers.
Example: node:18-alpine is an official Node.js image.
2. Container
A running instance of an image.
Containers are isolated and lightweight.
3. Docker Engine
The runtime used to build and run containers.
📝 What is a Dockerfile?
A Dockerfile is a script with instructions for building a Docker image.

🛠️ Example Dockerfile
# 1. Use a base image
FROM node:18-alpine

# 2. Set the working directory
WORKDIR /app

# 3. Copy only package.json first (for caching)
COPY package.json ./

# 4. Install dependencies
RUN npm install

# 5. Copy the remaining project files
COPY . .

# 6. Expose port (optional, for documentation)
EXPOSE 3000

# 7. Start the app
CMD ["npm", "start"]


#🔨 Build Docker Image

docker build -t welcome-docker .


#▶️ Run the Container

docker run -p 3000:3000 welcome-docker

Visit: http://localhost:3000

#You should see:

🚀 Hello from Docker!
