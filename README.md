# Monitor de Sites em Go

Aplicativo de linha de comando desenvolvido em Go para monitorar uma lista de sites, registrar o histórico de verificações e exibir logs quando necessário. Todo o comportamento está concentrado em `hello.go`.

## Pré-requisitos
- Go 1.20+ instalado
- Arquivo `sites.txt` na raiz do projeto contendo um endereço por linha

## Como executar
```bash
cd /home/alppinheiro/go/src/hello
go run hello.go
```

## Menu principal
O programa roda em loop até que o usuário escolha sair.

1. **Iniciar Monitoramento**: lê os sites de `sites.txt`, testa cada um 3 vezes (`monitoramentos`) com intervalo de 5 segundos (`delay`).
2. **Exibir Logs**: imprime o conteúdo de `log.txt` com o histórico das verificações.
0. **Sair**: encerra a aplicação.

## Funcionalidades
- **Saudação inicial**: apresenta nome do autor e versão do programa.
- **Listagem de nomes**: imprime uma lista fixa de nomes (função ilustrativa).
- **Leitura de sites**: carrega dinamicamente todos os URLs presentes em `sites.txt` usando `bufio.Reader`.
- **Monitoramento HTTP**: envia requisições `GET` para cada site e identifica sucesso (`StatusCode == 200`) ou falha.
- **Registro de logs**: grava cada verificação em `log.txt` com timestamp e status (`online: true/false`).
- **Consulta de logs**: lê e exibe todo o conteúdo do arquivo de log via `ioutil.ReadFile`.

## Estrutura de arquivos
- `hello.go`: código-fonte principal.
- `sites.txt`: lista de URLs monitorados.
- `log.txt`: alimentado automaticamente com os resultados de cada monitoramento.

## Personalização rápida
- Ajuste as constantes `monitoramentos` e `delay` em `hello.go` para mudar quantidade de rodadas e intervalo entre requisições.
- Edite `sites.txt` para adicionar ou remover hosts sem recompilar o programa.
