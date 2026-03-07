# sdd-navigator-infra
# SDD Navigator — тестовое задание

Развёртывание стека (Rust API + Next.js + PostgreSQL) в Kubernetes  
всё сделано **одним файлом** ansible playbook.

Файл: `deploy-sdd-navigator.yaml`

## Что используется

- Ansible + kubernetes.core collection
- Helm chart bitnami/postgresql
- Прямое применение Deployment + Service (без отдельных helm-чартов для api и frontend)

## Требования

```bash
ansible --version               # должен быть 2.10+
ansible-galaxy collection install kubernetes.core community.general
kubectl version --client
# самый простой вариант (локально, без ssh)
ansible-playbook deploy-sdd-navigator.yaml --connection=local
