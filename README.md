# AcidentesTransito
## Objetivo
Utilizar os dados disponível em [DadosAbertosPOA](https://dadosabertos.poa.br/dataset/acidentes-de-transito-acidentes/resource/b56f8123-716a-4893-9348-23945f1ea1b9) para análises mais profundas sobre acidentes de transito.
## Objetivo de aprendizado
-Fazer carregamento, tratamento e a disponibilização dos dados do dataset, utilizar a biblioteca folium para gerar mapa com a região onde os acidentes ocorreram através da latitude e longitude fornecidas

-Fazer um mapa de calor dos acidentes com a biblioteca folium e corrigir possíveis erros

-Fazer um mapa de clusters com as quantidades de acidentes em cada região utilizando o plugin (MarkerCluster)

-Finalizando o projeto com a construção de gráficos de barras pelo matplotlib com a quantidade de acidentes por ano

### OBSERVAÇÃO
Como encontrar as variáveis de longitude e latitude de uma região desejada (ex: sua cidade).
```
import folium
from geopy.geocoders import Nominatim
cidade = "Restinga, São Paulo"
geolocator = Nominatim(user_agent="my_geocoder")
location = geolocator.geocode(cidade)
if location is not None:
    latitude = location.latitude
    longitude = location.longitude

    # Crie o mapa usando folium com as coordenadas obtidas
    mapa = folium.Map(location=[latitude, longitude], zoom_start=11)

    # Adicione um marcador para a localização
    folium.Marker([latitude, longitude], popup=cidade).add_to(mapa)

    # Exiba o mapa
    mapa.save("mapa_restinga_sao_paulo.html")
    print("Mapa salvo com sucesso!")
else:
    print("Localização não encontrada para a cidade de", cidade)
mapa
```

