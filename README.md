# The Odin Project

## Useful stuff ദ്ദി ˉ꒳ˉ )

**Push local branch to remote and set up tracking**

```
git push -u origin <branch>
```

---

**Copy branch content to a subdir in another branch**

> [!NOTE]
> Run this command while on the target branch

> [!TIP]
> `foo/` is the prefix for the subdirectory
> `branch` is the source branch

```
git read-tree --prefix=foo/ -u branch
```

---

**Clean Deployment History via GitHub CLI**

1. Install [GitHub CLI](https://cli.github.com)
2. Run `gh auth login` to authenticate with your GitHub account
3. Run the following command to get all the deployments from the repo:

```
gh api --method GET -H "Accept: application/vnd.github+json" -H "X-GitHub-Api-Version: 2022-11-28" /repos/radblts/theOdinProject/deployments
```

4. Find the IDs of the deployments you want to delete
5. Run the following command to delete selected deployments

```
gh api --method DELETE -H "Accept: application/vnd.github+json" -H "X-GitHub-Api-Version: 2022-11-28" /repos/radblts/theOdinProject/deployments/{id}
```

> [!IMPORTANT]
> Don't forget to change `{id}`

**source: https://dhanushkac.medium.com/github-housekeeping-remove-unwanted-deployments-in-minutes-a57a52969eb2**

---

**Lorem Ipsum for Pictures**

[Lorem Picsum](https://picsum.photos)

**Examples:**

width / height

```
https://picsum.photos/200/300
```

square

```
https://picsum.photos/200
```

specific image (list of images: https://picsum.photos/images)

```
https://picsum.photos/id/237/200/300
```

static random image

```
https://picsum.photos/seed/picsum/200/300
```

request multiple images of the same size, without caching

```
<img src="https://picsum.photos/200/300?random=1">
<img src="https://picsum.photos/200/300?random=2">
```

## Setting up on a new device ୧( ◡̀_◡́)୨

**Git**

```
git config --global user.name "Your Name"
git config --global user.email yourname@example.com

```

```
git config --global init.defaultBranch main
```

```
ls ~/.ssh/id_ed25519.pub
```

```
ssh-keygen -t ed25519
```

Add key on GitHub

```
cat ~/.ssh/id_ed25519.pub
```

```
git config --global core.editor "code --wait"
```

sources: <br>
https://www.theodinproject.com/lessons/foundations-setting-up-git <br>
https://www.theodinproject.com/lessons/foundations-git-basics

**Installing nvm on Linux**

```
sudo apt update && sudo apt upgrade
```

```
sudo apt install curl
```

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.4/install.sh | bash
```

```
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

```
command -v nvm
```

source: https://github.com/TheOdinProject/curriculum/blob/main/foundations/javascript_basics/installation_guides/linux.md

**Installing Node**

```
nvm install --lts
```

```
nvm use --lts
```

```
npm config set min-release-age=3
```

source: https://www.theodinproject.com/lessons/foundations-installing-node-js
