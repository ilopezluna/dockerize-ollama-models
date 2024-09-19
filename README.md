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
- `short_description`: The DockerHub repository description

## Usage

To use this action in your workflow, add the following step:

```yaml
- name: Build and Deploy Docker Image
  uses: ilopezluna/dockerize-ollama-models@v1.0.2
  with:
    docker_username: ${{ secrets.DOCKER_USERNAME }}
    docker_password: ${{ secrets.DOCKER_PASSWORD }}
    docker_repository: <your-dockerhub-repository>
    docker_tag: <your-image-tag>
    model_name: <your-model-name>
    model_tag: <your-model-tag> # Optional
    ollama_version: <ollama-version> # Optional
    short_description: <model-description> # Optional
```

## Example
See the [example workflow](.github/workflows/dockerize_ollama_models.yml) for a complete example.
