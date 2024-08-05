# kubectl-neat-diff

De-clutter your `kubectl diff` output using [kubectl-neat](https://github.com/itaysk/kubectl-neat) (looking at you, `managedFields`):

![banner](./banner.png)

## Guide

(1) Install `kubectl-neat-diff`

```bash
project="$(mktemp -d)" && \
  git clone https://github.com/djosix/kubectl-neat-diff "$project" && \
  cd "$project" && make install && cd - && rm -r "$project"
```

(2) Install `colordiff` if you want syntax highlighting

```bash
sudo apt install colordiff
```

(3) Customize the diff command used by `kubectl diff`

```sh
export KUBECTL_EXTERNAL_DIFF='kubectl-neat-diff'
export KUBECTL_NEAT_DIFF_COMMAND='colordiff -uN'
kubectl diff -f -
```

## Credits

All the hard work is done by [kubectl-neat](https://github.com/itaysk/kubectl-neat). Go, give them a star!

## License

Licensed under the Apache-v2 license
