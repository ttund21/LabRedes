# Cheat Sheet

## Router / Switch Layer 3

+  **enable** -> *entra no modo root;*
   + **show running-config** -> *vê as configurações;*
   + **show ip interface brief** -> *mostra info sobre as interfaces de rede;*
   + **show startup-config** -> *mostra as configurações de inicialização;*
   + **show ip route** -> *mostra as rotas;*
   + **write memory** -> *salva as configurações;*
   + **configure terminal** -> *ativa o modo de configuração;*
     + **interface [nome da interface]** -> *entra na interface para configura-la;*
       + **ip address [ip] [mask]** -> *add um ip para a interface;*
       + **no shutdown** -> *liga a interface de rede;*
       + **ip helper-address [ip do servidor DHCP]** -> *encaminha requisições DHCP para o servidor DHCP;*
       + **switchport access vlan [numero da vlan]** -> *muda a vlan da interface acessada <-- !!! COMANDO EXCLUSIVO SWITCH LAYER 3 !!!*
       + **switchport mode [access - trunk]** -> *muda a função da porta <-- !!! COMANDO EXCLUSIVO SWITCH LAYER 3 !!!*
     + **interface range [nome da interface] [range ex: 0/1 - 10]** -> *entra em um range de interface para configura-las;*
     + **interface loopback [numero]** -> *cria uma interface loopback;*
     + **do** -> *escala o previlegio para o root;*
     + **ip route [ip a ser roteado] [mask] [ip do roteador na mesma rede]** -> *roteamento estatico*
   + **router rip** -> *ativa o protocolo de roteamento RIP;*
     + **network [ip da interface]**-> *ativa as interfaces de rede para o compartilhamento RIP;*
     + **version [1 - 2]** -> *alterna a versão do RIP;*
   + **router ospf [id do processo]** -> *ativa o protocolo de roteamento OSPF;*
     + **network [ip da da rota] [mascara invertida, ex: 255.255.255.0 - 000.000.000.255] area [número da área]** -> *ativa o OSPF*
   + **ip access-list [standard / extended] [Nome da Acl]** -> *Cria uma variável de ACL para receber os parametros;*
     + **10 deny 192.168.0.0 0.0.0.255** -> *Bloqueia todos os host da interface 192.168.0.0 <--- !!! COMANDO DA ACCESS LIST STANDARD !!!*
     + **10 permit tcp 192.168.1.0 0.0.0.255 host 192.168.0.100 eq 80** -> *Permite o trafego do protocolo http da interface 192.168.1.0 para o host 192.168.0.100 <--- !!! COMANDO DA ACCESS LIST EXTENDED!!!;*

## Switch Layer 3

+ **enable** -> *entra no modo root;*
  + **show vlan brief** -> *mostra informações das intefaces vlans;*
  + **show interface trunk** -> *mostra as portas no modo trunk;*
  + **configure terminal** -> *ativa o modo de configuração;*
    + **ip routing** -> *liga a função roteador;*
    + **vlan [numero da vlan]** -> *liga a vlan e entra no modo de configuração da vlan;*
      + **name [nome]** -> *altera o nome da vlan;*
    + **no vlan [numero da vlan]** -> *desliga a vlan;*
    + **interface vlan [nome da interface]** -> *entra na interface para configura-la;*
      + **ip address [ip] [mask]** -> *add um ip para a interface;*
      + **no shutdown** -> *liga a interface de rede.*
