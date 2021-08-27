# ethereum-example

Exemplo de uso do Blockchain com Ethereum baseado em aula do Prof. Marcelo Garcia da PUC Minas Virtual

Baixe o Geth & Tools em https://geth.ethereum.org/downloads/

## Criando uma rede privada

1. Em um bash Linux, execute o comando
`puppeth`

2. Configure um novo bloco gênesis

> **What would you like to do?**
> Configure new genesis

> **What would you like to do?**
> Create new genesis from scratch

> **Which consensus engine to use?**
> Ethash - proof of work

> **Which accounts should be pre-funded?**
> 0x

> **Should the precompile-address?**
> yes

> **Specify your chain/network ID if you want an explicit one**
> (não preencher)

> **What would you like to do?**
> Manage existing genesis
> Export genesis configuration

> **Which folder to save the genesis specs into?**
> (não preencher para ser a local)


## Iniciando uma rede privada

Executar dentro da pasta onde foram criados os arquivos do puppeth:
`geth --datadir . init ethprivate.json`

## Criando contas

Crie umas três contas de teste com senhas de preferência:
`geth --datadir . account new`

Listagem das contas criadas:
`geth --datadir . account list`

## Iniciando um nó com servidor RPC

Rode em um terminal o seguinte comando:
`geth --datadir . --nodiscover --mine --miner.threads 2 --rpcapi eth,web3,personal,miner,net --rpc --rpcport "8545" --port "30303" --rpccorsdomain "*" --nat "any" --unlock 0 --password ./password.sec --allow-insecure-unlock --ipcdisable`

E, em outro, faça o attach de um cliente para rodar comandos no nó
`geth attach http://127.0.0.1:8545`

## Rodando comandos para manipular as contas

eth.accounts, eth.coinbase, eth.getBalance(eth.coinbase) etc.
