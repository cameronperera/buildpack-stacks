ARG base_image
FROM ${base_image}

# Install packages that we want to make available at build time
RUN apt-get update && \
  apt-get install -y curl git jq && \
  rm -rf /var/lib/apt/lists/*

# Set required CNB information
ARG stack_id
ENV CNB_STACK_ID=${stack_id}
LABEL io.buildpacks.stack.id=${stack_id}

# Set user and group (as declared in base image)
USER ${CNB_USER_ID}:${CNB_GROUP_ID}
