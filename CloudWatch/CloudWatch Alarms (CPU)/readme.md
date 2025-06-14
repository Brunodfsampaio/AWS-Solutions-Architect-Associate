### Atenção
- como eu havia excluído todas as instâncias, vpc's entre outros, dos últimos labs, tive que criar novamente do zero.
- criei uma vpc com configurações padrões, 1 sub-pub / 1 sub-privada;
- criei uma ec2 padrão free tier
----


### Passo 1 - formas de acessar o monitoramento da instância...
1) No dashboard das instâncias, podemos ir em Actions > Monitoring and troubleshoot > Manage CloudWatch alarms
![image](https://github.com/user-attachments/assets/a5cc3c71-a855-4d32-9d7b-317659c91bd3)
![image](https://github.com/user-attachments/assets/a77491b8-a967-41d6-8534-f3e4a160e769)
1.1) e aqui você vai criar um alarme direciona à instância selecionada....

ou...

2) ir diretamente no serviço CloudWatch > Alarms > in alarm/all alarms > Create alarm
![image](https://github.com/user-attachments/assets/407dc3fc-2dce-45c8-bcf0-a710c6fc7f63)

### Passo 2 - criando alarme no CloudWatch
#### 2.1)
![image](https://github.com/user-attachments/assets/9df2db4c-2edd-4ac1-99c8-797c02143dfb)
- se você criou uma alerta de billing, sempre vai ter um alarme ativo na sua conta...
- após realizar os comandos: CloudWatch > Alarms > in alarm/all alarms > Create alarm. Começaremos com a edição do alarme.
![image](https://github.com/user-attachments/assets/481b81e3-5575-4be2-b1b7-5a3dcfb8a875)
- nessa etapa, vamos especificar qual o tipo de métrica do alarme...
![image](https://github.com/user-attachments/assets/65a4fe60-ec84-4295-b71e-b5437d3bfd48)
- no caso eu irei em EC2
- em seguida será exibido uma opção na qual iremos acessar:
![image](https://github.com/user-attachments/assets/0dc91768-dfda-4df6-a720-29697f68070c)
- e após acessar, vai aparecer várias métricas:
![image](https://github.com/user-attachments/assets/ca208ebc-4c46-4f86-8df2-19584d6ce8cf)
- apliquei um filtro "CPU" no search, para facilitar encontrar a opção "CPU utilization" e em seguida, vamos dar um "select metric"
![image](https://github.com/user-attachments/assets/b4789274-9a11-4b57-a0d4-bf87f1729aa8)
- para entender um pouco sobre a variação da opção "Statistic", visitar o mapa mental que eu compartilhei em labs passados...
- também podemos ver que podemos mudar o nome da métrica, é exibido o ID da instância...
![image](https://github.com/user-attachments/assets/2be43c9f-720e-4f68-8364-6b74b39d1aa2)
- e em seguida, temos os Conditions, que também vai estar melhor detalhado no mapa metal...
- no exemplo, vamos usar o threshol estático e sempre que a cpu for maior que 20%..... (continua nas configurações)
![image](https://github.com/user-attachments/assets/4ec764e5-4ef3-4f3d-84bd-84b808b49a60)
(não irei configurar configurações adicionais)

#### 2.2)
![image](https://github.com/user-attachments/assets/f0f2a886-f35b-42ef-a349-9571cf05ffde)
- na primeira parte vamos definir o estado de alarme que acionará a ação. no caso, vou deixar 'in alarm'
- se eu tivesse criado um tópico SNS com meu email (por exemplo), poderia adicionar nessa segunda parte, e sempre que fosse monitorado com as métricas definidas, eu receberia um email da ação.
![image](https://github.com/user-attachments/assets/37113916-36f4-41de-9e13-751998298e85)
- a primeira parte, temos reatividade de ação, nessa segunda, temos proatividade de ação, onde podemos escolher como os serviços poderão reagir a determinada métrica..
- aqui vamos manter uma ação em EC2 "EC2 action - add EC2 action"
![image](https://github.com/user-attachments/assets/c0a79be2-af90-436a-880e-1bea26fa3e62)
- aqui eu vou escolher para a EC2 'stopar' ao chegar naqueles 20% de CPU que eu configurei anteriormente...
- tentei continuar para próxima etapa, porém ele me exigiu configurar um notification...coloquei um padrão e já foi reconhecido meu email.
![image](https://github.com/user-attachments/assets/813bb9b1-3a91-498f-b744-23689b2e04b6)

- na página seguinte podemos adicionar uma descrição e em seguida vamos de next...
![image](https://github.com/user-attachments/assets/450839e3-bb18-4d9a-b03e-4c6a40930a02)

- na útima parte, será apresentada um overview de tudo que fizemos... é só clicar em 'create alarm'
![image](https://github.com/user-attachments/assets/1eab738f-c53d-4396-9017-d898abe50ee4)

### Passo 3 - stessar a instância
- vamos na instância, conectar via console, entrar no modo root e rodar o comando de stress.. 
> stress --cpu 8 --timeout 800 &
- se não der certo, reboota a instância!
- rode novamente e verá que a instância estará stopada!
![image](https://github.com/user-attachments/assets/f9c513f3-547e-4f56-b228-d820917a80cd)
![image](https://github.com/user-attachments/assets/6ffa2350-222d-4dd1-9c46-0a1bd3754dd8)
![image](https://github.com/user-attachments/assets/7239fceb-0d57-47b9-a46a-3eb30a38c20b)
- deveria ter ficado "! - in alarm' porém, ele foi logo para 'insufficient data'...
![image](https://github.com/user-attachments/assets/cd5dd4e4-2461-4b73-a738-f35f5aec3af1)
- email recebido do cloudwatch sobre a ec2 stopada!

> stay focused!












