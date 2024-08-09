
Visualmente no portal da azure:

	Grupos de Recursos:
	
	Clicar no botão "+ Criar":
		Detalhes do projeto:
			Assinatura: Estudante
			Grupo de Recursos: rg-dimdim
			Região: Padrão
		
		Criar
	
	Clicar no botão "+ Criar":
		Detalhes do projeto:
			Assinatura: Estudante
			Grupo de Recursos: rg-vendebem
			Região: Padrão
			
		Criar


Via Linhas de Comando (CLI):
	Abra o terminal Cloud Shell 
	Obs: Deixar os comandos em Linha Única
	
	Listar os Grupos de recursos com o comando:
		az group list --output table
		
	Exibe detalhes de um Grupo de Recurso:
		echo "Entre com o nome do Grupo de Recursos: " && 
		read resourceGroupName && 
		az group show --name $resourceGroupName
	
	Criando um Grupo de Recurso:
		echo "Entre com o nome do Grupo de Recursos: " && 
		read resourceGroupName && 
		echo "Entre com a localização (ex: brazilsouth): " &&
		read location &&
		az group create --name $resourceGroupName --location $location
		
	Excluindo um Grupo de Recurso:
		echo "Entre com o nome do Grupo de Recursos:" &&
		 read resourceGroupName && 
		 az group delete --name $resourceGroupName
		 
	Para excluir todos os Grupos de Recursos que estão vazios:
		for i in `az group list -o tsv --query [].name`; 
		do if [ "$(az resource list -g $i -o tsv)" ]; 
		then echo "$i nao esta vazio"; 
		else az group delete -n $i -y --no-wait; fi; done
		
	Lista os dados da Conta:
		az account list
		
	Lista os locais dos Datacenters:
		az account list-locations
		
	Lista uma tabela dos locais dos Datacenters:
		az account list-locations -o table 
		ou 
		az account list-locations --output table
		
	Lista os locais dos Datacenters e exporta os dados em um arquivo txt
		az account list-locations --output table > datacenters.txt


[[2 - Criando uma VM pelo CLI do Azure]]