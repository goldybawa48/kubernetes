# Kubectl completion

**In this chapter we are going to add auto completion in kubectl command.**

## How to add 

- Run the following commands to add auto completion on kubectl.

    ```bash
    cd
    sudo apt install bash-completion
    cd .kube
    kubectl completion bash > kubecome.sh
    source $HOME/.kube/kubecome.sh
    source <(kubectl completion zsh)
    echo "source <(kubectl completion zsh)" >> ~/.zshrc
    source ~/.zshrc
    ```

- With these commands you can add auto completion on kubectl.

## Note

- This is for `zsh` shell.