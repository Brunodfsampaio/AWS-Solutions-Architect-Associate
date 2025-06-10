## Neste lab, eu vou criar um bucket, fazer um upload de um arquivo e configurar regras para que ele possa ser acessado via browse.
---

### Passo 1: Criar o bucket
- na aba de buscas, procurar a feature S3 e entrar nela.
![image](https://github.com/user-attachments/assets/6dedba6f-07c8-4cc3-af79-926d9ed8d7c1)
-depois vamos criar um bucket...
![image](https://github.com/user-attachments/assets/e7e14dd8-516d-4066-b8db-502c8609a818)


### Passo 2: Criando o bucket
![image](https://github.com/user-attachments/assets/4801b8b9-db18-48a4-bda6-19c6dfcefa4c)
- podemos escolher os dois tipos: Uso Geral e Diretório.
- Perceba que a Região do bucket já está definida (Us-East-1)... para alterar, é só ir 'lá em cima' e alterar a região....

*Propósito Geral: Maior durabilidade, mais caro (dependendo do tipo), ideal para dados críticos ou com alta demanda de disponibilidade.
*Diretório: Mais barato, baixa latência, mas com menor durabilidade (armazenamento em uma única zona de disponibilidade), ideal para dados de acesso esporádico e menos críticos.

- A opção de "Copiar configurações do bucket existente" serve para facilitar a criação de um novo bucket com configurações semelhantes a um bucket já existente.
- Ou seja, se você já tem um bucket configurado com determinadas regras, permissões, ou configurações (como políticas de acesso, versão de objetos, cifras de segurança, etc.), você pode simplesmente copiar essas configurações para o novo bucket, sem precisar recriar tudo manualmente.

- ![image](https://github.com/user-attachments/assets/01f7014a-7eab-4037-951f-f102fa8a7ccd)

#### Ponto 1- Propriedade de objeto
- Essa opção se refere a como o acesso aos objetos dentro do seu bucket será controlado, principalmente no que diz respeito à propriedade dos objetos e ao uso das listas de controle de acesso (ACLs).

- ACLs desabilitadas (Recomendado):
-    Todos os objetos gravados no bucket serão considerados como propriedade da sua conta da AWS. Ou seja, a conta que criou o bucket terá controle total sobre todos os objetos, independentemente de quem os tenha carregado (ou seja, mesmo que outras contas da AWS carreguem objetos nesse bucket, esses objetos pertencem à sua conta).
-    Controle de acesso: O controle de acesso aos objetos será feito **exclusivamente por meio de políticas do IAM (Identity and Access Management) ou políticas de bucket do próprio S3.
-    Recomendação: Essa é a opção mais segura e recomendada pela AWS porque permite um controle mais consistente e robusto de acesso, sem a complexidade adicional das ACLs.

- ACLs habilitadas
-    Os objetos podem ter proprietários diferentes, ou seja, outros usuários ou contas da AWS podem ser considerados proprietários dos objetos dentro do seu bucket. Nesse caso,
-    Além das políticas do IAM e de bucket, você pode usar ACLs (listas de controle de acesso) para especificar quais usuários ou contas da AWS podem acessar os objetos e com que permissões. As ACLs permitem um controle mais granular
-    Essa opção é útil se você precisar que outros usuários ou contas tenham controle sobre os objetos que eles mesmos carregaram no seu bucket

#### Ponto 2- Configurações de bloqueio de acesso público do bucket
- a descrição já fala por si.

![image](https://github.com/user-attachments/assets/e0c20280-f51d-42b6-a058-5e7eb9f2ba57)

#### Ponto 3- Versionamento
- O versionamento permite que você guarde várias versões de um mesmo arquivo no seu bucket, de forma que cada vez que você carregar (ou atualizar) um objeto, o S3 cria uma nova "versão" desse objeto. Com isso, você pode:
-   Preservar e restaurar versões anteriores de um objeto, mesmo após modificações ou exclusões.
-   Recuperar arquivos deletados ou corrompidos acidentalmente.
-   Rastrear mudanças no tempo, especialmente útil em sistemas que sofrem modificações frequentes.

- Custo: Embora o versionamento ofereça ótimos benefícios, ele pode aumentar os custos de armazenamento, pois o S3 irá armazenar todas as versões de cada objeto. Isso pode ser um problema se você tiver muitos objetos atualizados frequentemente.
- Controle de versões: Você pode gerenciar como as versões são excluídas. Por exemplo, você pode definir uma política de expiração de versões antigas ou usar regras de ciclo de vida para excluir versões antigas automaticamente após um certo tempo.

#### Ponto 4- tag
isso já deve ser claro, para nível SAA.

#### Ponto 5- Cripto
- Quando você armazena dados no Amazon S3, a criptografia no lado do servidor (SSE, do inglês Server-Side Encryption) significa que os dados são criptografados automaticamente quando são gravados no S3 e descriptografados automaticamente quando são acessados, sem que o usuário precise fazer nada. Essa criptografia protege os dados durante o armazenamento no S3, garantindo que somente quem tem a chave de descriptografia possa acessar os dados.
- para mais informações sobre todos eles, ir no meu mapa mental... lá vai ter um detalhamento melhor. (https://mm.tt/map/3599935352?t=2RKK6F7kzT)

![image](https://github.com/user-attachments/assets/7f295006-528c-4efd-ac98-bd05439e6787)
- permite que você proteja dados críticos contra alterações ou exclusões acidentais ou maliciosas. O recurso implementa o modelo WORM (Write Once, Read Many), onde os dados são gravados uma vez e podem ser lidos várias vezes, mas não podem ser modificados ou apagados durante o período de retenção.
- pode gerar custos extras!

---

### Passo 3: Após o bucket criado, vamos acessar ele e fazer upload de um arquivo....
![image](https://github.com/user-attachments/assets/f22b5a3d-38f7-4f6d-92ff-47e4401f591a)
![image](https://github.com/user-attachments/assets/1c9b6657-a663-4bf5-94ef-2e1828566e5c)
![image](https://github.com/user-attachments/assets/5d8f67ef-6d5f-4d1b-b1db-78dffdda4aec)
![image](https://github.com/user-attachments/assets/01118c75-2029-4942-994c-b2745932fa00)
- podemos ver que no upload do arquivo, podemos escolher qual a classe que ele vai ficar....

![image](https://github.com/user-attachments/assets/df3398bc-2d5e-4127-93c4-c16a37068ed3)
- verificar sobre Checksum no mapa mental. (vale a pena!)

---

### Passo 4: alterando o bloqueio de acesso público do bucket
- alteração para que o acesso externo (via URL) possa ser completado...
![image](https://github.com/user-attachments/assets/2d3cd62d-7eaf-490f-946f-6c0d2c886dde)
- podemos ir em "EDITAR", dentro das opções, podemos desabilitar o botão 'bloquear todo o acesso público' e depois salvar.
![image](https://github.com/user-attachments/assets/f666adba-9287-4068-b07b-1cc2a5e52905)
- confirme a alteração.
![image](https://github.com/user-attachments/assets/9515d606-5ed9-40f0-b0e3-4a4cfe8f90e9)

----

### Passo 5: tentando acessar o arquivo...
- após liberar o bucket, possivelmente o arquivo ainda não esteja pronto para acesso público, para testar, vamos copiar o URL de objeto, colar no browser e ver se ele vai acessar...
![image](https://github.com/user-attachments/assets/707db7ae-4694-49c2-8991-f07c63fbcd88)
- como já previsto, o acesso ao objeto está bloqueado...vamos acessar a configurações para acessar ele.
![image](https://github.com/user-attachments/assets/9d815488-09b8-4263-8af9-98dce5487124)

- o passo é ir no objeto que fiz o upload, e clicar nas regras impostas que estão aplicadas:
![image](https://github.com/user-attachments/assets/e39e2f4b-6f43-4c31-9893-23dc76d284bd)

- depois vamos escolher ACLs habilitadas, clicar que reconhece que as ACLs serão restauradas e manter o autor do objeto. após isso, poderemos alterar as permissões do objeto:
![image](https://github.com/user-attachments/assets/8147a675-3616-4d85-968d-ae7dc41a30d0)

- a opção vai estar disponível para edição
![image](https://github.com/user-attachments/assets/3ff3969b-692d-467a-b827-9dc981be47c4)

- vamos habilitar o READ para todos e depois clicar que compreende os efeitos....depois é só salvar.

### Passo 6: acesso ao arquivo via URL
![image](https://github.com/user-attachments/assets/cd58ce9a-ed08-4028-8df7-e292c7b9d296)
![image](https://github.com/user-attachments/assets/16a9f28a-44ce-4a7f-ae32-894674684e44)

concluído!





stay focused!









  
