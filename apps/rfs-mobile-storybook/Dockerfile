# This file is generated by Nx.
#
# Build the docker image with `npx nx docker-build rfs-mobile-storybook`.
# Tip: Modify "docker-build" options in project.json to change docker build args.
#
# Run the container with `docker run -p 3000:3000 -t rfs-mobile-storybook`.
FROM docker.io/node:lts-alpine

ENV HOST=0.0.0.0
ENV PORT=3000

WORKDIR /app

RUN addgroup --system rfs-mobile-storybook && \
          adduser --system -G rfs-mobile-storybook rfs-mobile-storybook

COPY dist/apps/rfs-mobile-storybook rfs-mobile-storybook
RUN chown -R rfs-mobile-storybook:rfs-mobile-storybook .

# You can remove this install step if you build with `--bundle` option.
# The bundled output will include external dependencies.
RUN npm --prefix rfs-mobile-storybook --omit=dev -f install

CMD [ "node", "rfs-mobile-storybook" ]
