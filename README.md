PROXMOX VE 8.2-1

Instalação do Sistema de Virtualização Proxmox
# Baixar ISO da última versão estável no site.
# Criar um Pendrive Bootavel. 
# Colocar 2 hds no servidor um para instalar o proxmox
  e outro criar o storage para as vms. 
# Install Proxmox VE (Graphical).
      
Apos finalizar a instalação conectar via web pelo endereço:
# https://ip_do_servidor:8006
# Usuario : root
# Senha : Criada durante a instalação.

Criar Storage
# Menu/discos/
Selecionar o hd que servira de storage 

# limpar o disco 
Pois para criar o storage o hd tem que estar limpo sem formatação.


# Menu/Discos/ZFS/Create_ZFS/
Selecionar os hds e definir o nome.

# Create
Agora o storage já está criado com o sistema de arquivos ZFS.

Atualização do Proxmox

# Menu/Atualizações/Atualizar
# Depois de atualizar reiniciar o servidor Proxmox.

Repositório de ISOs

# Menu/storage_local/imagens_iso/Carregar

Criar Maquinas virtuais

# Canto superior direito Criar VM

Backup de Vms
Na instalação do proxmox ele cria o storage local, nesse storage
são aceitos arquivos ISO e os backups são salvos ali.

É possível agendar backups automáticos 
# datacenter/backup/add/create backup job

FAZER BACKUP MANUAL E SALVAR FORA DO SERVIDOR  

# Seleciona_a_vm/Backup/Escolhe_storage/mode:stop

Para baixar o backup feito basta usar o filezilla conectar via ssh no servidor navegar ate o diretório abaixo e fazer o download do backup.
# /var/lib/vz/dump


Para restaurar o backup feito basta usar o winscp conectar via ssh no servidor navegar ate o diretório abaixo e fazer o upload dos arquivos de backup.

# /var/lib/vz/dump

Depois é só selecionar o backup correspondente e clicar em restore
para subir a vm novamente .

