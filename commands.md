## encription

ansible-vault encrypt .ansible_vars.yml --vault-password-file .env
ansible-vault decrypt .ansible_vars.yml --vault-password-file .env

## git tag

git tag <nom_du_tag>
git push origin <nom_du_tag> ## OU : git push --tags

## deploy playbook

ansible-playbook deploy_nextcloud.yml --vault-password-file .env