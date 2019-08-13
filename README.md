# Análise do DataSet de Vinhos

<p>Os dados para esta análise vem do website <b><a href="https://archive.ics.uci.edu/ml/datasets/Wine+Quality">UCI-Machine Learning Repository</a></b> e iremos explorar duas amostras de vinho: <b>Vinho Tinto</b> e <b>Vinho Branco</b> oriundos do Norte de Portugual. Cada amostra vem com uma classificação de qualidade de 0 a 10 e o resultado de vários testes físico-químico. Em poucas palavras iremos analisar, a princípio, propriedades como quantidade de alcool, nível de acidez e o açucar residual.</p>
<p>Os arquivos estão no formato <code>CSV</code> e os seus valores separados por <code>;</code> possuindo 11 colunas de propriedades químicas + Qualidade:</p>
<ul>
  <li>Acidez fixa</li>
  <li>Acidez volátil</li>
  <li>Ácido cítrico</li>
  <li>Açúcar residual</li>
  <li>Cloretos</li>
  <li>Dióxido de enxofre livre</li>
  <li>Dióxido de enxofre total</li>
  <li>Densidade</li>
  <li>pH</li>
  <li>Sulfatos</li>
  <li>Álcool</li>
  <li>Qualidade (que tem pontuação de 0 a 10)</li>
</ul>

## Primeira Etapa

Se já tiver algum dos programas listados abaixo e quiser usá-los, apenas certifique-se de estarem atualizados e instalados corretamente. Para o bom funcionamento e a visualização correta do projeto será necessário o download de alguns arquivos:
<ul>
  <li>Fazer o donwload e instalar o <a href="https://www.anaconda.com/">Anaconda</a></li>
  <li>Fazer o donwload e instalar o <a href="https://www.winzip.com/win/en/downwz.html">WinZip</a>(Version para Win. No Mac há a opção direta sem necessidade de outro software)</li>
  <li>Fazer o download dos arquivos <code>winequality-red.csv</code> e <code>winequality-white.csv</code> no repositório <a href="https://github.com/sergioseo/Wine_quality">Wine_quality</a></li>
  <li>Depois de instalar o <code>Anaconda</code> procure pelo <code>Jupyter Notebook</code> e click em <code>install</code> e depois <code>launch</code></li>
</ul>
  
### Algumas questões antes de começar
<p>É importante pensarmos em algumas questões relevantes ao projeto antes de começar a de fato explorar o dataSet; tais como:
  <ol>
    <li>Quais características químicas são mais importantes para prever a qualidade do vinho?</li>
    <li>Existe um certo tipo de vinho (tinto ou branco) associado a uma melhor qualidade?</li>
    <li>Vinhos com maior teor alcoólico recebem classificações maiores?</li>
    <li>Vinhos mais doces (mais açúcar residual) recebem classificações maiores?</li>
    <li>Qual nível de acidez está associado a uma melhor qualidade?</li>
  </ol>

## Parte 1: Avaliando o DataSet
<p>A principio vamos inspecionar os dataSets <code>winequality-red.csv</code> e <code>winequality-white.csv</code>usando  <code>Pandas</code> e abri-los para verificar os rótulos e os separadores. No nosso caso temos <code>;</code>como separadores e não podemos esquecer de usar <code>sep=";"</code> para que as colunas sejam criadas separadamente.Também temos que nos atentar aos rótulos e uma dica q eu sempre dou é usar um editor simples (ATOM, SUBLIME, VSCODE, etc) para dar uma olhada e verificar se o dataSet possui rótulos como um cabeçalho.
<p>Passaremos para os seguintes passos:</p>
<ol>
  <li>Verificar o número de amostras em cada conjunto de dados</li>
  <li>Verificar o número de colunas em cada conjunto de dados</li>
  <li>Verificar os recursos com valores faltantes</li>
  <li>Verificar as linhas duplicadas em cada conjunto de dados</li>
  <li>Verificar o número de valores únicos para qualidade em cada conjunto de dados</li>
  <li>Verificar a densidade média em cada conjunto de dados</li>
</ol>

### Conclusão da Parte 1
<p>Através desta rápida avaliação podemos chegar a algumas repostas interessantes:</p>
  <ul>
  <li>Os conjuntos de dados não possuem dados faltantes</li>
  <li>Há valores duplicados mas a principio não tem necessidade de descartá-los</li>
  <li>A densidade média do <b>Vinho Tinto = 0.996747</b> e a do <b>Vinho Branco = 0.994027</b></li>
  </ul>
<p>Para acessar os métodos utilizados <b><a href="https://github.com/sergioseo/Wine_quality/blob/master/avaliando_parte_1.ipynb">clique aqui</a></b>  
</p>

## Parte 2: Unindo os Datasets

<p>Para podermos analisar com mais eficiência nossos datasets vamos combiná-los em um único DataFrame e acrescentar mais uma feature chamada <code>cor</code> para podermos identificar de qual conjunto de dados ele pertence. Para isso usaremos e importaremos o <code>Numpy</code></p>
<p><b>OBS:</b> Ao unir e combinar as colunas teremos uma coluna que não será combinada por estar com o nome levemente errado e para resolver teremos que renomear a coluna <code>total_sulfur-dioxide</code> para <code>total_sulfur_dioxide</code> do dataset <code>winequality-red.csv</code> para que o método <code>append()</code>funcione perfeitamente.
<p>Assim teremos um novo DataFrame chamado <code>winequality_edited.csv</code>. Para acessá-lo <b><a href="https://github.com/sergioseo/Wine_quality/blob/master/winequality_edited.csv">clique aqui</a></b>
<p>Para acessar os métodos utilizados nesta etapa <b><a href="https://github.com/sergioseo/Wine_quality/blob/master/unindo_datasets_parte_2.ipynb">clique aqui</a></b>  
</p>

## Parte 3: Começando as análises
<p>Agora que temos o DataFrame limpo, organizado com a coluna de cores acrescentada podemos discutir essas questões:</p>
<ul>
  <li>Será que o tipo de vinho está associado a uma qualidade superior?</li>
  <li>Qual o nível de acidez que recebe a maior avaliação média?</li>
</ul>
<p>Usaremos o método <code>groupby()</code> para agrupar os valores e conseguir criar novos rótulos para cada grupo</p>
<p>Para acessar os métodos utilizados <b><a href="https://github.com/sergioseo/Wine_quality/blob/master/comecando_as_analises_parte_3.ipynb">clique aqui</a></b>  
</p>





## Concluindo
  <li>Foi disponibilizado um arquivo HTML com os dados e o resultado da análise. Para acessá lo <b><a href="https://github.com/sergioseo/MotivateCo/blob/master/chicago_bike.html">click aqui<a/></b>
  <li>Também está disponível uma versão da análise em <code>Python 3</code> para apreciação. Para acessá lo <b><a href="https://github.com/sergioseo/MotivateCo/blob/master/chicago_bike.py">click aqui<a/></b>

