# My-zsh-installation
Мои личные Ansible-плейбуки для автоматической установки и настройки zsh с нужными мне плагинами, темой и полезными алиасами. Поддерживает macOS и Linux, автоматически выбирает нужные плагины в зависимости от операционной системы.

### Установка
```bash
ansible-galaxy install -r .ansible/requirements.yml
ansible-playbook playbooks/install-zsh.ansible.yml -K
ansible-playbook playbooks/install-my-gnzh-theme.ansible.yml -K
```

### Дальнейшая настройка
#### Docker autocomplete
```bash
mkdir -p ~/.oh-my-zsh/completions
docker completion zsh > ~/.oh-my-zsh/completions/_docker
cat <<"EOT" >> ~/.zshrc.local
# Автодополнение для docker (добавлено мной)
FPATH="$HOME/.docker/completions:$FPATH"
autoload -Uz compinit
compinit
EOT
```
