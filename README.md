# 🌦️ Challenge - Weather App

Welcome to the **Weather App Challenge!**
This repository contains the implementation of a simple weather application that retrieves and displays weather information using the [OpenWeather API](https://openweathermap.org/api).

We use predefined latitude and longitude coordinates from various cities to fetch and display detailed weather data, such as:

- 🌡️ Temperature
- 💧 Humidity
- 🌬️ Pressure (coming soon!)

<img src="weather_app.gif" alt="Weather app" height="500">

---

## 🚧 Current Status & To-Do List

The app is functional, but there are still some improvements and bug fixes to be made. Here's what's on our radar:

- [ ] 🔑 Add your API key to the `local.properties` file:
`WEATHER_API_KEY= <your-api-key-here>`
- [ ] 📊 Fetch and display **pressure** data from the API
- [ ] 🔄 Implement data refresh on **Refresh** button click
- [ ] 🎨 Fix broken **weather icons**
- [ ] 🧹 Eliminate **duplicate data** issues

---

## 🧠 Your Mission (Should You Choose to Accept It)

> 🎺 *Maestro, a drum roll, please...*

Your challenge is to help us fix those bugs and complete the tasks listed above.
Bring your problem-solving skills, creativity, and caffeine if needed — and let’s make this app shine!

Ready?
**Go go go...**
🚀🚀🚀🚀🚀🚀🚀🚀🚀

## 👨🏻‍💻 Nota do Desenvolvedor

Este repositório foi um fork de um desafio técnico, onde fui desafiado a realizar melhorias e corrigir bugs de uma aplicação Mobile.

**Tasks realizadas:**

- [x] 🔑 Add your API key to the `local.properties` file:
`WEATHER_API_KEY= <your-api-key-here>` - Para adquirir a chave de api, criei minha conta na OpenWeather API. Ao criar a conta e conseguir gerar a chave, copiei e adicionei em uma variável chamada WEATHER_API_KEY no arquivo local.properties.
- [x] 📊 Fetch and display **pressure** data from the API - Localizei o arquivo WeatherListAdapter, arquivo responsável por renderizar os componentes e conteúdo da lista que contém os dados do tempo, nele há a função holdWeather, responsável por adicionar o conteúdo nos componentes. Notei que no campo que era para aparecer a pressão havia uma String, então substitui por weather.getMain().getPressure();
- [x] 🔄 Implement data refresh on **Refresh** button click - Na MainActivity eu encontrei a função referente ao funcionamento do Refresh Button. Analisando o código, foi possível observar que no fetchButton.setOnClickListener, comando que permite o botão ser clicável, estava apenas mostrando ao usuário um toast dizendo que futuramente será implementado. Dessa forma, ao acessar a função fetchAllForecasts no arquivo MainViewModel, eu o tornei público para que essa função possa ser acessada fora do arquivo. Reutilizei o toast para informar a mensagem “Atualizado com sucesso”
- [x] 🎨 Fix broken **weather icons** - Notei que na pasta Drawables havia uma das imagens que estava com o nome divergente ao que é fornecido pela API. Corrigi de weather_icon_03dd.png para weather_icon_03d.png
- [x] 🧹 Eliminate **duplicate data** issues - No arquivo MainViewModel há o trecho de código que contém a função fetchAllForecasts(), que busca previsões do tempo para cada localização informada na getLocalizations() e atualiza a lista de climas exibida na tela. A getLocations pertence ao arquivo Repository, e lá tem as coordenadas pré-definidas dos lugares que devem ser puxados os dados do tempo, dentro dele havia coordenadas repetidas, o que fazia com que viessem dados duplicados.
- [x] ⭐️ **EXTRA:** Por melhoria de UX, troquei o ícone que aparece ao não reconhecer a imagem para um símbolo de alerta, para indicar que teve um erro ao mostrar o ícone. Além disso, alterei o ícone do aplicativo para uma nuvem e o nome do app para Weather App, junto disso alterei o ícone da splash screen também.
