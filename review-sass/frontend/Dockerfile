FROM node:18

# Set working directory
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./

RUN if [ -f package.json ]; then npm install; fi

# Copy application code
COPY . .

# Expose port
EXPOSE 3000
