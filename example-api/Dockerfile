FROM node:24-alpine

# Install wget for health checks
RUN apk add --no-cache wget

WORKDIR /app
COPY package*.json ./

# Install production dependencies only
RUN npm install --omit=dev && \
    npm cache clean --force

COPY src ./src

# Create non-root user
RUN addgroup -g 1001 -S nodejs && \
    adduser -S nodejs -u 1001 && \
    chown -R nodejs:nodejs /app
USER nodejs

EXPOSE 3000
CMD ["node", "src/index.js"]
