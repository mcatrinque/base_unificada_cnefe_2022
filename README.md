# Concatenação dos Dados dos Endereços por UF do CNEFE 2022 em uma Única Base

## Introdução

Este notebook descreve o processo de download, extração e unificação dos arquivos contendo os registros de endereços de todas as Unidades Federativas (UF) do Brasil, presentes no Cadastro Nacional de Endereços para Fins Estatísticos (CNEFE) do IBGE (Instituto Brasileiro de Geografia e Estatística). Esses dados foram coletados durante o Censo Demográfico de 2022 e são essenciais para análises estatísticas e geográficas.

## Objetivos

- **Download dos Arquivos**: Obter os arquivos de endereços das UFs diretamente do site do IBGE.
- **Verificação e Atualização**: Certificar-se de que os arquivos locais estão atualizados em relação aos disponíveis online.
- **Descompactação**: Extrair os dados dos arquivos ZIP.
- **Unificação**: Combinar todos os arquivos em um único CSV, consolidando os dados de endereços de todo o Brasil.

## Requisitos

Antes de iniciar, você precisará ter:

- Python 3.x instalado.
- As bibliotecas Python necessárias: `requests`, `beautifulsoup4`, `pandas`, `zipfile`. Essas podem ser instaladas via pip:
  ```bash
  pip install requests beautifulsoup4 pandas
  ```

## Estrutura do Notebook

### Configuração Inicial

- **Definir Diretório**: Solicita o caminho do diretório onde os arquivos baixados serão armazenados.
  ```python
  diretorio_enderecos_uf = input("Insira o diretório de destino dos arquivos a serem baixados: ")
  ```

### Download dos Arquivos

- **Função `obter_links(url_base)`**: Extrai os links dos arquivos ZIP de endereços da página do IBGE.
- **Função `verificar_arquivo(url_arquivo, caminho_arquivo)`**: Verifica se o arquivo local existe e está atualizado em relação ao arquivo remoto.
- **Função `baixar_enderecos_uf(url_arquivo, caminho_arquivo)`**: Faz o download de um arquivo específico a partir de uma URL.
- **Função `extrair_arquivos(url_base, diretorio)`**: Coordena o processo de download de todos os arquivos ZIP de endereços.

### Descompactação dos Arquivos

- **Função `descompactar_arquivos(diretorio)`**: Descompacta todos os arquivos ZIP no diretório especificado, extraindo os CSVs de endereços.

### Unificação dos Dados

- **Função `criar_base_unificada(diretorio, arquivo_enderecos_br, batch_size)`**: Combina todos os arquivos CSV de endereços em um único arquivo CSV. A leitura é feita em batches para otimizar o uso de memória.

### Conclusão

O notebook finaliza consolidando todos os arquivos de endereços das UFs em um único CSV, pronto para análises detalhadas.

## Como Usar o Notebook

1. **Clone este repositório** ou baixe o notebook.
2. **Abra o notebook** com o Jupyter Notebook ou JupyterLab.
3. **Configure o diretório de destino**: Insira o caminho onde os arquivos serão armazenados.
4. **Execute as células do notebook** sequencialmente para:
   - Baixar os arquivos de endereços das UFs.
   - Descompactar os arquivos ZIP.
   - Unificar os dados em um único arquivo CSV.

## Links Úteis

- [Página de Download do CNEFE 2022 - IBGE](https://www.ibge.gov.br/estatisticas/sociais/populacao/38734-cadastro-nacional-de-enderecos-para-fins-estatisticos.html?=&t=downloads)
- [Documentação do Pandas](https://pandas.pydata.org/pandas-docs/stable/)

## Licença

Este projeto está licenciado sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

---

**Nota**: Este notebook é uma ferramenta poderosa para consolidar os dados do CNEFE, mas sempre verifique a integridade e a atualidade dos dados antes de usá-los para análises críticas.

```
