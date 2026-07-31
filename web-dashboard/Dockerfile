# Use the official Node.js 18 image
FROM node:18-alpine AS web-dashboard-builder

WORKDIR /app

# Copy package files
COPY web-dashboard/package*.json ./
RUN npm ci

# Copy source code
COPY web-dashboard/ ./

# Build Next.js application
RUN npm run build

# Production image with nginx
FROM nginx:alpine

# Copy built files from builder
COPY --from=web-dashboard-builder /app/out /usr/share/nginx/html

# Copy custom nginx config
COPY web-dashboard/nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
