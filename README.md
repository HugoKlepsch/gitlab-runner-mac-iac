# Gitlab runner mac

Run a gitlab runner instance on a mac. This repo has all you need to 
create and register a single instance gitlab runner on a mac. 

Following [this tutorial](https://docs.gitlab.com/runner/install/osx.html) 
rather than [this page](https://docs.gitlab.com/runner/configuration/macos_setup.html) 
because the former mentioned that gitlab does not administer the homebrew 
recipe, which is used in the later.

# Usage

- Create a runner with a shared runner auth token: [link](https://docs.gitlab.com/ee/ci/runners/runners_scope.html#create-a-shared-runner-with-a-runner-authentication-token)

## Install GitLab Runner on macOS

Download (you may have to create the `/usr/local/bin` directory, and add it to your `PATH` variable):

- Intel macs:

```bash
sudo curl --output /usr/local/bin/gitlab-runner "https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-darwin-amd64"
```

- Apple Silicon macs (M1, etc):

```bash
sudo curl --output /usr/local/bin/gitlab-runner "https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-darwin-arm64"
```

Give permissions to execute:

```bash
sudo chmod +x /usr/local/bin/gitlab-runner
```

## Register runner

Registering will create `config.toml`.

[Register](https://docs.gitlab.com/runner/register/index.html?tab=macOS#register-with-a-runner-authentication-token)

## Start runner

Open a terminal as the user that will be running the runner, install GitLab 
runner as a service and start it:

```bash
gitlab-runner install
gitlab-runner start
```

Reboot your system
