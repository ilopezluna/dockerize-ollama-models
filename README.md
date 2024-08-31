# Build and Push Docker Image with Ollama Model GitHub Action

This GitHub Action automates the process of building and pushing a Docker image that includes a specified model running in Ollama to DockerHub.

## Inputs

- `docker_username`: **Required**. Your DockerHub username.
- `docker_password`: **Required**. Your DockerHub password.
- `docker_repository`: **Required**. The DockerHub repository name where the image will be pushed.
- `docker_tag`: **Required**. The tag to use for the pushed Docker image.
- `model_name`: **Required**. The name of the model to be included in the Docker image.
- `model_tag`: The tag of the model. Defaults to `latest`.
- `ollama_version`: The version of Ollama to use. Defaults to `latest`.

## Usage

To use this action in your workflow, add the following step:

```yaml
- name: Build and Deploy Docker Image
  uses: ilopezluna/dockerize-ollama-models@773965899379c6383374f222a862a03e762a0360
  with:
    docker_username: ${{ secrets.DOCKER_USERNAME }}
    docker_password: ${{ secrets.DOCKER_PASSWORD }}
    docker_repository: <your-dockerhub-repository>
    docker_tag: <your-image-tag>
    model_name: <your-model-name>
    model_tag: <your-model-tag> # Optional
    ollama_version: <ollama-version> # Optional
```

## Example
See the [example workflow](.github/workflows/build_image.yml) for a complete example.