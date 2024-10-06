# Login
### Sistema de Cadastro e Login de Usuário em PHP com PDO

Este projeto implementa um sistema completo de cadastro, login e logout de usuários utilizando PHP, PDO (PHP Data Objects) e MySQL para o armazenamento de dados. Ele abrange desde a interface HTML para entrada de dados até a lógica de autenticação e gerenciamento de sessões.

#### Funcionalidades:

1. **Formulário de Cadastro**:
   - Um formulário HTML simples que captura o e-mail e a senha do usuário, enviando esses dados para o script `motor.php` via método `POST`.
   - O script processa e armazena os dados no banco de dados de forma segura, utilizando **hashing de senhas** com `password_hash()` para proteção dos dados sensíveis.

2. **Validação e Mensagens de Sucesso/Erro**:
   - O código exibe mensagens de sucesso ou erro na tela após o cadastro, com base em um código de status passado via URL.
   - Exemplo: se o código for `1`, o sistema exibe "Cadastrado com Sucesso", caso contrário, exibe o erro.

3. **Login de Usuário**:
   - Formulário HTML que permite ao usuário inserir e-mail e senha para login.
   - O script `login.php` valida as credenciais comparando a senha inserida com o hash armazenado no banco de dados usando `password_verify()`.
   - Se as credenciais forem válidas, o usuário é redirecionado para o painel de controle.

4. **Gerenciamento de Sessão**:
   - O sistema utiliza sessões para manter o usuário logado, armazenando informações como o e-mail do usuário e um flag de login.
   - Scripts como `painel.php` verificam se a sessão está ativa antes de permitir o acesso, e o usuário pode fazer logout através de um botão que destrói a sessão.

5. **Segurança**:
   - O código utiliza **prepared statements** com PDO para evitar **SQL Injection**.
   - As entradas dos usuários são sanitizadas com `htmlspecialchars()` para evitar ataques de **Cross-Site Scripting (XSS)**.

#### Tecnologias Utilizadas:
- **PHP** para a lógica de backend.
- **PDO** para interação segura com o banco de dados MySQL.
- **HTML5** para criação dos formulários de cadastro e login.
- **MySQL** para armazenamento dos dados dos usuários.

Este sistema é uma ótima base para qualquer aplicação web que precise de um sistema de autenticação seguro e funcional.
