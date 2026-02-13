# 1. Базовый образ
FROM node:24-alpine

# 2. Рабочая директория
WORKDIR /app

# 3. Копируем package.json и yarn.lock / package-lock.json
COPY package*.json ./

# 4. Устанавливаем зависимости
RUN npm install

# 5. Копируем весь код
COPY . .

# 6. Генерация Prisma client
RUN npx prisma generate

# 7. Компиляция (если TypeScript)
RUN npm run build

# 8. Экспорт переменных окружения
ENV NODE_ENV=development
ENV PORT=9000

EXPOSE 9000
# 9. Команда запуска
CMD ["npm", "run", "dev"]
# CMD ["node", "dist/main.js"]
