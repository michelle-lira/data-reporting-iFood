# Data Reporting | iFood

## Objetivo:

O desafio foi montar um case através de uma experiência Data Driven com os meus dados pessoais em aplicativos de uso diário.

---

## Ferramentas Utilizadas:

> Scrum e Kanban      
> Jupyter Notebook       
> Python (Descartes, Geopandas, Geopy, Pill, Pandas, Numpy, Seaborn, Wordcloub, além dos módulos json e glob)       
> Tableau         

---

## Desenvolvimento:

Após um brainstorm e reavaliação do projeto para conclusão do módulo 5, no VamoAI, selecionei as bases de dados que gostaria de       
acrescentar e que seriam viáveis, que teriam dados suficientes.
Fiz o tratamento dos dados no Jupyter Notebook. Acrescentei algumas colunas com períodos do dia separados, que me ajudariam no
momento da visualização. Corrigi tipos de dados de algumas variáveis, verifiquei dados nulos e eliminei colunas que não pretendia     
utilizar.

As bases de dados que escolhi foram:

* Spotify
* iFood
* Instagram
* Uber
* Youtube
* Google Maps

Não dei continuidade à apresentação dos dados do Maps, devido insuficiência do volume de dados. Porém, tratei os dados e tentei         
extrair informações úteis. O notebook do maps está em anexo no reporitório junto aos demais.

---

## Resultados:

* Para acessar a análise exploratória dos dados [clique aqui](https://github.com/michelle-lira/data-reporting-iFood/tree/main/notebooks).

* Para acessar os painéis com maior detalhamento e interatividade acesse o meu perfil no [Tableau Public](https://public.tableau.com/app/profile/michelle.lira) e      o [case](https://public.tableau.com/views/case_iFood/data_reporting?:language=en-US&:display_count=n&:origin=viz_share_link).

![A Mãe do Ben entre dados, beats e bytes](https://github.com/michelle-lira/data-reporting-iFood/blob/main/dashboards/Dash-1.png)

---

![Dashboard Spotify](https://github.com/michelle-lira/data-reporting-iFood/blob/main/dashboards/Dash-Spotify.png)

---

![Dashboard iFood](https://github.com/michelle-lira/data-reporting-iFood/blob/main/dashboards/Dash-Ifood.png)

---

![Dashboard Instagram](https://github.com/michelle-lira/data-reporting-iFood/blob/main/dashboards/Dash-Insta.png)

---

![Dashboard Uber](https://github.com/michelle-lira/data-reporting-iFood/blob/main/dashboards/Dash-Uber.png)

---

![Dashboard Youtube](https://github.com/michelle-lira/data-reporting-iFood/blob/main/dashboards/Dash-Youtube.png)

---

## Exemplo de gráfico gerado na Análise Exploratória, no Jupyter Notebook:

> **Nuvem de palavras com máscara usando a logo do iFood**      

**Código**       
```
# Indicando o caminho, na minha máquina, onde estão as imagens (máscara e imagem base)
local = path.dirname(__file__) if "/home/mchll/my_project_dir/my_project_env/preparacao_projeto_5/images/ifood-3.png" in locals() else os.getcwd()
image_mask = np.array(Image.open(path.join(local, "/home/mchll/my_project_dir/my_project_env/preparacao_projeto_5/images/ifood-3.png")))

# Stopwords: conjunto de strings ou None. As palavras que serão eliminadas.    
# Se None, a lista STOPWORDS integrada será usada.
stopwords = set(STOPWORDS)
stopwords.add("said")

# Definindo detalhes da imagem
cloud = WordCloud(background_color="white", max_words=2000, mask=image_mask,
               stopwords=stopwords, width=900, contour_width=5, contour_color='red', colormap='Dark2').generate(restaurantes)

# Escolhendo o arquivo que receberá a máscara
cloud.to_file(path.join(local, "restaurantes_ifood_michelle_2.png"))

# Plotando a nuvem + máscara

plt.imshow(cloud, interpolation='bilinear')
plt.axis("off")
plt.figure()

plt.imshow(image_mask, cmap=plt.cm.gray, interpolation='bilinear')
plt.axis("off")

# Exibindo a imagem
plt.show()

# Salvando a imagem com a máscara
#wordcloud.to_file("restaurantes_ifood_michelle_3.png");
```

**Imagem gerada**

![](https://github.com/michelle-lira/data-reporting-iFood/blob/main/images/restaurantes_ifood_michelle_2.png)

![](https://github.com/michelle-lira/data-reporting-iFood/blob/main/images/ifood-3.png)


## Referências:

[Alura | Formação Python para Data Science](https://www.alura.com.br/formacao-python-data-science)     
[A Practical Guide for Data Analysis with Pandas](https://towardsdatascience.com/a-practical-guide-for-data-analysis-with-pandas-e24e467195a9)      
[Converting nested json structures to pandas dataframes](https://medium.com/swlh/converting-nested-json-structures-to-pandas-dataframes-e8106c59976e) 
[Customizing Colorbars](https://jakevdp.github.io/PythonDataScienceHandbook/04.07-customizing-colorbars.html)
[Geopandas](https://geopandas.org/)
[Insightlab](https://insightlab.ufc.br/6-truques-do-pandas-para-impulsionar-sua-analise-de-dados/)           
[Kejisen - Tech Forest](https://www.kejisen.com/pt/article/113141201.html)         
[Matplotlib](https://matplotlib.org/stable/contents.html)
[Pandas.pydata.org - json_normalize](https://pandas.pydata.org/pandas-docs/version/0.21/generated/pandas.io.json.json_normalize.html)         
[Seaborn Documentation](https://seaborn.pydata.org/)         
[Storytelling with Data](https://www.storytellingwithdata.com/books)               
[Tutorial flatten nested json in pandas](https://www.kaggle.com/jboysen/quick-tutorial-flatten-nested-json-in-pandas)
[WordCloud Documentation](https://amueller.github.io/word_cloud/generated/wordcloud.WordCloud.html)



