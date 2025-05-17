FROM node:18

WORKDIR /app

COPY . .

RUN corepack enable && \
    corepack prepare pnpm@8.6.3 --activate && \
    pnpm install --no-frozen-lockfile && \
    pnpm build

EXPOSE 5678

CMD ["pnpm", "start"]
