### Aqui vamos instalar o AWS CLI no SO local e configurar para acessar via CLI

#### Passo 1 - baixar o CLI para seu local host
- https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
- após baixado, vamos abrir o prompt de comando (ou terminal se for o caso.)

#### Passo 2 - Criar um novo lab-user para acessar via CLI
- Iam > user > create user

![image](https://github.com/user-attachments/assets/6f27ad96-6a22-4c6f-840b-ea8f5028d6d8)

- não vou habilitar o acesso da console. vamos dar um nome e dar next.
- irei atachar esse usuário ao grupo admcloud que criei.
- por fim, darei um create user.

#### Passo 3 - vamos crair uma access key
- Users > Security Credentials ..... vamos rolar até encontrar a opção Access Keys > Create access key

![image](https://github.com/user-attachments/assets/51231599-6f69-4e10-8e93-c27be15ed38c)
![image](https://github.com/user-attachments/assets/17e5fc46-b9d9-49bf-a019-a62c3077938f)

- aqui ele dá algumas opções de uso, vamos marcar a caixa que entendemos as recomendações e dar um next.

![image](https://github.com/user-attachments/assets/8e498342-3625-4bb3-b8ec-62989779dc71)

- não irei atribuir nada aqui.
- após isso, será gerado um ACCESS KEY E SECRET KEY.
- SALVE ESSES DOIS POIS IREMOS PRECISAR DELES PARA LOGAR VIA CLI!!!!

![image](https://github.com/user-attachments/assets/1e2264c6-5534-47ee-9d98-83bf1c0e3f80)

- após concluir o lab, esse user vai ser deletado, portanto, não vi problema compartilhar o access key :v
- também podemos realizar o download do .CSV !

### Passo 4 - acessando via CMD
- após já ter instalado o AWS CLI, criado o user iam cli, vamos abrir o CMD (no meu caso) e logar!
- no cmd, usar o comando:

> aws configure

- aqui ele vai pedir o access key, secret key, a região

![image](https://github.com/user-attachments/assets/11914ce9-fa36-49f6-b29a-2c47c288fcdf)
![image](https://github.com/user-attachments/assets/04e21f7a-c50d-40b7-a6da-03f61eeb3455)

### Passo 4 - extra no localhost
- as credenciais ficarão salvas no seu pc, dentro da pasta .AWS:

![image](https://github.com/user-attachments/assets/cc2b4eba-38ba-412b-88a2-29b8cd80f698)
![image](https://github.com/user-attachments/assets/c4d95763-07ab-4270-ba03-6d9dc6136444)
![image](https://github.com/user-attachments/assets/5f554a9a-9515-47fb-8e50-3d12f78806d3)

- caso seu pc seja hackeado, o ator de ameça poderá usar suas credenciais e ter acesso ao seu user.

> stay focused!!!






  


 
