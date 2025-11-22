---
icon: fontawesome/solid/cube
---

# Images & Containers

Designing & developing within containers.

## For Development

For Python projects, create:

<ul class="disc">
  <li class="disc">requirements.txt</li>
  <li class="disc">Dockerfile</li>
  <li class="disc">devcontainer.json: optional, for <a href="https://github.com/features/codespaces" target="_blank">GitHub CodeSpaces</a></li>
</ul>

Within the `.devcontainer/` directory, which must be within the project's parent directory; <a href="https://github.com/excomputing/distributions/tree/master/.devcontainer" target="_blank">example</a>.  Always ascertain that the `requirements.txt` file lists the packages/libraries required for development.  Next, build the image:

```shell
docker build . --file .devcontainer/Dockerfile --tag {tag.name}
```

Subsequently, run an instance of the image for development purposes, e.g.,

```shell
docker run --rm -i -t -p 127.0.0.1:10000:8888 -w /app
  --mount type=bind,src="$(pwd)",target=/app {tag.name}
```

or

```shell
docker run --rm -i -t -p 127.0.0.1:10000:8888 -w /app
  --mount type=bind,src="$(pwd)",target=/app -v ~/.aws:/root/.aws {tag.name}
```

wherein

<ul>
  <li>--rm: <a href="https://docs.docker.com/engine/reference/commandline/run/#:~:text=a%20container%20exits-,%2D%2Drm,-Automatically%20remove%20the" target="_blank">automatically remove container</a></li>
  <li>-i: <a href="https://docs.docker.com/engine/reference/commandline/run/#:~:text=and%20reaps%20processes-,%2D%2Dinteractive,-%2C%20%2Di" target="_blank">interact</a></li>
  <li>-t: <a href="https://docs.docker.com/get-started/02_our_app/#:~:text=Finally%2C%20the-,%2Dt,-flag%20tags%20your" target="_blank">tag</a></li>
  <li>-p: <a href="https://docs.docker.com/engine/reference/commandline/run/#:~:text=%2D%2Dpublish%20%2C-,%2Dp,-Publish%20a%20container%E2%80%99s" target="_blank">publish a container's port to a host port</a></li>
  <li>--mount type=bind: <a href="https://docs.docker.com/engine/storage/bind-mounts/#syntax" target="_blank">a bind mount</a></li>
  <li>-v: <a href="https://docs.docker.com/engine/storage/volumes/" target="_blank">volume</a></li>
</ul>

and `-p 10000:8888` maps the host port `10000` to container port `8888`.  Note, the container's working environment, i.e., -w, must be inline with this project's top directory.  The second option is important for interactions with Amazon Web Services.


Get the name of the running instance of {tag.name} via:

```shell
docker ps --all
```

Next, attach the running IDE (integrated development environment) application to a running container.  If IntelliJ IDEA, connect to a Docker <a href="https://www.jetbrains.com/help/idea/docker.html#connect_to_docker" target="_blank">daemon</a> via[^1]

<ul>
  <li><b>Settings</b> &rarr; <b>Build, Execution, Deployment</b> &rarr; <b>Docker</b> &rarr; <b>WSL:</b> {operating.system}</li>
  <li><b>View</b> &rarr; <b>Tool Window</b> &nbsp; <b>Services</b> <br>Within the <b>Containers</b> section connect to the running instance of interest, or ascertain connection to the running instance of interest.</li>
</ul>



## For Deployment

**Never deploy root containers**; study [this production Dockerfile](https://github.com/excomputing/distributions/blob/master/Dockerfile), which blocks access to `root` by creating a standard user; cf. [the development Dockerfile](https://github.com/excomputing/distributions/blob/master/.devcontainer/Dockerfile).

<br>
<br>
<br>
<br>

<br>
<br>
<br>
<br>


[^1]: Visual Studio Code as its container attachment instructions; study [Attach Container](https://code.visualstudio.com/docs/devcontainers/attach-container).

<br>
<br>

