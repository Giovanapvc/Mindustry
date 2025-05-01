## Atividade 3: Engenharia de Software 2


Repositório selecionado: https://github.com/Anuken/Mindustry


Gráfico selecionado: production and test files  (os gráficos gerados se encontram no fork com o nome index.html, relacionados ao commit "Adding graphics from GitEvo"


Explicação: o gráfico selecionado apresenta um comportamento não esperado. Podemos avaliar uma evolução ao longo de aproximadamente 5 anos(2020 -2025), e nesse período os arquivos de produção aumentaram gradualmente, com uma maior taxa de 2022 para 2023. No entanto, os arquivos de teste apresentam baixíssima variabilidade,, girando em torno de 7 a 9 arquivos ao longo dos anos, uma quantidade baixa e com uma taxa estagnada de crescimento. Analisando os arquivos de teste e outros do repositório, algumas das possíveis explicações para isso podem ser advindas do fato da aplicação ser um jogo que usa também um framework de game design baseado em Java(libGDX) em seu desenvolvimento, o que pode potencialmente dificultar a implementação de testes automatizados. Outra questão é a presença de pouco arquivos de teste, mas bem longos, indicando a adição de testes sem uma maior modularizaç~aõ entre arquivos deles. Essa utilização, somada ao grande uso de componentes gráficos também podem indicar que testes automatizados não são práticas tão comuns em aplicações de jogos. Assim, é possível que a aplicação priorize testes manuais para testar jogabilidade e efeitos gráficos, dentro outros aspectos. De qualquer forma, isso não é uma boa prática de manutenção, pois vemos que o número de arquivos de produção(bem como linhas de código, como mostrado em outros gráficos) aumenta linearmente ao longo dos anos, sinalizando a implementação de novas features no jogo. Nesse cenário, a implementação de novos testes pode ser mais constante e presente no projeto. Outra prática que poderia ser melhor explorada se relaciona à presença de poucos arquivos com muitos testes e bem longos. Uma boa prática para substituir essa característica seria uma maior modularização de arquivos para diferentes tipos de teste, separados entre features do jogo, por exemplo. 



![Logo](core/assets-raw/sprites/ui/logo.png)

[![Build Status](https://github.com/Anuken/Mindustry/workflows/Tests/badge.svg?event=push)](https://github.com/Anuken/Mindustry/actions)
[![Discord](https://img.shields.io/discord/391020510269669376.svg?logo=discord&logoColor=white&logoWidth=20&labelColor=7289DA&label=Discord&color=17cf48)](https://discord.gg/mindustry)  

The automation tower defense RTS, written in Java.

_[Trello Board](https://trello.com/b/aE2tcUwF/mindustry-40-plans)_  
_[Wiki](https://mindustrygame.github.io/wiki)_  
_[Javadoc](https://mindustrygame.github.io/docs/)_ 

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md).

## Building

Bleeding-edge builds are generated automatically for every commit. You can see them [here](https://github.com/Anuken/MindustryBuilds/releases).

If you'd rather compile on your own, follow these instructions.
First, make sure you have [JDK 17](https://adoptium.net/archive.html?variant=openjdk17&jvmVariant=hotspot) installed. **Other JDK versions will not work.** Open a terminal in the Mindustry directory and run the following commands:

### Windows

_Running:_ `gradlew desktop:run`  
_Building:_ `gradlew desktop:dist`  
_Sprite Packing:_ `gradlew tools:pack`

### Linux/Mac OS

_Running:_ `./gradlew desktop:run`  
_Building:_ `./gradlew desktop:dist`  
_Sprite Packing:_ `./gradlew tools:pack`

### Server

Server builds are bundled with each released build (in Releases). If you'd rather compile on your own, replace 'desktop' with 'server', e.g. `gradlew server:dist`.

### Android

1. Install the Android SDK [here.](https://developer.android.com/studio#command-tools) Make sure you're downloading the "Command line tools only", as Android Studio is not required.
2. In the unzipped Android SDK folder, find the cmdline-tools directory. Then create a folder inside of it called `latest` and put all of its contents into the newly created folder.
3. In the same directory run the command `sdkmanager --licenses` (or `./sdkmanager --licenses` if on linux/mac)
4. Set the `ANDROID_HOME` environment variable to point to your unzipped Android SDK directory.
5. Enable developer mode on your device/emulator. If you are on testing on a phone you can follow [these instructions](https://developer.android.com/studio/command-line/adb#Enabling), otherwise you need to google how to enable your emulator's developer mode specifically.
6. Run `gradlew android:assembleDebug` (or `./gradlew` if on linux/mac). This will create an unsigned APK in `android/build/outputs/apk`.

To debug the application on a connected device/emulator, run `gradlew android:installDebug android:run`.

### Troubleshooting

#### Permission Denied

If the terminal returns `Permission denied` or `Command not found` on Mac/Linux, run `chmod +x ./gradlew` before running `./gradlew`. *This is a one-time procedure.*

#### Where is the `mindustry.gen` package?

As the name implies, `mindustry.gen` is generated *at build time* based on other code. You will not find source code for this package in the repository, and it should not be edited by hand.

The following is a non-exhaustive list of the "source" of generated code in `mindustry.gen`:

- `Call`, `*Packet` classes: Generated from methods marked with `@Remote`.
- All entity classes (`Unit`, `EffectState`, `Posc`, etc): Generated from component classes in the `mindustry.entities.comp` package, and combined using definitions in `mindustry.content.UnitTypes`.
- `Sounds`, `Musics`, `Tex`, `Icon`, etc: Generated based on files in the respective asset folders.

---

Gradle may take up to several minutes to download files. Be patient. <br>
After building, the output .JAR file should be in `/desktop/build/libs/Mindustry.jar` for desktop builds, and in `/server/build/libs/server-release.jar` for server builds.

## Feature Requests

Post feature requests and feedback [here](https://github.com/Anuken/Mindustry-Suggestions/issues/new/choose).

## Downloads

| [![](https://static.itch.io/images/badge.svg)](https://anuke.itch.io/mindustry)    |    [![](https://play.google.com/intl/en_us/badges/images/generic/en-play-badge.png)](https://play.google.com/store/apps/details?id=io.anuke.mindustry)   |    [![](https://fdroid.gitlab.io/artwork/badge/get-it-on.png)](https://f-droid.org/packages/io.anuke.mindustry)	| [![](https://flathub.org/assets/badges/flathub-badge-en.svg)](https://flathub.org/apps/details/com.github.Anuken.Mindustry)  
|---	|---	|---	|---	|
