#### Antes de começar esse lab, vou subir uma nova vpc e uma nova ec2. (já que encerrei as do último lab...)

### Passo 1 - acessando o EventBridge
- podemos acessar direto no campo de busca ou no painel do CW, indo em "events > rules"
![image](https://github.com/user-attachments/assets/f9b90cf6-1298-40b3-906c-46fc3f4d3581)
- após clicar em rules, somos direcioando ao Amazon EventBridge.
![image](https://github.com/user-attachments/assets/c9e83bf6-48b1-4ca6-bf59-e56afac25c87)

### Passo 2 - criando uma rule
- no E.B, só ir em "buses > rules > create rule"
![image](https://github.com/user-attachments/assets/2a560ced-ed44-490a-bae0-b452a628d573)
- no mapa mental, eu defini as rules type e as principais diferenças entre elas.
- neste lab, vamos usar a rule com um event pattern.
- em event pattern, vamos usar o use pattern from ( a diferença entre eles, também foi detalhada no mapa mental)
- no event source, vamos usar os serviços da AWS
- o serviço será EC2
- o tipo de evento será a mudança do estado da instância, tanto 'running' como 'stopped'
- e isso será atrelado para qualquer instância existente.
- em select targets:
-   nesse tópico, o que acontecer, vai gerar um target. por exemplo, se a instância começar a rodar ou parar, vai me enviar um SNS. mas existem outras várias opções, como chamar um Lambda, System Manager, SQS etc...
![image](https://github.com/user-attachments/assets/675a7461-f909-4160-8c30-f9204d3ddc23)
![image](https://github.com/user-attachments/assets/f735a28a-e345-4a99-966a-f852ade44089)
- neste lab eu não irei adicionar configurações adicionais.
![image](https://github.com/user-attachments/assets/2df335e7-aa29-41e8-9829-dba50dc96226)
- também não irei tags.
![image](https://github.com/user-attachments/assets/9c43bb02-659d-44e7-9a1b-5ef91d7d3514)
- geralmente as últimas etapas são apresentados os overviews do que foi feito.
- create rule!!
![image](https://github.com/user-attachments/assets/02eaa791-9f26-426d-a09c-9f9c2ab98b82)

### Passo 3 - vamos voltar no painel de instâncias
- aqui eu vou parar a única instância existente e ver se vou receber o email. (embora eu nao tenha nenhum sns configurado... utilizei o padrão.. acredito que ele vai vincular ao meu email automaticamente....vamos ver.)
![image](https://github.com/user-attachments/assets/ac35baf3-0b98-4228-bd1e-087193f10337)
- stopando a instância existente.
![image](https://github.com/user-attachments/assets/a4a66d19-53ce-4acb-94ed-3ed9e4368200)
- fui no SNS apenas verificar se realmente tinha configurado hehe!
![image](https://github.com/user-attachments/assets/5800bebf-4539-438c-8711-e243dbfe268e)
- e deu tudo certo. após stopar a instância, logo em seguida eu recebi a notificação.
- agora vamos iniciar ela novamente.
![image](https://github.com/user-attachments/assets/a6010ed1-5085-4804-b5e0-03a8549d2884)
- e em seguida, uma nova notificação da instância rodando:
![image](https://github.com/user-attachments/assets/693bcd41-7319-4aa6-813d-89cb098ef526)


> stay focused!




  
