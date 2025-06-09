# Ansible - Coleta de Usuários e Grupos em Servidores Linux

Este projeto Ansible realiza a **coleta de usuários e grupos ativos** em servidores Linux e **gera um relatório em HTML** consolidado e formatado.

## 📁 Estrutura do Projeto

```
ansible-project/
├── playbooks/
│   ├── coleta_usuarios_grupos.yml     # Playbook para coletar usuários e grupos
│   └── gera_relatorio_html.yml        # Playbook para gerar relatório HTML
├── roles/
│   └── coleta_info/
│       ├── tasks/
│       │   └── main.yml               # Tarefas da role de coleta
│       └── templates/
│           └── relatorio.html.j2      # Template Jinja2 do relatório HTML
├── inventario/
│   └── hosts                          # Inventário com os servidores Linux
└── dados/
    └── resultados.json                # Arquivo gerado com os dados coletados
```

## Sugestão, comando para criar a estrutura acima
```mkdir -p ansible_colects/{playbooks,roles/coleta_info/{tasks,templates},inventario,dados} && \
touch ansible_colects/playbooks/{coleta_usuarios_grupos.yml,gera_relatorio_html.yml} && \
touch ansible_colects/roles/coleta_info/tasks/main.yml && \
touch ansible_colects/roles/coleta_info/templates/relatorio.html.j2 && \
touch ansible_colects/inventario/hosts && \
touch ansible_colects/dados/resultados.json
```

## 🚀 Funcionalidades

- Conecta a múltiplos servidores Linux via SSH
- Coleta usuários e grupos não padrão (ativos)
- Armazena os dados em JSON
- Gera um relatório em HTML usando template Jinja2

## 🛠️ Pré-requisitos

- Ansible instalado
- Acesso SSH aos servidores com permissões para listar usuários/grupos
- Python instalado nos hosts gerenciados

## ▶️ Como Usar

1. **Configurar o inventário:**

   Edite o arquivo `inventario/hosts` com os IPs ou nomes dos servidores Linux.

2. **Executar coleta:**

   ```bash
   ansible-playbook -i inventario/hosts playbooks/coleta_usuarios_grupos.yml
   ```

3. **Gerar relatório HTML:**

   ```bash
   ansible-playbook playbooks/gera_relatorio_html.yml
   ```

4. **Ver relatório:**

   O relatório será gerado no arquivo `dados/relatorio.html`.

## 📌 Observações

- O relatório ignora usuários e grupos padrão do sistema.
- A estrutura suporta servidores com diferentes distribuições (RHEL, CentOS, RockyLinux, Ubuntu, Debian).

## 📄 Licença

Este projeto está licenciado sob os termos da [MIT License](LICENSE).

