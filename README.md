# Amazon Elastic Compute Cloud - EC2
O EC2 oferece uma capacidade de computação escalável sob demanda na AWS, sendo assim, um serviço tipo IAAS (Infraesctruture as a Service). É possível usar o Amazon EC2 para executar quantos servidores virtuais forem necessários, configurar a segurança e as redes e gerenciar o armazenamento. É possível adicionar capacidade (aumentar a escala verticalmente) para lidar com tarefas de computação pesada, como processos mensais ou anuais ou picos no tráfego do site. Quando o uso diminui, você pode reduzir a capacidade (reduzir a escala verticalmente) de novo.

Uma instância do EC2 é um servidor virtual na Nuvem AWS. Quando executa uma instância do EC2, o tipo de instância que você especifica determina o hardware disponível para sua instância. Cada tipo de instância oferece um equilíbrio diferente entre recursos de computação, memória, armazenamento e rede.
<img width="831" height="219" alt="instance-types" src="https://github.com/user-attachments/assets/5f11ff9c-74e9-4b8f-8f06-e636f5b03b5f" />

Cada tipo de instância oferece diferentes capacidades de computacção memória e armazenamento, e está agrupada em uma família com base essas capacidades. Uma instância EC2 é composta por CPU, Memória, disco, rede e sistema opercional. Escolher a instância correta na AWS é crucial para garantir eficiência, escalabilidade e economia nos gastos com nuvem. <img width="2501" height="105" alt="image" src="https://github.com/user-attachments/assets/0b26cb91-473f-422a-a9e7-1cbd62d9ff5c" />

Tipos de Instâncias: 
1. General Purpose - Fornece de forma balanceada recursos de computação, memória e rede. Ideis para recursos de servidores, rpositórios de códico, e quando não se tem certeza dos recursos do workload.
2. Copute Optimized - Ideias para tarefas que usem mutos recursos de compução, como servidores de jogos, compução de alto desempenho, aprendizado de máquina, e modelagem científica.
3. Momory Optimized - Muito usada para recursos que precisem processar grandes de base de dados. 
4. Accelerated Computing - Usam recusros de hardware com GPU para processar de forma eficiente tarefas como, calculo de pontos flutuantes, processamento de gráfico e aprendizado de máquina
5. Storage Optimized - Ideal para tarefas qque exijam performace para armazenamento de dados, como armazenamento de grandes bancos de dados, data warehousing, e aplicações com grande quantidade de I/O.
   
