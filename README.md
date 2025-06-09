Estrutura Ansible para validar em todos os servidores Linux os usuários e grupos,listar e formatar em HTML.

ansible-project/
├── playbooks/
│   ├── coleta_usuarios_grupos.yml
│   └── gera_relatorio_html.yml
├── roles/
│   └── coleta_info/
│       ├── tasks/
│       │   └── main.yml
│       └── templates/
│           └── relatorio.html.j2
├── inventario/
│   └── hosts
└── dados/
    └── resultados.json
