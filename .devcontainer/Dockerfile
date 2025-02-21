FROM node:20-alpine

# Install PNPM globally
RUN corepack enable && corepack prepare pnpm@10.4.1 --activate

# Set working directory
WORKDIR /workspace

# Copy package.json and pnpm-lock.yaml to avoid reinstalling dependencies unnecessarily
COPY package.json pnpm-lock.yaml pnpm-workspace.yaml ./

# Install dependencies
RUN pnpm install

# Default to using the app folder
WORKDIR /workspace/packages/app

CMD ["pnpm", "dev"]
