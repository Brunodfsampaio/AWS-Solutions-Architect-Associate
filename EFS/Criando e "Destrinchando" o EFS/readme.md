#### Segundo a AWS: 
-Como parte do Nível gratuito da AWS, você pode começar a usar gratuitamente o EFS. Após a inscrição, os novos clientes da AWS recebem 5 GB de armazenamento no EFS Standard com um sistema de arquivos regional por 12 meses. O Nível gratuito da AWS não é aplicável a arquivos armazenados no tipo de sistema de arquivos de armazenamento One Zone. 
- Na pasta do Practitioner, dentro do "AWS Zero to Hero" existe 2 labs sobre EFS, vale a pena conferir antes de ler tudo isso...
---

### Passo 1 - localizando o EFS na console e criando o EFS do zero...
![image](https://github.com/user-attachments/assets/97881866-47ed-4dd8-8911-56c27ba6e5d9)

### Passo 2 - overview geral
![image](https://github.com/user-attachments/assets/8aa29a9d-e31e-4982-a8f3-773bc0325518)
- depois vamos em criar o sistema de arquivos.

### Passo 3 - criando...
- vale lembrar que o EFS é um storage elástico baseado em NFS (Network File System);

![image](https://github.com/user-attachments/assets/412200ca-2b25-4d80-9895-44a8487f7c55)
- podemos perceber que é necessário atrelar ele à uma VPC. Como eu exclui todas as VPCs, não vai aparecer nenhuma... Pelo fato dele ser baseado em NFS, vemos o motivo dessa exigência.
- em seguida, vamos na opção "PERSONALIZAR".

![image](https://github.com/user-attachments/assets/559439c7-9dff-4c60-ad2b-b4794492c114)
- entre o 'Tipo do sistema de arquivos" temos 2 opções: REGIONAL e ONE Zone - como a descrição já podemos ver que isso vai se tratar sobre Alta Disponibilidade e Custo.
- Regional vai estar em todas as AZ's da região.
- One Zone em apenas uma AZ.
- Na opção de backups automáticos, a descrição já é explicativa. Lembrando que ela ativada, poderá gerar custos extras. $$$$

![image](https://github.com/user-attachments/assets/04ad6114-53c6-4cb7-8bd7-7af879ba0497)
- Política do life cycle dos dados (transição entre classes - economia de custos etc...)
- O EFS vai usar o Intelligent Tiering (ML), onde o  dado vai estar no modelo Standart. Na primeira opção podemos mudar para classe IA de acordo com os dias estabelecidos... em seguida uma transição para a classe Archive e por fim a transição de volta para o Standart, que poderá estar desativada (Nenhum) ou a partir do primeiro  acesso.
- Na opção de Chave do KMS, permite que você personalize a criptografia do seu sistema de arquivos Amazon EFS usando uma chave do AWS KMS (Key Management Service).
-   O Amazon EFS pode criptografar os dados armazenados no sistema de arquivos para garantir segurança.
-   Você pode escolher uma chave gerenciada pelo AWS KMS em vez da chave padrão do serviço. Isso dá mais controle sobre a criptografia e quem pode acessar os dados.
-   Se você já tem uma chave KMS criada, pode inserir o ARN (Amazon Resource Name) ou o ID da chave para usá-la.
-   Caso não tenha uma chave KMS disponível, pode criar uma nova diretamente na AWS.

![image](https://github.com/user-attachments/assets/9a75cffc-ca91-42f9-bf37-bbce093e3758)
![image](https://github.com/user-attachments/assets/83e47804-a773-41b1-9b4e-3f66c8da313b)
![image](https://github.com/user-attachments/assets/b11ac707-472b-4962-b11b-7f9074eb31f9)
- O modo de taxa de transferência no Amazon EFS define como o throughput do sistema de arquivos será gerenciado.
- Avançado (Enhanced): Oferece mais flexibilidade e throughput mais alto para workloads com requisitos variados de desempenho.
- Intermitente (Bursting): Ajusta automaticamente o throughput com base na quantidade de armazenamento, ideal para workloads com demandas básicas. 
- Elastic (Recomendado): Perfeito para workloads imprevisíveis, pois ajusta o desempenho automaticamente conforme a atividade. Você paga apenas pelo throughput usado
- Provisionado: Melhor para workloads com requisitos previsíveis. Você define um valor fixo de throughput e paga por ele, independentemente do uso
> Se sua workload tem picos imprevisíveis de uso, o Elastic Throughput pode ser a melhor escolha. Já se você consegue estimar a demanda, o Provisionado pode ser mais eficiente em termos de custo.

- Nas configurações adicionais, podemos escolher entre Uso Geral ou E/S máxima
- Uso geral (Recomendado) ou General Purpose: Ideal para a maioria das workloads, incluindo aplicações de alta performance e sensíveis à latência. Esse modo oferece baixa latência por operação, tornando-o adequado para workloads que exigem respostas rápidas.
- E/S máxima (MAX I/O): Projetado para workloads altamente paralelizadas que podem tolerar latências mais altas. Esse modo permite maior taxa de operações simultâneas, sendo útil para sistemas que realizam muitas operações de leitura/escrita ao mesmo tempo

- próxima página....
![image](https://github.com/user-attachments/assets/a4b82143-2781-4fd7-b80d-b6a7bb34b439)
- relacionar à uma vpc existente.
- como eu não tenho nenhuma vpc, nao vai aparecer a opção, mas.......
- quando voce selecionar, vai abrir as opções da AZ's atuais disponiveis da sua VPC de acordo com a região escolhida para ela.
- Os destinos de montagem no Amazon EFS são interfaces de rede elásticas que permitem que instâncias dentro da sua VPC acessem o sistema de arquivos via NFSv4.
- próxima página...

![image](https://github.com/user-attachments/assets/8a1f1ece-2aea-4461-9b8b-07c7c81d1091)
- aba para habilitar políticas de acesso ou IAM.

![image](https://github.com/user-attachments/assets/8ff65393-5d7a-473a-9d00-bb09fcf97c7f)
- por fim, voce vai ter um dashboard de revisão.
- só criar.

> stay focused.






