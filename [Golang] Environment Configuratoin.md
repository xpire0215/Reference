# Golang Environment Configuratoin

## Environment

### Modify profile (bash) or zprofile (zsh)

```
vi ~/.profile
```

### Add the workspace (bin) to PATH

```
(.profile)

export PATH="$PATH:$(go env GOPATH)/bin"

For example:
export PATH="$PATH:$HOME/go/bin"
```

### Export Go environment

```
(.profile)

export GOPATH="$(go env GOPATH)"

For example:
export GOPATH="$HOME/go"

```

