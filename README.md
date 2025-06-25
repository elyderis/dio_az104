Gerenciamento de Máquinas Virtuais no Microsoft Azure
O que é uma Máquina Virtual (VM)?
Uma máquina virtual (VM) é um recurso de computação no Azure que emula um computador físico. Ela permite que você execute sistemas operacionais e aplicativos de maneira isolada, como se fosse um computador local.

Componentes principais de uma VM
Imagem do sistema operacional: Escolha o sistema operacional (Windows, Ubuntu, etc.) para a VM.

Tamanho da VM: Define a capacidade de CPU e memória, impactando no desempenho e no custo da VM.

Disco do sistema operacional: O disco principal que armazena o sistema operacional.

Discos adicionais: Discos extras que podem ser anexados à VM.

Rede virtual (VNet) e sub-rede: A rede onde a VM estará conectada.

Grupo de segurança de rede (NSG): Define as regras de firewall para controlar o tráfego de rede da VM.

IP público: Se necessário, configura um IP público para permitir acesso externo.

Passo a passo para criação de uma VM no portal do Azure
Acessar o portal: Vá para https://portal.azure.com.

Criar a VM: No menu, vá até "Máquinas Virtuais" > "Criar".

Configurar a VM: Preencha as informações necessárias:

Nome da VM

Região

Sistema Operacional

Credenciais de Acesso (usuário e senha)

Escolher o tamanho da VM: Selecione um tamanho adequado para sua VM. Por exemplo, para testes rápidos, você pode escolher o tamanho B1s.

Configurar discos, rede e regras de acesso: Ajuste as configurações de rede, disco e segurança.

Revisar e Criar: Verifique as configurações e clique em Criar.

Exemplo com Azure CLI
Se você preferir usar a Azure CLI para criar uma VM, basta executar o comando abaixo:

bash
Copiar
Editar
az vm create \
  --resource-group meuGrupoDeRecursos \
  --name minhaVM \
  --image UbuntuLTS \
  --size Standard_B1s \
  --admin-username meuUsuario \
  --admin-password minhaSenha123 \
  --vnet-name minhaVNet \
  --subnet minhaSubRede
Esse comando cria uma máquina virtual com as seguintes características:

Imagem: Ubuntu LTS.

Tamanho: Standard_B1s.

Usuário administrador: meuUsuario.

Senha: minhaSenha123.

Rede virtual (VNet): minhaVNet.

Sub-rede: minhaSubRede.

Dicas adicionais
Segurança: Sempre configure um Grupo de Segurança de Rede (NSG) para controlar o tráfego da sua VM.

Backup: Considere configurar backup automático para garantir que seus dados estejam seguros.

Desligamento automático: Configure um desligamento automático para economizar recursos quando a VM não estiver em uso.
