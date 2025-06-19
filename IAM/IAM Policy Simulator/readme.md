### IAM Policy Simulator

#### Passo 1 - acessando a console
- link para acesso: https://policysim.aws.amazon.com
- se você estiver logado na console da AWS, automaticamente ele vai reconhecer o usuário no simulador.

![image](https://github.com/user-attachments/assets/03225f9e-4ddc-4980-9f3b-6c19f9acbe25)

- neste exemplo vamos verificar o recurso S3 e criação de bucket para um determinado usuário

![image](https://github.com/user-attachments/assets/9332760f-a239-4d2f-89c0-e37f755084ca)

- após, vamos clicar no usuário que você desejar testar.
- caso esse user já tenha políticas atachadas nele, elas serão exibidas.
- run simulator !

![image](https://github.com/user-attachments/assets/89f99a08-9cb7-4ac9-9827-55d2a47e6c65)
![image](https://github.com/user-attachments/assets/b794e641-d63f-428f-a75a-d37735ba4118)

- como esse meu usuário tem permissão de Administrator Access, ele possui permissão para criar bucket!
- vale ressaltar que existe um botão de "Create new policy" onde podemos criar uma nova política, editando um JSON para atrelar ao user em teste. 

> stay focused !

  
