Já obtemos o nome do Datacenter e agora vamos recuperar a lista de imagens de VMs disponíveis no Marketplace.

Sintaxe:
	az vm image list [--all]
				  [--location]
				  [--offer]
				  [--publisher]
				  [--sku]
				  [--subscription]
				  
--all:
	Recupera a lista de imagens do serviço Azure online ao invés de usar uma lista de imagens offline.
	
-- offer ou -f
	Nome da Imagem Oferecida (realiza uma busca parcial).
	
--publisher ou -p
	Nome do Publicador da Imagem (realiza uma busca parcial).

------------------------------

Lista as VMs disponíveis e salva no arquivo txt:
	az vm image list --all -p canonical -f UbuntuServer --output table > vmsubuntu.txt
