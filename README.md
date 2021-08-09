# Teste técnico Intergalaxy

Clone esse repositório (atenção a flag de submódulos)

    git clone --recurse-submodules https://github.com/JeanGT/Intergalaxy-test.git
    
### API setup

Acesse o diretório da API

    cd intergalaxy-test-api

Instale as dependências

    composer install

Copie o arquivo env de exemplo

    cp .env.example .env

Gere uma nova chave de aplicação

    php artisan key:generate

Gere uma nova chave de autenticação JWT

    php artisan jwt:secret

Crie um banco de dados vazio e coloque as credenciais de acesso no .env

Execute a migração das tabelas

    php artisan migrate --seed

Rode o servidor localmente

    php artisan serve

Agora você pode acessar o servidor em http://localhost:8000

### Front-end setup

Acesse o diretório do front-end

    cd intergalaxy-text-front-end
    
Instale as dependências

    npm install
    
Copie o arquivo .env de exemplo

    cp .env.example .env

Rode o projeto localmente
  
    npm run serve

Agora você pode acessar o projeto em http://localhost:8080

### Credenciais padrão de administrador:
- email: chapolin@gmail.com e senha: password
    
- email: clotilde@gmail.com e senha: password

### Credenciais padrão de prestador:
- email: chaves@gmail.com e senha: password

- email: chiquinha@gmail.com e senha: password

- email: madruga@gmail.com e senha: password

## Premissa

Criar um sistema de pagamento ao prestador
- Dashboard administrativo
- Login Admin
- Cadastro de prestadores
- Lançamento de horas trabalhadas por período
- Relatórios:
  - Total horas lancadas por prestador
  - Total horas lancadas por prestador por período 
  - Total horas geral por período
- Emissão de recibo prestador

## Solução

Dado o objetivo do teste foi desenvolvido uma aplicação com funcionalidades separadas para usuários **administradores** e **prestadores**.

Tanto a api quanto o front-end tem as rotas e funcionalidades protegidas por tipo de usuário.

### Administrador

O administrador tem acesso às horas de todos os usuários e pode visualizá-las filtrando por prestador e/ou data.

![Imgur](https://i.imgur.com/qbCQ2JX.gif)

O administrador também possuí a possibilidade de gerar um recibo em PDF para o prestador referente ao mês desejado.

![Imgur](https://i.imgur.com/wC1ySld.gif)

Caso o administrador queira é possível gerar novamente o mesmo recibo, o que causará uma recontagem do valor do mesmo.

![Imgur](https://i.imgur.com/nGdSZfr.gif)

Além disso, é possível baixar uma segunda via do último recibo gerado para a data selecionada.

![Imgur](https://i.imgur.com/IyMTJio.gif)

Por fim, o administrador pode visualizar, cadastrar, atualizar e deletar as horas de qualquer prestador utilizando o quadro de horas.

![Imgur](https://i.imgur.com/1WJSwsb.gif)

### Prestador

O prestador pode visualizar, cadastrar, atualizar e deletar somente as próprias horas.

![Imgur](https://i.imgur.com/tykP1wh.gif)

Pode também filtrar quantas horas ele trabalhou em algum período específico e baixar a segunda via de qualquer recibo gerado por um administrador em seu nome.

![Imgur](https://i.imgur.com/GtWPX7V.gif)

É isso! =)

## Licença
Esse projeto pode ser usado por qualquer pessoa! Licença MIT.
