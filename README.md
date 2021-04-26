# EM DESENVOLVIMENTO!


### Projeto de desenvolvimento mobile

## Neste projeto será abordado a construção de um App de Barbearia, que tera as funcionalidades de cadastrar usuário, e agendamento de hora com barbeiros disponíveis próximo ao local.


Iniciando o projeto é necessário a criação da estrutura com o comando:

`npx react-native init app`

Instalando as depedências necessárias com:

`npm install styled-components`

`npm install @react-navigation/native`

`npm install react-native-reanimated react-native-gesture-handler react-native-screens react-native-safe-area-context @react-native-community/masked-view`

Após isso, import no arquivo `index.html` o `reac-native-gesture-handler` para ajudar nos processos de gestos que faremos com o app, aumentando ainda mais rescursos que nossa aplicação irá disponibilizar. Então no arquivo `index.html` escreva:

`import 'react-native-gesture-handler';`

Continuando a instalaçaõ das dependências:

`npm install @react-navigation/stack`

`npm install @react-navigation/bottom-tabs`

`npm install @react-native-community/async-storage`

`npm install @react-native-community/geolocation`

`npm install react-native-permissions`

Após o Download dessa ultima dependência, é necessário informar ao nosso app, que utilizaremos a localização do usúario, dessa forma há a possibilidade pra utilizar  o recurso de localização do usuário. Para isso vá a te a pasta `android` > `src` > `main` > `AndroidManifest.xml` e na linha e abaixo da linha 4 cole esse código:

`<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />`

Continuando as ultimas instalações:

`npm install react-native-swiper`

`npm install react-native-svg`

`npm install react-native-svg-transformer`

Ao término da instalação da ultima dependência, é necessário acrescentar alguns códigos a nossa estrutura original, acrescimo essa realizada em `metro.config.js` na raiz do projeto, e nesse estrutura cole o seguinte: 

```
const { getDefaultConfig } = require("@expo/metro-config");
module.exports = (async () => {
  const {
    resolver: { sourceExts, assetExts }
  } = await getDefaultConfig(__dirname);
  return {
    transformer: {
      getTransformOptions: async () => ({
        transform: {
          experimentalImportSupport: false,
          inlineRequires: true,
        },
      }),
      babelTransformerPath: require.resolve("react-native-svg-transformer")
    },
    resolver: {
      assetExts: assetExts.filter(ext => ext !== "svg"),
      sourceExts: [...sourceExts, "svg"]
    }
  };
})();
```
Substituindo todo o codigo que continha anteriormente neste arquivo.
   wallisonlima@wallisonlima-MS-7817:/usr/local/android-studio/bin$ ./studio.sh
