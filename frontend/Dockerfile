# 1. Базовый образ
FROM node:24-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

# Собираем Next.js
RUN npm run build

# Запускаем Next.js в production
# EXPOSE 3000

CMD ["npm", "run", "dev"]






#  Production stage
# FROM node:24-alpine

# WORKDIR /app

# ENV NODE_ENV=production

# COPY --from=builder /app/package*.json ./
# COPY --from=builder /app/node_modules ./node_modules
# COPY --from=builder /app/.next ./.next
# COPY --from=builder /app/public ./public

# EXPOSE 3000

# CMD ["npm", "start"]