![WhatsApp Image 2025-09-06 at 22 17 45](https://github.com/user-attachments/assets/56786e99-8bb4-457c-9748-ab42724650ce)

1. Sob Demana - São compradas a uma taxa fixa por hora e são recomendadas para aplicativos com cargas de trabalho irregulares de curto prazo que podem ser interrompidas. Elas também são adequadas para uso durante o teste de desenvolvimento de aplicativos no EC2.
2. Instâncias Reservadas - Costumam ser mais baratas que as instâncias sob demanda, mas você precisa pagar o ano inteiro de uso. É uma desvantagem para que não precisa usar a instância com frequência. Precisa pagar por 1 ou 3 anos. 
3. Instâncias Spot - Garante a disponibilidade das aplicações sob demanda com descontos de até 90%. A desvantagem das instâncias SPOT é que elas podem ser encerradas pela Amazon Web Service (AWS) a qualquer momento, com um aviso de dois minutos.
4. Savings Plans - Pode ser 72% mais baratos, mas também precisa assinda de 1 a 3 anos
5. Hosts Dedicados - POssível reservar um servidor inteiro para uso exclusivo, esta opção oferece controle completo e é ideal para trabalhos com necessidades de segurança restita
6. Instâncias Dedicafas - Hardware dedicado para a conta, de formaa ter o recurso isolado de outros clientes da AWS.

Aqui está sua anotação reorganizada, revisada e com as lacunas preenchidas. Formatei em **Markdown** e corrigi erros de digitação, mantendo a clareza e o objetivo de estudo:

---

# 📌 EBS vs S3

## **Amazon EBS – Elastic Block Store**

* Fornece **armazenamento em bloco** (volumes, como se fossem HDs virtuais).
* Pode ser anexado a uma instância do **EC2** (como se fosse uma outra partição de um computador com dual boot).
* Tem **expansão rápida** de capacidade.
* Projetado para uso com instâncias em execução.

**Exemplos de uso:**

* Armazenamento de **banco de dados**.
* Armazenamento de aplicações que precisam de **baixa latência e alta performance**.

**Snapshots:**

* Os **snapshots** do EBS são cópias pontuais de um volume.
* Esses snapshots são armazenados no **Amazon S3**.
* Podem ser usados para:

  * Criar novos volumes EBS.
  * Fazer backup e restauração.
  * Garantir durabilidade dos dados.

**Custos:**

* Custos variam conforme a **região**.
* Pago pelo volume provisionado e pelo snapshot armazenado.

---

## **Amazon S3 – Simple Storage Service**

* Serviço de **armazenamento de objetos**.
* Escalável, durável e econômico.
* Ideal para armazenar **arquivos, backups, logs, imagens, vídeos** e **dados não estruturados**.

**Exemplos de uso:**

* Movimentação de arquivos.
* Disparar **AWS Lambda** a partir de eventos (ex.: upload de um arquivo).
* Data Lake e integrações com análise de dados.

**Classes de Armazenamento:**

* **S3 Standard** – acesso frequente.
* **S3 Standard-IA (Infrequent Access)** – acesso eventual.
* **S3 One Zone-IA** – acesso eventual em uma única zona.
* **S3 Glacier** – arquivamento de longo prazo, baixo custo, recuperação em horas.
* **S3 Glacier Deep Archive** – arquivamento de longo prazo, menor custo, recuperação em até 12 horas.

**Vantagens:**

* Economia de custos.
* Altamente disponível e durável.
* Paga apenas pelo uso (pay-as-you-go).

---

## **AMI – Amazon Machine Image**

* É uma **imagem pré-configurada de máquina virtual**.
* Inclui:

  * Sistema operacional.
  * Servidor de aplicações.
  * Aplicações e configurações necessárias.

**Criação das AMIs:**

1. Podem ser criadas a partir de instâncias **em execução ou paradas**.
2. Podem ser **públicas** (compartilhadas) ou **privadas**.
3. Podem ser **personalizadas** (instalar softwares, ajustar configurações).
4. São usadas para **iniciar novas instâncias EC2**.
5. Podem ser de diferentes **tipos** (Linux, Windows, com ou sem ferramentas adicionais).

---

## **EBS x AMI**

* **EBS:**

  * Armazenamento em bloco.
  * Funciona como “disco rígido virtual”.
  * Usado para dados persistentes de uma instância.

* **AMI:**

  * É uma imagem pronta para gerar instâncias EC2.
  * Inclui sistema operacional + configurações.
  * Funciona como “foto” da máquina inteira, não apenas do disco.

---
# Arquitetura Proposta 

A arquitetura utiliza o Amazon S3 como repositório central de dados, funcionando como Data Lake. Arquivos brutos são armazenados em buckets específicos e, a cada novo upload, um AWS Lambda é acionado para realizar validações, transformações leves ou movimentação dos dados entre camadas de armazenamento (raw → processed).

Para cargas de trabalho mais intensivas, é utilizada uma instância Amazon EC2, configurada a partir de uma AMI personalizada com as dependências necessárias. Essa instância conta com Amazon EBS como volume de armazenamento em bloco, fornecendo alto desempenho de leitura e escrita para o processamento em batch.

Os dados processados retornam ao Amazon S3, agora organizados em camadas analíticas, podendo ser consumidos por serviços como Amazon Athena ou QuickSight.

Essa solução combina escalabilidade (S3), processamento automatizado (Lambda), flexibilidade computacional (EC2) e desempenho em armazenamento de bloco (EBS), atendendo diferentes necessidades de um pipeline de dados.
<img width="748" height="277" alt="arquitetura Ec2 drawio (1)" src="https://github.com/user-attachments/assets/efb99c15-d0b3-43f5-a712-1a8eba73663b" />




