
# mosaのmac環境構築手順

[構築手順](./mac_build.txt)をみると全部かいてあるよ

秘伝のタレのdotfilesは別リポジトリだよ

## Ansible
Ansibleだけ試してみたいときはこちら

```
brew install python
brew install ansible

mkdir .macbook-provisioning
cd .macbook-provisioning/
ln -s <THIS-REPOSITORY>/hosts hosts
ln -s <THIS-REPOSITORY>/localhost.yml localhost.yml

HOMEBREW_CASK_OPTS="--appdir=/Applications"  ansible-playbook -i hosts -vv localhost.yml
```
