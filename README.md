# Criação de servidor para deploy

Será necessário ter algum programa que permite a criação de máquinas virtuais (vms). Eu usei o VMWare, mas pode usar o VirtualBox ou qualquer outro.

Baixe um arquivo que servirá como imagem da máquina virtual. Basta baixar uma ```iso``` que seja baseada em linux. Utilizei nesse exemplo o Ubuntu 20.04 LTS.

# Configurações iniciais

A máquina virtual deve ter a rede configurada em modo ```Bridge```.

Faça pesquisas e análises para que a vm funcione adequadamente.

# Inicie a máquina virtual...

Teste conexão com a vm utilizando do ```ping``` no terminal, caso não haja conexão pode ser que a vm tenha mudado a rede para modo NAT, seja qual for o problema, certifique-se de corrigir para continuar.

Para testar a conexão, abra o terminal na vm e digite o comando ```ip address show``` e salve o endereço de ip (pode encontra-lo com o comando ```ifconfig``` também, mas terá que executar ```sudo apt install net-tools``` primeiro). Na sua máquina, digite ```ping <endereco_de_ip_da_vm>``` para o teste.

# Instalação do servidor ssh

Verifique se a vm tem conexão com a internet executando o comando ```ping 8.8.8.8``` no terminal.

Atualize o repositório: ```sudo apt-get update```. (Adeque o comando para o teu sistema operacional)

Instale o servidor ssh: ```sudo apt install ssh```.

# Acesso por ssh

No terminal da sua máquina, crie a chave ssh pela qual fará a conexão com a vm, basta executar:
```ssh-keygen -f ~/.ssh/<nome_da_chave_ssh> -t rsa -b 4096```

Copie todo o conteudo da chave gerada na sua máquina e cole em um arquivo na vm chamado "authorized_keys". Utilize ```nano ~/.ssh/authorized_keys``` para criar e abrir o arquivo e tecle Ctrl+Shift+V para colar.

Na sua máquina, execute ```ssh <nome_de_usuario_da_vm>@<ip_da_vm>``` e verifique se conseguiu fazer a conexão. Caso tenha obtido sucesso, você acaba de criar seu servidor para deploy.




<h3>Repositório em construção...</h3>


<img src='./loading.gif' />
