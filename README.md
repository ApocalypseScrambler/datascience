# datascience
******************************************************************************
df_subset = df_subset.explode('cast')
popularidad_actores = df_subset.groupby('cast')['popularity_Sqrt'].sum().reset_index()
popularidad_actores = popularidad_actores.sort_values(by='popularity_Sqrt', ascending=False)

actores_top20 = popularidad_actores.head(20)

# Configura el estilo de seaborn
sns.set(style="whitegrid")

# Crea un gráfico de barras horizontales para mostrar los géneros más populares
plt.figure(figsize=(10, 6))
sns.barplot(x='popularity_Sqrt', y='cast', data=actores_top20, palette='viridis')
plt.xlabel('Popularidad Total')
plt.ylabel('Actores')
plt.title('Actores Más Populares')
plt.show()

*******************************************************************************

df_subset = df_subset.explode('main_genre')
popularidad_generos = df_subset.groupby('main_genre')['popularity_Sqrt'].sum().reset_index()
popularidad_generos = popularidad_generos.sort_values(by='popularity_Sqrt', ascending=False)

# Configura el estilo de seaborn
sns.set(style="whitegrid")

# Crea un gráfico de barras horizontales para mostrar los géneros más populares
plt.figure(figsize=(10, 6))
sns.barplot(x='popularity_Sqrt', y='main_genre', data=popularidad_generos, palette='viridis')
plt.xlabel('Popularidad Total')
plt.ylabel('Género')
plt.title('Géneros Más Populares')
plt.show()
