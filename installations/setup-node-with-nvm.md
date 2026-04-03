# Setup Node with nvm

## Install nvm

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/<NVM_VERSION>/install.sh | bash   # <- install nvm
export NVM_DIR="$HOME/.nvm"                                                             # <- add .nvm to export path
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"                                         # <- load in current shell
nvm --version                                                                           # <- get version of nvm
```

## Install Node.js

```bash
nvm install --lts          # <- install current LTS
nvm use --lts              # <- use current LTS
nvm alias default 'lts/*'  # <- make LTS default
node -v                    # <- get node version
npm -v                     # <- get npm version
```
