<div align="center">

# 🖥️ DG Inventory

### Gestão de ativos de TI com PHP e SQLite

**Um projeto DG Tech — tecnologia aplicada à organização e ao controle de patrimônio.**

![PHP](https://img.shields.io/badge/PHP-8.1%2B-777BB4?logo=php&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-PDO-003B57?logo=sqlite&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-Interface-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-Responsivo-1572B6?logo=css3&logoColor=white)
![Status](https://img.shields.io/badge/Status-Demonstração%20funcional-2ea44f)

[**Código-fonte**](https://github.com/danielcc6p32-droid/dg-inventory) · **Demo online: em preparação**

</div>

---

## Sobre o projeto

O **DG Inventory** é uma aplicação web para **cadastro, consulta e controle de equipamentos de TI**, desenvolvida com PHP puro e banco de dados SQLite. A proposta é demonstrar, de forma prática, conceitos de desenvolvimento backend, modelagem de dados, autenticação, proteção de formulários e construção de interfaces web.

O projeto nasceu da experiência com infraestrutura e suporte técnico e foi desenvolvido como parte dos estudos em **Desenvolvimento de Sistemas**, integrando o portfólio profissional DG Tech.

## Funcionalidades

- **CRUD de equipamentos:** cadastro, visualização, edição e exclusão.
- **Informações do patrimônio:** identificação, tipo, setor/responsável, status e observações.
- **Categorias:** Notebook, Desktop, Monitor, Impressora, Rede e Outro.
- **Status:** Disponível, Em uso, Manutenção e Baixado.
- **Pesquisa textual** por equipamento, descrição ou responsável e **filtro por status**.
- **Cadastro e login de usuários** com senhas protegidas por hash.
- **Modo demonstração sem cadastro**, com conta de teste isolada por visitante.
- **Separação dos registros por usuário**, tanto nas consultas quanto nas operações de alteração e exclusão.
- **Interface responsiva**, com layout adaptado para desktop e dispositivos móveis.

> A demonstração foi planejada para avaliação funcional. Não utilize dados pessoais ou patrimoniais reais neste ambiente.

## Tecnologias e conceitos aplicados

| Camada | Tecnologia / conceito |
| --- | --- |
| Backend | PHP 8.1+ sem framework |
| Banco de dados | SQLite com PDO |
| Frontend | HTML5 e CSS3 responsivo |
| Autenticação | Sessões PHP e `password_hash()` / `password_verify()` |
| Segurança | Token CSRF, escape de HTML, consultas preparadas e cabeçalhos de segurança |
| Versionamento | Git e GitHub |

## Estrutura do projeto

```text
dg-inventory/
├── public/
│   ├── index.php       # Interface, autenticação e operações do sistema
│   └── style.css       # Estilos e responsividade
├── private/
│   ├── README.txt      # Orientações sobre arquivos privados
│   └── dados.sqlite    # Criado automaticamente; NÃO versionado
├── .gitignore
└── README.md
```

O diretório `public/` é a raiz do servidor web; o diretório `private/` deve permanecer inacessível por HTTP.

## Executar localmente

**Pré-requisitos:** PHP 8.1 ou superior, com `PDO`, `pdo_sqlite` e `mbstring` habilitados.

1. Clone o repositório e entre na pasta:

   ```bash
   git clone https://github.com/danielcc6p32-droid/dg-inventory.git
   cd dg-inventory
   ```

2. Inicie o servidor de desenvolvimento do PHP:

   ```bash
   php -S localhost:8000 -t public
   ```

3. Abra **http://localhost:8000** no navegador.
4. Clique em **Entrar na demonstração (sem cadastro)** para experimentar o sistema imediatamente.

O banco SQLite e suas tabelas são criados automaticamente na primeira execução, desde que a pasta `private/` permita escrita pelo processo PHP.

## Cuidados para implantação

- Configure o **document root** para `public/`, preservando `private/` fora da área pública.
- Garanta escrita no banco SQLite e **armazenamento persistente** para que cadastros não sejam perdidos em reinicializações ou atualizações.
- Nunca publique `dados.sqlite`, credenciais ou arquivos reais de usuários no GitHub.
- Antes de abrir acesso público, valide sessões, limites de requisição, permissões e políticas de uso da hospedagem.

## Próximas evoluções

- Dashboard com indicadores por categoria e status.
- Exportação de relatórios CSV.
- Histórico de movimentações e auditoria.
- Perfis e permissões administrativas.
- Melhorias de acessibilidade e usabilidade.

---

**Desenvolvido por Daniel Pereira Gonçalves**  
*DG Tech · Portfólio de Desenvolvimento de Sistemas*
