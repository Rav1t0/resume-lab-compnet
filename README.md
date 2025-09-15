# resume-lab-compnet
Resumo das lições aprendidas no laboratório de Computação e Rede do bootcamp "Microsoft Azure AZ-900" na DIO

## Introdução
Este repositório contém anotações, dicas e práticas relacionadas à máquinas virtuais do Azure. O Objetivo é entender como configurar recursos, dimensionamentos e boas práticas ao trabalhar com Máquinas Virtuais na Azure.

## Resumo
Entendemos como utilizar outras formas de criação e gerenciamento de máquinas virtuais no Azure.

- Máquina Virtual do Azure: criar uma VM hospedada pela Azure
- VM com configuração predefinida: VM com predefinições com base em suas cargas de trabalho (ex. produção ou teste)
- VMs e soluções relacionadas: implanta cargas de trabalho completas e produtos do Azure para suas necessidades de negócios.

---

## Passo a Passo dos Recursos

### **Máquina Virtual - Virtual Machine (VM)**
  1. Clique em Create a Resource > "Virtual Machine" > Create
  2. Selecione:
    - Assinatura
    - Resource Group ou criar novo
    - Nome da Virtual Machine
    - Região
    - Opções de disponibilidade:
       - Nenhuma redundância infraestrutura necessária: não adiciona datacenters extras.
       - Zona de disponibilidade: define redundância por zona
    - Zona de disponibilidade: define quantas zonas terá o servidor, caso caia uma Zona, terá mais 1 ou 2 disponíveis.
    - Imagem
    - Tamanho
  4. Na seção de Rede (Networking): Selecione a rede criada anteriormente ou crie uma nova
  5. Clique em Next
    - Preencha as demais configurações, se desejado.
  6. Clique em "Review + create" > Create\

  - **Ponto de dica:**   
    Se não for necessário acesso público, desabilitar a criação de IP Público e usar apenas rede privada ou VPN, ou se for necessário, marcar IP Público, caso contrário, só será possível o acesso por meio de VPN.
    
  - **Ponto de atenção:**   
    Ao excluir a VM, confirmar se também excluiu discos, IPs e serviços associados. Esses recursos podem gerar cobrança.

---

## Recursos Avançados

### Conjunto de Dimensionamento de VMs (VM Scale Set)
- Permite criar várias instâncias de VMs idênticas.  
- Ideal para cenários de alta disponibilidade e balanceamento de carga.  
- Suporta dimensionamento automático, aumentando ou reduzindo a quantidade de VMs de acordo com a demanda.  

### Tipos de Instâncias
- Contagem fixa: define manualmente o número de instâncias.  
- Dimensionamento automático (autoscale): cresce ou reduz conforme CPU, memória ou métricas definidas.  

### Desconto de Spot no Azure
- Usado para workloads que podem ser interrompidos.  
- Oferece custo muito menor, mas a VM pode ser desalocada quando o Azure precisar dos recursos.  

---

## Segurança e Boas Práticas

- Portas de entrada:
  - Evitar definir como RDP para ambientes de produção, e evitar expor portas diretamente para internet.
  - Preferir VPN.
 
- Desligamento Automático (Auto-Shutdown):
  - Para evitar cobranças desnecessárias. Porém não há o start necessário pro início do período de uso.

- Extensões
  - Permitem instalar softwares na VM

---

## Área de Trabalho Virtual do Azure (Azure Virtual Desktop (AVD))

O Azure Virtual Desktop fornece acesso a desktops e aplicativos virtuais na nuvem.  

- Tipos de Pool:  
  - Pooled: vários usuários compartilham a mesma VM, ideal para reduzir custos.  
  - Personal: cada usuário tem uma VM dedicada, garantindo maior personalização.  

- Utilidades:  
  - Ambientes de trabalho remotos seguros.  
  - Suporte a trabalho híbrido ou remoto.  
  - Redução de custos em comparação com desktops físicos.  

---

## Anotações Úteis

- Sempre organizar os recursos em Resource Groups diferentes para facilitar exclusão.  
- Lembrar de excluir discos SO, IPs públicos e NICs após remover uma VM.  
- Preferir máquinas de teste com Spot para reduzir custos.  
- Evitar exposição direta de portas críticas à internet.  
- Configurar shutdown automático em ambientes de aprendizado ou teste.  

---
