# Comandos GPON

## Alterar a senha do usuário corrente
iSH> ```changepass intelbras```

## Parar queda do terminal
iSH> ```timeout off```<br />
iSH> ```log session off```

## Adicionar modo debug ao usuário
iSH> ```updateuser <usuário>```

## Verificar if_index da interface
iSH> ```showlinestatus 1/1/1/1/gpononu```

## Verificar Uptime e informações da OLT
iSH> ```shelfctrl monitor```<br />
iSH> ```card stats all```<br />
iSH> ```ata info```<br />
iSH> ```slots 1```

## Verificar GEM Ports/allocId
iSH> ```iSH> gpononu gemport```

## Criando linkagg LACP 
iSH> ```linkagg add group LAG-1/linkagg link 1-1-10-0/eth mode active```<br />
iSH> ```bridge add LAG-1/linkagg uplink vlan 90 untagged```<br />
iSH> ```linkagg show```<br />
iSH> ```lacp monitor 2```

## Verificar status das portas PON
iSH> ```gponolt show port```<br />
iSH> ```port stats 1-1-1-0/gponolt```<br />
iSH> ```sfp show 1-1-2-0/gponolt```<br />
iSH> ```xfp show 1-1-10-0/eth```

## SNMP
```new community-profile 1```

(...)<br />
community-name: ------> {}: ```public```<br />
(...)<br />

## Provisionamento offline
iSH> ```gpononu set 1-1-1-35 meprof intelbras-110g vendorid ZNTS serno fsan 035GY2FX```

## Descrição portas
iSH> ```port description add 1-1-2-0/gponolt blablabla```<br />
iSH> ```port description list 1/1/10```

## Transferir arquivos OLT via TFTP
iSH> ```file upload 10.1.31.122 consolelog1.txt consolelog1.txt```

## Ativar opções de log

##### 1. Habilitar usuário no modo debug
iSH> ```updateuser intelbras```<br />

Please provide the following: [q]uit.<br />
(...)<br />
debug: ------->  {no}: ```yes```<br />
(...)<br />

##### 2. Habilitar log permanente. 
iSH> ```update system 0```<br />
(...)<br />
persistentLogging: --->  {disabled}: ```enabled```<br />
(...)<br />

##### 3) Habilitar todas as opções no log
iSH> ```log option all on```

## Visualizar arquivos OLT
iSH> ```consolelog display podex_ler.txt```

## Deletar arquivos OLT
iSH> ```del podex_ler.txt```

## Adicionar servidores DNS
zSH> ```new resolver 1```<br />
Please provide the following: [q]uit.<br />
(...)<br />
first-nameserver: --> {0.0.0.0}: ```192.168.8.21```<br />
(...)<br />
