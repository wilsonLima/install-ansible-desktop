install-ansible-desktop
=========

Role do Ansible para instalação da ferramenta Ansible em uma máquina remota.

Distribuições Suportadas pela Role
------------

- Fedora 29 ou superior          
- Linux Mint LMDE 3 ou superior  
- Linux Mint 18 ou superior      
- openSUSE Leap 15.0 ou superior 
- openSUSE Tumbleweed            
- Ubuntu 18.10 ou superior       


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.
- deps: Instala as dependências essenciais para o Ansible.
- repo: Adiciona os repositórios do Ansible.
- ansible: Realiza a instalação do pacote Ansible, via instalador Pip no openSUSE ou package manager em outras distribuições.
- directory: Cria os diretórios onde ficam os playbooks, roles e outros componentes do Ansible.
- config: Realiza a configuração de pós instalação do Ansible.


Variáveis da Role 
--------------

- home_dir: Diretório home para a criação dos diretórios de desenvolvimento. Valor padrão, o HOME do usuário linux utilizado no inventário.
- root_env_dir: Especifica um diretório customizado onde ficam os playbooks, roles e outros componentes do Ansible. Variável opcional, exemplo de valor: /opt
- timeout_value: Representa o valor de timeout na conexão SSH, em segundos. Valor padrão: "30".

Example Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: servers
      roles:
         - install-ansible-desktop

Exemplo de uso da Role, com diretório customizado:

    - hosts: servers
      roles:
         - { role: install-ansible-desktop, root_env_dir: "developer" }

Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "config" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, config"


License
-------

MIT