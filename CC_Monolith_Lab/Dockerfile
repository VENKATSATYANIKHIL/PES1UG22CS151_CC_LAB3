FROM nginx:alpine
WORKDIR /usr/share/nginx/html

# Remove default nginx HTML files
RUN rm -rf ./*

# Install git, clone the repo, and copy files
RUN apk add --no-cache git && \
    git clone <YOUR_GITHUB_REPO_URL> /temp-repo && \
    cp -r /temp-repo/* . && \
    rm -rf /temp-repo

# Expose port 80 for web traffic
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
