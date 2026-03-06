# SDD Specification: Infrastructure for SDD Navigator Stack

**Цель**: Развернуть Rust API + PostgreSQL + Next.js frontend в Kubernetes через Helm + Ansible с CI-валидацией.

**Требования**:
- Использовать только Helm charts и Ansible (kubernetes.core.helm)
- Отдельные чарты для каждого компонента
- Поддержка dev/staging/prod через values
- CI: helm lint + ansible-lint + kubeconform + dry-run
- PostgreSQL с persistence
- Rust API и Next.js — stateless, с readiness/liveness probes
- Ingress (опционально) + секреты через values

**Критерии приёмки**:
- `ansible-playbook deploy-stack.yml` разворачивает весь стек
- CI проходит на каждый PR
- Время деплоя < 5 минут в Minikube/Kind