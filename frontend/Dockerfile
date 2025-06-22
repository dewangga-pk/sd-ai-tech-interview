FROM node:22.15.0
WORKDIR /app
COPY package*.json . 
RUN npm install && npm install --no-save serve
COPY . .
# Build-time environment variable for Vite
ARG VITE_API_BASE_URL
ENV VITE_API_BASE_URL=$VITE_API_BASE_URL
# Build the frontend
RUN npm run build
EXPOSE 3000

CMD ["npx", "serve", "-s", "dist"]