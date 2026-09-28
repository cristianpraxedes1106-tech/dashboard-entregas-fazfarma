# Painel de entregas — projeto para VS Code

## Abrir e executar
1. Extraia o ZIP.
2. No VS Code, escolha Arquivo > Abrir Pasta e selecione a pasta painel-entregas.
3. Abra index.html no navegador. Também é possível usar a extensão Live Server do VS Code.

Não é necessário instalar Node.js, executar npm install ou compilar o projeto.
É necessária conexão com a internet para carregar a biblioteca D3.js (versão 7.9.0), usada pelos gráficos.

## Arquivos
- index.html: estrutura da página, textos, filtros e tabela.
- styles.css: cores, fontes, espaçamento e adaptação para celular.
- app.js: dados, cálculos, filtros e gráficos interativos.
- dados/ENTREGAS.xls: planilha original utilizada como fonte.

## Dados e alterações
A constante data, no início de app.js, contém os 2.914 registros das lojas 01, 05, 06, 07, 09 e 10.
Cada registro segue esta ordem:
["loja", "AAAA-MM-DD", "bairro", "turno", valorDoFrete]
Exemplo: ["01", "2026-08-02", "CENTRO", "Tarde", 8]
Os valores numéricos usam ponto decimal, sem símbolo de moeda.

Os dados abrangem 01/08/2026 a 22/09/2026 e somam R$ 34.153,96.
As linhas de total da planilha não entram como registros. Foram incluídos todos os blocos de dados, inclusive os blocos lado a lado da loja 09.
A quantidade exibida representa linhas do relatório e não necessariamente entregas individuais.
As grafias dos bairros foram preservadas, removendo apenas espaços nas extremidades.

Alterar o arquivo Excel não atualiza o painel automaticamente: é preciso atualizar a constante data em app.js.
Se adicionar outros meses ou anos, ajuste também as opções do filtro de mês, os textos do período e a indicação de ano do gráfico.

## Funcionamento
- Os filtros de loja, mês, bairro e turno são combinados.
- Os botões de lojas, turnos e bairros também aplicam filtros.
- O gráfico diário permite selecionar um dia.
- A medida alterna entre quantidade de registros e valor total de frete.
- A tabela mostra 25 registros por página.
- Limpar filtros restaura a visualização de todas as lojas.

## Publicação
Este é um site estático em HTML, CSS e JavaScript, sem servidor de dados ou banco de dados.
Mantenha os três arquivos principais juntos ao hospedar em um serviço de sites estáticos.
Os dados ficam no código enviado ao navegador. A proteção de acesso do site hospedado anteriormente pertence ao serviço de hospedagem, não ao código deste ZIP.
Editar esta cópia no VS Code não altera automaticamente a versão já publicada.

## Identidade visual Fazfarma
Logo original em assets/fazfarma-logo.jpg. Mantenha essa pasta junto dos arquivos do site.
A paleta foi aproximada a partir da imagem enviada: azul-petróleo #00627f, magenta #b52966 e cinza #767b80.
As variáveis --brand-petroleo, --brand-magenta e --brand-cinza estão no final de styles.css.
