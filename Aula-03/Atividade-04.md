**Atividade 4 – Visualização da Arquitetura da Rede Industrial**

<hr>

**DIAGRAMA:**

                         ┌──────────────────────────┐
                         │      Rede Corporativa    │
                         │   (ERP / Servidor SQL)   │
                         └─────────────┬────────────┘
                                       │
                              Firewall / Roteador
                                       │
                         ┌─────────────┴────────────┐
                         │   Switch Industrial Core  │
                         │   (Gerenciável – VLAN)    │
                         └───────┬─────────┬────────┘
                                 │         │
                    ┌────────────┘         └────────────┐
                    │                                   │
          ┌─────────┴─────────┐               ┌─────────┴─────────┐
          │  Switch Industrial │               │  Switch Industrial │
          │     Setor Prensa   │               │   Setor Secagem    │
          └─────────┬─────────┘               └─────────┬─────────┘
                    │                                   │
            ┌───────┴───────┐                   ┌───────┴───────┐
            │     CLP 1     │                   │     CLP 2     │
            │ (Produção)    │                   │  (Secagem)    │
            └───────┬───────┘                   └───────┬───────┘
                    │                                   │
        ┌───────────┼───────────┐           ┌───────────┼───────────┐
        │           │           │           │           │           │
     Sensores    Esteiras    Prensa      Sensores    Ventilação   Motores
   (Umidade)   Transport.  Hidráulica   Temperatura

                                 │
                         ┌───────┴────────┐
                         │   Servidor     │
                         │   SCADA        │
                         │ (Supervisório) │
                         └────────────────┘

                                 │
                         ┌───────┴────────┐
                         │      IHM       │
                         │ Operação Local │
                         └────────────────┘


Descrição Técnica da Arquitetura
🔹 1. Estrutura em Camadas

A arquitetura foi organizada em três níveis:

**Nível de Campo**
- Sensores (umidade, temperatura, vibração)
- Atuadores e motores
- 
**Nível de Controle**
- CLPs responsáveis pela automação dos setores
- Comunicação via Ethernet Industrial (ex: PROFINET)
- 
**Nível de Supervisão**
- Servidor SCADA
- IHMs para operação local
- Integração com banco de dados e ERP

<hr>

**Conexão com a Rede Corporativa**

- Interligação feita por firewall industrial
- Segmentação por VLAN
- Controle de acesso
- Possibilidade de integração futura com:
  - ERP
  - BI
  - Sistemas de manutenção
 
<hr>

**Possibilidade de Expansão Futura**

A arquitetura permite:

- Adição de novos CLPs
- Inclusão de novos switches industriais
- Ampliação do número de sensores
- Implementação futura de:
  - IIoT
  - Monitoramento remoto
  - Computação em nuvem
  Indústria 4.0

