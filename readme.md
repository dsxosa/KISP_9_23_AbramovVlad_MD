 # Create a project

Expo — это React Native-фреймворк, который упрощает разработку приложений для Android и iOS. Наш фреймворк поддерживает маршрутизацию на основе файлов, предоставляет стандартную библиотеку нативных модулей и многое другое. Expo — это проект с открытым исходным кодом и активным сообществом на GitHub и в Discord.

Мы также создали Expo Application Services (EAS) — набор сервисов, которые дополняют фреймворк Expo на каждом этапе процесса разработки.

***System requirements***
Node.js (LTS).
Поддерживаются macOS, Windows (Powershell и WSL 2) и Linux.

***Start with a default project***
Мы рекомендуем начать с проекта по умолчанию, созданного с помощью 'create-expo-app'. Проект по умолчанию содержит примеры кода, которые помогут вам начать работу.

Чтобы создать новый проект, выполните следующую команду:

'''

npx create-expo-app@latest

'''

Вы можете выбрать другой шаблон, добавив параметр '--template'

***Начните с примера***
Вместо проекта по умолчанию вы можете начать с одного из примеров Expo. Это небольшие приложения, каждое из которых демонстрирует определенную функцию или интеграцию, например маршрутизатор Expo, виджеты Expo или экран с камерой.

Чтобы просмотреть полный список и выбрать нужный пример, запустите 'create-expo-app' с параметром '--example' и без имени:

'''

npx create-expo-app@latest --example

'''

Чтобы напрямую создать известный пример, укажите его название:

'''

npx create-expo-app@latest --example with-widgets

'''

***Настройка ИИ-агента***
В новом проекте есть файлы контекста проекта, которые считывают ИИ-агенты: AGENTS.md, CLAUDE.md и .claude/settings.json. Для Claude Code и Codex также есть официальный плагин для Expo. С помощью одной команды вы можете установить Expo Skills и зарегистрировать сервер протокола контекста модели Expo (MCP): 

'''

codex plugin add expo@openai-curated

'''

Затем войдите в свою учетную запись Expo:

'''

codex mcp login expo

'''

Плагин также устанавливает навык, который сообщает агенту, где находятся файлы в новом проекте Expo:

expo-project-structure

Для Cursor и других агентов установите Expo Skills и Expo MCP Server отдельно. Настройка каждого агента описана в разделе «Агенты ИИ и обзор Expo».

***Следующий шаг***
У вас есть проект. Теперь пришло время настроить среду разработки, чтобы вы могли приступить к работе.


# Set up your environment

Узнайте, как настроить среду разработки, чтобы начать работу с Expo.

Давайте создадим локальную среду разработки для запуска вашего проекта на Android и iOS.

***Где бы вы хотели разрабатывать?***
Мы рекомендуем использовать для разработки реальное устройство, так как вы сможете увидеть именно то, что увидят ваши пользователи.

1. Android
2. iOS
3. Android emulator
4. iOS emulator

***Как бы вы хотели разрабатывать?***
Expo Go - это площадка, где студенты и обучающиеся могут быстро опробовать Expo. Сборка для разработчиков - это сборка вашего собственного приложения, включающая инструменты разработчика Expo.

1. Expo Go - Предназначена для быстрого тестирования Expo и понимания основ. Это приложение для игровых площадок, поэтому оно ограничено и не подходит для создания проектов производственного уровня.

2. Сборка для разработки - Создайте сборку своего собственного приложения с помощью инструментов разработчика. Поддерживает пользовательские собственные модули. Предназначено для производственных проектов.

***Следующий шаг***
У вас есть проект и среда разработки. Теперь пора приступать к разработке.

# Приступайте к разработке

***Запустите сервер разработки***
Чтобы запустить сервер разработки, выполните следующую команду:

'''

npx expo start

'''

***Откройте приложение на своем устройстве***
После выполнения указанной выше команды в терминале появится QR-код. Отсканируйте его, чтобы открыть приложение на своем устройстве.

Если вы используете эмулятор Android или iOS Simulator, нажмите A или I соответственно, чтобы открыть приложение.

***Внесите первое изменение***
Откройте файл src/app/index.tsx в редакторе кода и внесите изменения.

'''

  <ThemedView style={styles.heroSection}>
       <AnimatedIcon />
       <ThemedText type="title" style={styles.title}>
           Welcome to&nbsp;Expo
           Привет, мир!
       </ThemedText>
     </ThemedView>

'''

***Структура файлов***
Ниже представлена структура файлов проекта по умолчанию.

* src/app - Содержит навигацию по файлам приложения.  Файловая структура каталога src/app определяет навигацию по приложению. В приложении есть два маршрута, заданных двумя файлами: src/app/index.tsx и src/app/explore.tsx.  Файл макета src/app/_layout.tsx настраивает навигатор вкладок с помощью специфичного для платформы компонента AppTabs.

* src/components - Содержит компоненты React Native, такие как themed-text.tsx, которые создают текстовые элементы, использующие цветовую схему приложения в светлом и темном режимах.  Некоторые компоненты имеют варианты для конкретных платформ с расширением .native.tsx для нативных приложений и расширением .tsx по умолчанию для веб-приложений (например, animated-icon.tsx и app-tabs.tsx).

* src/constants - Содержит файл theme.ts, в котором определены цвета, шрифты и интервалы, используемые во всем приложении.

* src/hooks - Содержит React Hooks, которые позволяют использовать общее поведение в разных компонентах.  Например, useTheme() — это хук, который возвращает текущий объект темы, а useColorScheme() определяет цветовую схему пользователя.  Некоторые хуки имеют платформозависимые варианты с расширением .web.ts.

* assets - В каталоге assets находится каталог expo.icon с иконкой приложения для iOS и подкаталог images с файлами адаптивных иконок для Android (android-icon-foreground.png, android-icon-background.png, android-icon-monochrome.png), splash-icon.png для заставки, favicon.png для веб-версии и иконки навигации по вкладкам.

* scripts - Содержит файл reset-project.js, который можно запустить с помощью команды npm run reset-project. Этот скрипт переместит каталоги src и scripts в /example и создаст новый каталог src/app с файлами index.tsx и _layout.tsx.

* app.json - Содержит параметры конфигурации проекта и называется app config. Эти параметры изменяют поведение вашего проекта при разработке, сборке, отправке и обновлении приложения.

* package.json - Файл package.json содержит зависимости, скрипты и метаданные проекта.  Каждый раз, когда в проект добавляется новая зависимость, она добавляется и в этот файл.

* tsconfig.json - Содержит правила, которые TypeScript будет использовать для обеспечения безопасности типов во всем проекте.

# Особенности
Шаблон проекта по умолчанию обладает следующими возможностями:

* Маршрутизация на основе файлов - В приложении есть два экрана: src/app/index.tsx и src/app/explore.tsx. Файл макета в src/app/_layout.tsx настраивает навигацию с помощью специфичного для платформы компонента AppTabs, который использует встроенные вкладки на Android и iOS и вкладки Expo Router UI в веб-версии.

* Поддержка Android, iOS и веб-версий - Этот проект можно открыть на Android, iOS и в браузере. Чтобы открыть веб-версию, после запуска проекта нажмите W в терминале.

* Изображения - Для статичных изображений можно использовать суффиксы @2x и @3x, чтобы предоставить изображения для экранов с разной плотностью пикселей.

* Светлый и тёмный режимы - В этом шаблоне реализована поддержка светлого и тёмного режимов. Хук useColorScheme() позволяет проверить текущую цветовую схему пользователя, чтобы соответствующим образом настроить цвета интерфейса.

* Анимации - Компонент src/components/animated-icon.native.tsx использует react-native-reanimated для создания анимированного оверлея и эффекта вращающегося свечения на нативных платформах. Веб-версия в src/components/animated-icon.tsx использует CSS-анимации, демонстрируя специфичный для платформы код с использованием расширений файлов.

# Следующие шаги

***Сброс настроек проекта***
Вы можете удалить шаблонный код и начать с чистого листа, создав новый проект. Выполните следующую команду, чтобы сбросить настройки проекта:

'''

npm run reset-project

'''

Эта команда переместит существующие файлы из папки app в папку app-example, а затем создаст новую папку app с новым файлом index.tsx.

***Разработка, проверка и развертывание***
Узнайте, как разрабатывать приложения, прочитав документацию в разделе «Разработка». Вы узнаете, как создавать элементы пользовательского интерфейса, добавлять модульные тесты, подключать нативные модули и многое другое. 

 После того как вы разработаете приложение, вы сможете показать его коллегам для проверки. 

 Наконец, вы сможете собрать проект и отправить его в магазины приложений.

***Пошаговое руководство***
 Пошаговое руководство по созданию приложения с помощью Expo от начала и до конца можно найти здесь. <https://docs.expo.dev/tutorial/introduction/>

# Инструменты для разработки

 При создании нового проекта с помощью Expo вам пригодятся следующие важные инструменты и веб-сайты.  На этой странице представлен список рекомендуемых инструментов. 

 ***EXPO CLI***
Expo CLI — это инструмент разработки, который устанавливается автоматически вместе с пакетом expo при создании нового проекта.  Вы можете использовать его с помощью npx (утилиты для запуска пакетов Node.js).

 Он создан для того, чтобы ускорить процесс разработки приложений.  Например, первое, что нужно сделать при работе с Expo CLI, — запустить сервер разработки с помощью команды npx expo start.

 Ниже приведен список распространенных команд, которые вы будете использовать при разработке приложения с помощью Expo CLI.

* npx expo start-Запускает сервер разработки (независимо от того, используете ли вы сборку для разработки или Expo Go).

* npx expo prebuild-Создает нативные каталоги для Android и iOS с помощью Prebuild.

* npx expo run:android-компилирует нативное Android-приложение локально.

* npx expo run:ios-Локально компилирует нативное iOS-приложение.

* npx expo install package-name-Используется для установки новой библиотеки или проверки и обновления определенных библиотек в вашем проекте с помощью опции --fix.

* npx expo lint-Настройка и конфигурирование ESLint. Если ESLint уже настроен, эта команда выполнит линтинг файлов вашего проекта.

В двух словах, Expo CLI позволяет разрабатывать, компилировать, запускать приложения и многое другое.  Дополнительные параметры и действия, которые можно выполнять с помощью Expo CLI, описаны в справочнике по Expo CLI.

***EAS CLI***
EAS CLI используется для входа в учетную запись Expo и компиляции приложения с помощью различных сервисов EAS, таких как Build, Update или Submit. Этот инструмент также можно использовать для:

* Опубликуйте свое приложение в магазинах приложений
* Создайте сборку приложения для разработки, предварительного просмотра или рабочую сборку
* Создавайте обновления по беспроводной сети (OTA)
* Управляйте учетными данными своего приложения
* Создайте специальный профиль подготовки для устройства iOS

Чтобы использовать EAS CLI, необходимо установить его на локальный компьютер глобально, выполнив команду:

'''

npm install --global eas-cli

'''

***Expo Doctor***
Expo Doctor — это инструмент командной строки, который используется для диагностики проблем в вашем проекте Expo. Чтобы воспользоваться им, выполните следующую команду в корневом каталоге вашего проекта:

'''

npx expo-doctor

'''

Эта команда выполняет проверку и анализирует кодовую базу вашего проекта на наличие распространенных проблем в файлах app config и package.json, совместимости зависимостей, файлах конфигурации и в целом на работоспособность проекта.  После завершения проверки Expo Doctor выводит результаты. 

 Если Expo Doctor обнаружит проблему, он предоставит ее описание и рекомендации по устранению или укажет, где можно получить помощь. 

 По умолчанию Expo Doctor сверяет пакеты вашего проекта с каталогом React Native и проверяет, правильно ли синхронизированы свойства app config при наличии нативных каталогов.  Эти проверки можно настроить в файле package.json вашего проекта.  Подробнее см. в разделах reactNativeDirectoryCheck и appConfigFieldsNotSyncedCheck. 

 Для получения информации об использовании можно также использовать команду npx expo-doctor --help.

 ***Orbit***
Orbit — это приложение для macOS, Windows и Linux, которое позволяет:

* Устанавливайте и запускайте сборки из EAS на физических устройствах и эмуляторах. 
* Устанавливайте и запускайте обновления из EAS на эмуляторах Android или iOS. 
* Запускайте проекты snack на эмуляторах Android или iOS. 
* Используйте локальные файлы для установки и запуска приложений.  Orbit поддерживает любые файлы .apk для Android, файлы .app, совместимые с iOS Simulator, а также приложения с самоподписанием. 
* Список закрепленных проектов доступен на панели управления EAS.

***Установка***
Вы можете скачать Orbit для Windows прямо из репозиториев [GitHub](https://github.com/expo/orbit/releases)

*Orbit использует Android SDK на macOS, Windows и Linux, а xcrun — только для управления устройствами на macOS, что требует установки Android Studio и Xcode.*

***Тестируйте прототипы с помощью Snack и Expo Go***

**Snack**
Snack — это браузерная среда разработки, работающая по принципу Expo Go. Это отличный способ делиться фрагментами кода и экспериментировать с React Native, не загружая никакие инструменты на свой компьютер.
 Чтобы воспользоваться Snack, перейдите на snack.expo.dev, отредактируйте компонент <Text> в App.js, выберите платформу (Android, iOS или веб) на правой панели и наблюдайте за изменениями в реальном времени.

**Expo Go**
Expo Go — это бесплатная площадка с открытым исходным кодом, где студенты и учащиеся могут опробовать React Native. Она работает с Android и iOS.

Подробнее о том, как её использовать:
* Нажмите на эту [ссылку](https://docs.expo.dev/get-started/set-up-your-environment/?mode=expo-go) чтобы перейти
* Выберите платформу для разработки. Где бы вы хотели разрабатывать?
* Выберите Expo Go. Как бы вы хотели разрабатывать?
* Следуйте инструкциям из этого руководства

*Примечание: Expo Go имеет ограниченные возможности и не подходит для создания проектов промышленного уровня. Используйте сборки для разработки.*

**expo-go CLI**
Интерфейс командной строки expo-go — это отдельный инструмент, который загружает бинарный файл Expo Go для конкретной платформы и версии SDK или выводит URL для его загрузки. Укажите версию SDK, чтобы закрепить конкретную версию, или не указывайте ее, чтобы загрузить последнюю версию, а также укажите платформу, чтобы загрузить нужный бинарный файл.

'''

npx expo-go download android latest
npx expo-go url ios latest

'''

Эта команда загружает приложение Expo Go в текущий каталог и кэширует его в папку ~/.expo.

*Интерфейс командной строки expo-go работает на устройствах Android, в эмуляторе Android и iOS Simulator. Согласно политике Apple, устройства iPhone в целом не поддерживают загрузку старых версий приложений, и интерфейс командной строки expo-go этого не поддерживает.*

***Каталог React Native***
Любая библиотека, совместимая с React Native, будет работать в проекте Expo, если для создания проекта используется сборка для разработки. 

reactnative.directory — это база данных библиотек React Native с возможностью поиска.  Если нужной вам библиотеки нет в Expo SDK, воспользуйтесь каталогом, чтобы найти совместимую библиотеку для своего проекта.

# Навигация в приложениях Expo и React Native

В основную библиотеку React Native не входит встроенное решение для навигации, поэтому вы можете выбрать библиотеку, которая лучше всего соответствует вашим потребностям.  Для приложений на Expo и React Native обычно выбирают между React Navigation и Expo Router.

***Зачем React Native-приложениям нужна библиотека навигации***
Ядро React Native включает в себя базовые компоненты пользовательского интерфейса, обработку сенсорных данных, API устройств и сетевые возможности, но не включает, среди прочего, функции хранения данных, камеру, карты, большинство датчиков устройства и навигацию! Эти возможности должны быть реализованы в библиотеках сообщества.

***React Navigation***
React Navigation — это библиотека навигации на основе компонентов, широко используемая в экосистеме React Native.  Она позволяет создавать навигаторы в виде стека, вкладок и выдвижных панелей полностью в коде, чтобы вы могли реализовать сложные последовательности действий, пользовательские переходы и UX-паттерны, специфичные для вашего приложения. 

 Библиотека поддерживает внешний вид, адаптированный под конкретную платформу, с плавной анимацией и жестами, унифицированную мобильную и веб-маршрутизацию, автоматические глубокие ссылки, статическую настройку маршрутов и широкие возможности настройки.

 [React Navigation: Get Started](https://reactnavigation.org/docs/getting-started)

 ***Expo Router (рекомендуется для проектов Expo)***
 Expo Router — это библиотека маршрутизации на основе файлов для проектов Expo и React Native. Следуя соглашению о структуре каталогов приложения, она преобразует файлы в маршруты и интегрируется с Expo для использования интерфейса командной строки Expo и сборки без дополнительной настройки. Библиотека также добавляет такие функции, как типизированные маршруты, динамические маршруты, отложенная сборка в режиме разработки, статический рендеринг для веба и автоматическая глубокая маршрутизация. 

 Новые проекты Expo, созданные с помощью npx create-expo-app@latest, по умолчанию включают Expo Router.

 [Introduction to Expo Router](https://docs.expo.dev/router/introduction/)

 [Manual installation](https://docs.expo.dev/router/installation/)

 [Core concepts](https://docs.expo.dev/router/basics/core-concepts/)


# Introduction

***О туториале***

В этом туториале создаётся универсальное приложение **StickerSmash** на **Expo**, которое работает на **Android, iOS и Web** с использованием одной кодовой базы.

Цель — познакомиться с Expo и основами **Expo SDK**.

***Что изучим***

- Создание приложения с помощью шаблона и TypeScript.
- Настройка двух экранов и нижней панели вкладок через Expo Router.
- Создание интерфейса с помощью Flexbox.
- Использование нативных кнопок и компонентов Expo UI.
- Выбор изображений из галереи устройства.
- Создание выбора эмодзи с помощью `FlatList`.
- Добавление жестов для взаимодействия с элементами.
- Создание и сохранение скриншотов.
- Настройка статус-бара, заставки и иконки приложения.

***Особенности платформ***

Приложение использует интерфейсы каждой платформы:

- **Android:** Material 3 для вкладок, кнопок и нижней панели.
- **iOS 26 и новее:** Liquid Glass для панели вкладок.
- **Web:** компоненты React Native.

**Expo UI** позволяет использовать компоненты Jetpack Compose и SwiftUI в React Native.

***Как проходить туториал***

Туториал состоит из **8 глав**, рассчитан примерно на 2 часа и построен по принципу обучения на практике.

Исходный код проекта: [StickerSmash на GitHub](https://github.com/expo/examples/tree/master/stickersmash).

Дополнительный вариант для новичков: [Build with AI tutorial](https://docs.expo.dev/tutorial/build-with-ai/introduction/).

***Пример кода***

Простой экран с текстом Hello world:

```
import { StyleSheet, Text, View } from 'react-native';

export default function Index() {
  return (
    <View style={styles.container}>
      <Text>Hello world!</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

**Основные компоненты:**

- `View` — контейнер.
- `Text` — отображение текста.
- `StyleSheet` — оформление элементов.
- `flex: 1` — занимает доступное пространство.

# Create your first app

***Создание проекта Expo***

Для создания нового проекта используется `create-expo-app` — инструмент для создания приложений React Native.

В терминале выполнить:

```
npx create-expo-app@latest StickerSmash
```

Выбрать версию Expo SDK: **Latest (SDK 58)**.

Перейти в папку проекта:

```
cd StickerSmash
```

Команда создаёт папку `StickerSmash` с готовым шаблоном, в который входят Expo Router и Expo UI.

***Подготовка ресурсов***

1. Скачать архив с ресурсами.
2. Распаковать его.
3. Заменить стандартные изображения в папке `assets/images`.
4. Открыть проект в редакторе кода, например VS Code.

***Сброс стандартного шаблона***

Чтобы начать разработку с нуля, выполнить:

```
npm run reset-project
```

Когда появится вопрос о переносе старых файлов в папку `example`, нажать **Enter**.

После выполнения в `src/app` останутся два основных файла:

- `index.tsx` — главный экран.
- `_layout.tsx` — настройка структуры приложения и навигации.

Остальные стандартные файлы переместятся в папку `example`.

***Запуск приложения***

Запустить сервер разработки:

```
npx expo start
```

После запуска появится QR-код:

- **Android:** открыть Expo Go и выбрать Scan QR.
- **iOS:** отсканировать QR-код стандартной камерой.
- **Web:** нажать `W` в терминале.

Для запуска на физическом iPhone компьютер и Expo Go должны быть авторизованы в одном аккаунте Expo.

Если нужно войти с компьютера:

```
npx expo login
```

***Редактирование главного экрана***

Файл `src/app/index.tsx` отвечает за первый экран приложения.

В React Native используются компоненты:

- `View` — контейнер для элементов.
- `Text` — отображение текста.
- `StyleSheet` — создание стилей.

Стили задаются через **JavaScript-объекты**, а не CSS, хотя многие свойства похожи.

Пример изменённого экрана:

```
import { Text, View, StyleSheet } from 'react-native';

export default function Index() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Home screen</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    alignItems: 'center',
    justifyContent: 'center',
  },
  text: {
    color: '#fff',
  },
});
```

***Основные свойства стилей***

- `flex: 1` — занимает всё доступное пространство.
- `backgroundColor` — цвет фона.
- `color` — цвет текста.
- `alignItems` — выравнивание элементов по горизонтали.
- `justifyContent` — выравнивание по вертикали.
- `#25292e` — цвет фона.
- `#fff` — белый цвет текста.

React Native поддерживает форматы цветов **HEX, RGBA, HSL**, а также названия цветов, например `red`, `green`, `blue`.


# Add navigation

***Основы Expo Router***

**Expo Router** — система навигации для React Native и Web, которая использует структуру файлов и папок для создания экранов и переходов между ними.

Основные правила:

- `src/app` — папка, в которой находятся экраны и настройки навигации.
- `_layout.tsx` — файл общей структуры экранов (заголовки, вкладки и навигация).
- `index.tsx` — главная страница, соответствует маршруту `/`.
- Каждый файл маршрута экспортирует React-компонент через `export default`.
- Android, iOS и Web используют общую структуру навигации.

***1. Добавление нового экрана***

Создать файл `src/app/about.tsx`.

```
import { Text, View, StyleSheet } from 'react-native';

export default function AboutScreen() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>About screen</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    justifyContent: 'center',
    alignItems: 'center',
  },
  text: {
    color: '#fff',
  },
});
```

В файле `src/app/_layout.tsx` настроить заголовки экранов с помощью `Stack.Screen`:

```
import { Stack } from 'expo-router';

export default function RootLayout() {
  return (
    <Stack>
      <Stack.Screen name="index" options={{ title: 'Home' }} />
      <Stack.Screen name="about" options={{ title: 'About' }} />
    </Stack>
  );
}
```

**Stack** — навигация в виде стека: экраны открываются поверх предыдущих.

***2. Переход между экранами***

Для перехода между страницами используется компонент `Link` из `expo-router`.

Пример для `src/app/index.tsx`:

```
import { Text, View, StyleSheet } from 'react-native';
import { Link } from 'expo-router';

export default function Index() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Home screen</Text>
      <Link href="/about" style={styles.button}>
        Go to About screen
      </Link>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    alignItems: 'center',
    justifyContent: 'center',
  },
  text: {
    color: '#fff',
  },
  button: {
    fontSize: 20,
    textDecorationLine: 'underline',
    color: '#fff',
  },
});
```

- `Link` — компонент-ссылка.
- `href="/about"` — путь к экрану About.
- `fontSize` — размер текста.
- `textDecorationLine` — оформление текста.
- `color` — цвет текста.

***3. Добавление страницы 404***

Если пользователь переходит на несуществующий маршрут, Expo Router показывает страницу ошибки.

Для создания собственной страницы нужно добавить файл `src/app/+not-found.tsx`.

```
import { View, StyleSheet } from 'react-native';
import { Link, Stack } from 'expo-router';

export default function NotFoundScreen() {
  return (
    <>
      <Stack.Screen options={{ title: 'Oops! Not Found' }} />
      <View style={styles.container}>
        <Link href="/" style={styles.button}>
          Go back to Home screen!
        </Link>
      </View>
    </>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    justifyContent: 'center',
    alignItems: 'center',
  },
  button: {
    fontSize: 20,
    textDecorationLine: 'underline',
    color: '#fff',
  },
});
```

Файл `+not-found.tsx` отвечает за отображение страницы 404. Ссылка `href="/"` возвращает на главный экран.

Проверить работу можно через адрес `http://localhost:8081/123`.

***4. Создание нижней панели вкладок (Bottom Tabs)***

Для группировки экранов в нижнюю панель создаётся специальная папка `(tabs)`.

Новая структура проекта:

```
src/
└── app/
    ├── _layout.tsx
    ├── +not-found.tsx
    └── (tabs)/
        ├── _layout.tsx
        ├── index.tsx
        └── about.tsx
```

- `(tabs)` — группа экранов с нижней панелью.
- `_layout.tsx` внутри `(tabs)` — настройка вкладок.
- `index.tsx` — главная вкладка.
- `about.tsx` — вкладка About.

Файлы `index.tsx` и `about.tsx` нужно переместить в папку `(tabs)`.

В корневом файле `src/app/_layout.tsx` указать:

```
import { Stack } from 'expo-router';

export default function RootLayout() {
  return (
    <Stack>
      <Stack.Screen name="(tabs)" options={{ headerShown: false }} />
    </Stack>
  );
}
```

`headerShown: false` — скрывает верхний заголовок.

***5. Настройка вкладок NativeTabs***

В файле `src/app/(tabs)/_layout.tsx` создаётся нижняя панель:

```
import { NativeTabs } from 'expo-router/native-tabs';

export default function TabLayout() {
  return (
    <NativeTabs>
      <NativeTabs.Trigger name="index">
        <NativeTabs.Trigger.Label>Home</NativeTabs.Trigger.Label>
      </NativeTabs.Trigger>
      <NativeTabs.Trigger name="about">
        <NativeTabs.Trigger.Label>About</NativeTabs.Trigger.Label>
      </NativeTabs.Trigger>
    </NativeTabs>
  );
}
```

- `NativeTabs` — нативная нижняя панель вкладок.
- `NativeTabs.Trigger` — отдельная вкладка.
- `NativeTabs.Trigger.Label` — название вкладки.

На Android и iOS используется системная панель вкладок. На Web отображаются названия вкладок в верхней части страницы.

***6. Добавление иконок и оформление вкладок***

Для добавления иконок используется `NativeTabs.Trigger.Icon`.

```
import { NativeTabs } from 'expo-router/native-tabs';

export default function TabLayout() {
  return (
    <NativeTabs
      tintColor="#ffd33d"
      backgroundColor="#25292e"
    >
      <NativeTabs.Trigger name="index">
        <NativeTabs.Trigger.Label>Home</NativeTabs.Trigger.Label>
        <NativeTabs.Trigger.Icon
          sf={{ default: 'house', selected: 'house.fill' }}
          md="home"
        />
      </NativeTabs.Trigger>

      <NativeTabs.Trigger name="about">
        <NativeTabs.Trigger.Label>About</NativeTabs.Trigger.Label>
        <NativeTabs.Trigger.Icon
          sf={{ default: 'info.circle', selected: 'info.circle.fill' }}
          md="info"
        />
      </NativeTabs.Trigger>
    </NativeTabs>
  );
}
```

**Иконки для разных платформ:**

- `sf` — названия иконок для iOS (SF Symbols).
- `md` — названия иконок для Android (Material Symbols).
- `default` — обычное состояние иконки.
- `selected` — иконка активной вкладки.

**Свойства оформления:**

- `tintColor` — цвет активной иконки и названия вкладки.
- `backgroundColor` — цвет фона панели.

На iOS 26 и новее используется эффект **Liquid Glass**, поэтому `backgroundColor` не изменяет фон панели.

***7. Цвета индикатора и эффекта нажатия***

Для Android можно дополнительно настроить цвета вкладок:

```
<NativeTabs
  tintColor="#ffd33d"
  backgroundColor="#25292e"
  indicatorColor="rgba(255, 211, 61, 0.2)"
  rippleColor="rgba(255, 211, 61, 0.3)"
>
```

- `indicatorColor` — цвет индикатора активной вкладки.
- `rippleColor` — цвет эффекта нажатия на вкладку.

На Web `indicatorColor` задаёт фон активной вкладки.

**Итог:** Expo Router позволяет создавать переходы между экранами, страницы 404 и нижнюю панель вкладок с помощью структуры файлов и компонентов навигации.

# Build a screen

***Создание первого экрана***

В этой главе создаётся первый экран приложения **StickerSmash**.

На экране будут:
- Изображение в верхней части.
- Две кнопки в нижней части:
  - `Choose a photo` — выбрать изображение с устройства.
  - `Use this photo` — использовать изображение приложения.

Для создания экрана используются **Pressable**, **Expo Image**, **Expo UI** и другие компоненты React Native.

***1. Разделение экрана на элементы***

Основные элементы интерфейса:

- Большое изображение в верхней половине экрана.
- Две кнопки в нижней половине.
- Первая кнопка имеет жёлтый фон, иконку и текст, расположенные в одну строку.

***2. Отображение изображения***

Для отображения изображений используется библиотека **expo-image**. Компонент `Image` поддерживает локальные изображения и изображения из интернета.

Файл `src/app/(tabs)/index.tsx`:

```tsx
import { Platform, View, StyleSheet } from 'react-native';
import { Image } from 'expo-image';
import { SafeAreaView } from 'react-native-safe-area-context';

const PlaceholderImage = require('@/assets/images/background-image.png');

export default function Index() {
  return (
    <SafeAreaView style={styles.container}>
      <View style={styles.imageContainer}>
        <Image source={PlaceholderImage} style={styles.image} />
      </View>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    alignItems: 'center',
  },
  imageContainer: {
    flex: 1,
    paddingTop: Platform.select({ web: 96, default: 20 }),
  },
  image: {
    width: 320,
    height: 440,
    borderRadius: 18,
  },
});
```

**Основные компоненты и свойства:**

- `Image` — отображение изображения.
- `SafeAreaView` — размещение содержимого в безопасной области экрана.
- `require()` — подключение локального изображения.
- `Platform.select()` — выбор значения в зависимости от платформы.
- `borderRadius` — скругление углов изображения.

***3. Разделение компонентов по файлам***

Чтобы код было удобнее поддерживать, создаются отдельные компоненты.

В папке `src` создаётся папка `components`, а внутри файл `image-viewer.tsx`.

`src/components/image-viewer.tsx`:

```tsx
import { StyleSheet } from 'react-native';
import { Image, type ImageSource } from 'expo-image';

type Props = {
  imgSource: ImageSource;
};

export default function ImageViewer({ imgSource }: Props) {
  return <Image source={imgSource} style={styles.image} />;
}

const styles = StyleSheet.create({
  image: {
    width: 320,
    height: 440,
    borderRadius: 18,
  },
});
```

Теперь компонент можно использовать в `src/app/(tabs)/index.tsx`:

```tsx
import { Platform, StyleSheet, View } from 'react-native';
import { SafeAreaView } from 'react-native-safe-area-context';

import ImageViewer from '@/components/image-viewer';

const PlaceholderImage = require('@/assets/images/background-image.png');

export default function Index() {
  return (
    <SafeAreaView style={styles.container}>
      <View style={styles.imageContainer}>
        <ImageViewer imgSource={PlaceholderImage} />
      </View>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    alignItems: 'center',
  },
  imageContainer: {
    flex: 1,
    paddingTop: Platform.select({ web: 96, default: 20 }),
  },
});
```

Файлы компонентов размещаются вне `src/app`, потому что внутри `src/app` находятся маршруты и файлы навигации.

***4. Создание кнопок с Pressable***

**Pressable** — компонент React Native для обработки нажатий. Он поддерживает обычные нажатия и длительное удержание.

Создаём файл `src/components/button.tsx`:

```tsx
import { StyleSheet, View, Pressable, Text } from 'react-native';

type Props = {
  label: string;
  onPress?: () => void;
};

export default function Button({ label, onPress }: Props) {
  return (
    <View style={styles.buttonContainer}>
      <Pressable style={styles.button} onPress={onPress}>
        <Text style={styles.buttonLabel}>{label}</Text>
      </Pressable>
    </View>
  );
}

const styles = StyleSheet.create({
  buttonContainer: {
    width: 320,
    height: 68,
    alignItems: 'center',
    justifyContent: 'center',
  },
  button: {
    height: 48,
    paddingHorizontal: 20,
    borderRadius: 24,
    alignItems: 'center',
    justifyContent: 'center',
    flexDirection: 'row',
    gap: 8,
  },
  buttonLabel: {
    color: '#fff',
    fontSize: 16,
  },
});
```

Свойство `onPress` определяет действие при нажатии на кнопку.

Добавляем кнопки в `src/app/(tabs)/index.tsx`:

```tsx
<View style={styles.footerContainer}>
  <Button label="Choose a photo" onPress={() => alert('You pressed a button.')} />
  <Button label="Use this photo" onPress={() => alert('You pressed a button.')} />
</View>
```

Для контейнера кнопок используется стиль:

```tsx
footerContainer: {
  flex: 1 / 3,
  alignItems: 'center',
},
```

***5. Улучшение внешнего вида кнопки***

Для разных вариантов оформления добавляется свойство `theme`.

В `src/components/button.tsx` подключается `SymbolView` из `expo-symbols`, чтобы отображать иконки.

```tsx
import { StyleSheet, View, Pressable, Text } from 'react-native';
import { SymbolView } from 'expo-symbols';

type Props = {
  label: string;
  theme?: 'primary';
  onPress?: () => void;
};

export default function Button({ label, theme, onPress }: Props) {
  if (theme === 'primary') {
    return (
      <View style={styles.buttonContainer}>
        <Pressable style={[styles.button, styles.primaryButton]} onPress={onPress}>
          <SymbolView
            name={{ ios: 'photo', android: 'image', web: 'image' }}
            size={18}
            tintColor="#25292e"
          />
          <Text style={[styles.buttonLabel, { color: '#25292e' }]}>
            {label}
          </Text>
        </Pressable>
      </View>
    );
  }

  return (
    <View style={styles.buttonContainer}>
      <Pressable style={styles.button} onPress={onPress}>
        <Text style={styles.buttonLabel}>{label}</Text>
      </Pressable>
    </View>
  );
}

const styles = StyleSheet.create({
  buttonContainer: {
    width: 320,
    height: 68,
    alignItems: 'center',
    justifyContent: 'center',
  },
  button: {
    height: 48,
    paddingHorizontal: 20,
    borderRadius: 24,
    alignItems: 'center',
    justifyContent: 'center',
    flexDirection: 'row',
    gap: 8,
  },
  primaryButton: {
    backgroundColor: '#ffd33d',
  },
  buttonLabel: {
    color: '#fff',
    fontSize: 16,
  },
});
```

Для первой кнопки указываем тему:

```tsx
<Button
  theme="primary"
  label="Choose a photo"
  onPress={() => alert('You pressed a button.')}
/>
```

**Важные особенности:**

- `theme="primary"` — включает основное оформление кнопки.
- `SymbolView` — отображает иконку для разных платформ.
- `name` — задаёт названия иконок для iOS, Android и Web.
- `[styles.button, styles.primaryButton]` — объединяет несколько стилей.
- `tintColor` — цвет иконки.

***6. Использование нативных кнопок через Expo UI***

**Expo UI** позволяет использовать нативные компоненты платформ:

- Android — Jetpack Compose.
- iOS — SwiftUI.
- Web — обычные компоненты React Native.

Для Android дополнительно устанавливается библиотека:

```bash
npx expo install @expo/material-symbols
```

Перед установкой нужно остановить сервер сочетанием `Ctrl + C`.

**Кнопка для Android**

Создаём `src/components/button.android.tsx`:

```tsx
import { StyleSheet, View } from 'react-native';
import {
  Host,
  Button as ComposeButton,
  TextButton,
  Icon,
  Row,
  Text,
} from '@expo/ui/jetpack-compose';

type Props = {
  label: string;
  theme?: 'primary';
  onPress?: () => void;
};

export default function Button({ label, theme, onPress }: Props) {
  if (theme === 'primary') {
    return (
      <View style={styles.buttonContainer}>
        <Host matchContents>
          <ComposeButton
            onClick={onPress}
            colors={{ containerColor: '#ffd33d', contentColor: '#25292e' }}>
            <Row verticalAlignment="center" horizontalArrangement={{ spacedBy: 8 }}>
              <Icon
                source={require('@expo/material-symbols/image.xml')}
                size={18}
                tint="#25292e"
              />
              <Text color="#25292e">{label}</Text>
            </Row>
          </ComposeButton>
        </Host>
      </View>
    );
  }

  return (
    <View style={styles.buttonContainer}>
      <Host matchContents>
        <TextButton onClick={onPress} colors={{ contentColor: '#fff' }}>
          <Text color="#fff">{label}</Text>
        </TextButton>
      </Host>
    </View>
  );
}

const styles = StyleSheet.create({
  buttonContainer: {
    width: 320,
    height: 68,
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

**Кнопка для iOS**

Создаём `src/components/button.ios.tsx`:

```tsx
import { StyleSheet, View } from 'react-native';
import { Host, Button as SwiftUIButton } from '@expo/ui/swift-ui';
import {
  buttonStyle,
  controlSize,
  foregroundStyle,
  tint,
} from '@expo/ui/swift-ui/modifiers';

type Props = {
  label: string;
  theme?: 'primary';
  onPress?: () => void;
};

export default function Button({ label, theme, onPress }: Props) {
  if (theme === 'primary') {
    return (
      <View style={styles.buttonContainer}>
        <Host matchContents>
          <SwiftUIButton
            label={label}
            systemImage="photo"
            onPress={onPress}
            modifiers={[
              buttonStyle('borderedProminent'),
              controlSize('large'),
              tint('#ffd33d'),
              foregroundStyle('#25292e'),
            ]}
          />
        </Host>
      </View>
    );
  }

  return (
    <View style={styles.buttonContainer}>
      <Host matchContents>
        <SwiftUIButton
          label={label}
          onPress={onPress}
          modifiers={[
            buttonStyle('borderless'),
            controlSize('large'),
            foregroundStyle('#fff'),
          ]}
        />
      </Host>
    </View>
  );
}

const styles = StyleSheet.create({
  buttonContainer: {
    width: 320,
    height: 68,
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

**Основные понятия:**

- `Host` — контейнер для отображения нативных компонентов Expo UI.
- `ComposeButton` — кнопка Android.
- `SwiftUIButton` — кнопка iOS.
- `modifiers` — дополнительные настройки внешнего вида компонентов iOS.
- `matchContents` — размер контейнера под содержимое.

***7. Платформенные файлы***

React Native поддерживает отдельные файлы для разных платформ. Metro автоматически выбирает подходящий файл при импорте компонента.

Структура папки `src/components`:

```text
components/
├── button.tsx          # Web
├── button.android.tsx  # Android
├── button.ios.tsx      # iOS
└── image-viewer.tsx    # Общий компонент
```

Все три версии кнопки используют одинаковые свойства (`label`, `theme`, `onPress`), поэтому файл главного экрана менять не нужно.

После создания файлов снова запустить сервер:

```bash
npx expo start
```

# Use an image picker

***1. Установка библиотеки***

`expo-image-picker` — библиотека для выбора изображений и видео из галереи устройства.

```bash
npx expo install expo-image-picker
```

***2. Выбор изображения***

В `src/app/(tabs)/index.tsx` импортировать библиотеку:

```tsx
import * as ImagePicker from 'expo-image-picker';
```

Создать функцию выбора изображения:

```tsx
const pickImageAsync = async () => {
  const result = await ImagePicker.launchImageLibraryAsync({
    mediaTypes: ['images'],
    allowsEditing: true,
    quality: 1,
  });

  if (!result.canceled) {
    console.log(result);
  } else {
    alert('You did not select any image.');
  }
};
```

**Основные параметры:**
- `mediaTypes` — тип выбираемых файлов.
- `allowsEditing` — возможность обрезать изображение.
- `quality` — качество изображения.
- `canceled` — отменён ли выбор.

***3. Подключение кнопки***

Передать функцию `pickImageAsync` в `onPress` первой кнопки:

```tsx
<Button
  theme="primary"
  label="Choose a photo"
  onPress={pickImageAsync}
/>
```

***4. Отображение выбранного изображения***

Для хранения адреса изображения используется `useState`:

```tsx
import { useState } from 'react';

const [selectedImage, setSelectedImage] = useState<string | undefined>(undefined);
```

Сохранить адрес выбранного изображения:

```tsx
if (!result.canceled) {
  setSelectedImage(result.assets[0].uri);
}
```

Передать изображение компоненту:

```tsx
<ImageViewer
  imgSource={PlaceholderImage}
  selectedImage={selectedImage}
/>
```

***5. Обновление ImageViewer***

В файле `src/components/image-viewer.tsx`:

```tsx
import { StyleSheet } from 'react-native';
import { Image, type ImageSource } from 'expo-image';

type Props = {
  imgSource: ImageSource;
  selectedImage?: string;
};

export default function ImageViewer({ imgSource, selectedImage }: Props) {
  const imageSource = selectedImage ? { uri: selectedImage } : imgSource;

  return <Image source={imageSource} style={styles.image} />;
}

const styles = StyleSheet.create({
  image: {
    width: 320,
    height: 440,
    borderRadius: 18,
  },
});
```

**Итог:** `expo-image-picker` позволяет выбрать изображение из галереи, `useState` хранит его URI, а `ImageViewer` отображает выбранное изображение вместо стандартного.

# Create a modal

***Показ кнопок после выбора изображения***

В `src/app/(tabs)/index.tsx` добавляем состояние для отображения кнопок:

```tsx
const [showAppOptions, setShowAppOptions] = useState<boolean>(false);
```

- После выбора изображения вызываем `setShowAppOptions(true)`.
- Кнопка **Use this photo** также включает это состояние.
- После выбора изображения появляются три кнопки: **Reset**, **Add Sticker** и **Save**.

***Кнопки действий***

Создаём платформенные компоненты в `src/components`:

- `circle-button.android.tsx`, `circle-button.ios.tsx`, `circle-button.tsx` — круглая кнопка с плюсом.
- `icon-button.android.tsx`, `icon-button.ios.tsx`, `icon-button.tsx` — кнопки с иконкой и подписью.

Для каждой платформы используются свои элементы:
- Android — Expo UI и Material Symbols.
- iOS — SwiftUI и SF Symbols.
- Web — React Native `Pressable` и `SymbolView`.

В `index.tsx` добавляем обработчики:
- `onReset()` — возвращает экран к выбору изображения.
- `onAddSticker()` — открывает выбор стикера.
- `onSaveImageAsync()` — пока без реализации.

***Создание EmojiPicker***

Создаём `src/components/emoji-picker.tsx`.

Используем `BottomSheet` из `@expo/ui`:

```tsx
<BottomSheet
  isPresented={isVisible}
  onDismiss={onClose}
  snapPoints={['half']}
  containerColor="#25292e"
>
  <RNHostView>
    {children}
  </RNHostView>
</BottomSheet>
```

- `isPresented` — управляет открытием окна.
- `onDismiss` — вызывается при закрытии.
- `snapPoints` — задаёт высоту окна.
- `RNHostView` позволяет использовать React Native компоненты внутри BottomSheet.

В `index.tsx` добавляем состояние:

```tsx
const [isModalVisible, setIsModalVisible] = useState<boolean>(false);
```

При нажатии на кнопку плюса устанавливаем `true`, при закрытии — `false`.

***Список эмодзи***

Создаём `src/components/emoji-list.tsx`.

- Храним изображения эмодзи в массиве `emoji`.
- `FlatList` отображает их сеткой из трёх колонок (`numColumns={3}`).
- При нажатии вызываются `onSelect(item)` и `onCloseModal()`.

***Отображение выбранного стикера***

Создаём `src/components/emoji-sticker.tsx`.

Компонент принимает:
- `imageSize` — размер стикера.
- `stickerSource` — изображение эмодзи.

В `index.tsx` добавляем состояние выбранного эмодзи:

```tsx
const [pickedEmoji, setPickedEmoji] = useState<ImageSource | undefined>(undefined);
```

Передаём функцию выбора в список:

```tsx
<EmojiList
  onSelect={setPickedEmoji}
  onCloseModal={onModalClose}
/>
```

Показываем стикер, только если эмодзи выбран:

```tsx
{pickedEmoji && (
  <EmojiSticker imageSize={40} stickerSource={pickedEmoji} />
)}
```

**Результат:** пользователь может открыть BottomSheet, выбрать эмодзи и увидеть его поверх изображения.

# Add gestures

***Настройка Gesture Handler***

Чтобы жесты работали во всём приложении, в `src/app/_layout.tsx` оборачиваем `Stack`:

```tsx
<GestureHandlerRootView>
  <Stack>
    <Stack.Screen name="(tabs)" options={{ headerShown: false }} />
  </Stack>
</GestureHandlerRootView>
```

***Анимированный стикер***

В `emoji-sticker.tsx` используем `Animated.View` из `react-native-reanimated` вместо обычного `View`.

- Стикер позиционируется относительно изображения через `position: 'absolute'`.
- В `index.tsx` оборачиваем `ImageViewer` и `EmojiSticker` в общий `View`.

***Жест двойного нажатия (Double Tap)***

Используем `useTapGesture` из `react-native-gesture-handler` и анимацию `withSpring` из Reanimated.

```tsx
const scaleImage = useSharedValue(imageSize);

const doubleTap = useTapGesture({
  numberOfTaps: 2,
  onActivate: () => {
    scaleImage.set(
      scaleImage.get() === imageSize ? imageSize * 2 : imageSize
    );
  },
});
```

- `useSharedValue` хранит изменяемое значение размера.
- Двойное нажатие увеличивает стикер в два раза, повторное возвращает исходный размер.
- `useAnimatedStyle` обновляет ширину и высоту с анимацией `withSpring`.

***Перетаскивание стикера (Pan)***

Добавляем координаты положения:

```tsx
const translateX = useSharedValue(0);
const translateY = useSharedValue(0);
```

Для перемещения используем `usePanGesture`. Функция `clamp()` ограничивает координаты, чтобы стикер не выходил за пределы изображения.

Размеры изображения: `320 × 440`.

```tsx
const drag = usePanGesture({
  onUpdate: event => {
    translateX.set(clamp(
      translateX.get() + event.changeX,
      0,
      IMAGE_WIDTH - scaleImage.get()
    ));
    translateY.set(clamp(
      translateY.get() + event.changeY,
      0,
      IMAGE_HEIGHT - scaleImage.get()
    ));
  },
});
```

Объединяем жесты:

```tsx
const gesture = useSimultaneousGestures(drag, doubleTap);
```

В `stickerStyle` добавляем `transform` для перемещения:

```tsx
transform: [
  { translateX: translateX.get() },
  { translateY: translateY.get() },
],
```

При изменении размера стикера его координаты тоже ограничиваются через `clamp()`, чтобы он оставался внутри изображения.

Для `Image` устанавливаем `pointerEvents: 'none'`, чтобы браузер не перехватывал перетаскивание на Web.

**Результат:** двойное нажатие увеличивает или уменьшает стикер, а перетаскивание позволяет перемещать его по изображению, не выходя за его границы.

# Take a screenshot

***Установка библиотек***

Устанавливаем библиотеки для создания и сохранения скриншотов:

```bash
npx expo install react-native-view-shot html2canvas-pro expo-media-library
```

- `react-native-view-shot` — создание скриншота компонента `View`.
- `expo-media-library` — сохранение изображения в галерею на Android и iOS.
- `html2canvas-pro` — поддержка создания скриншотов в Web.

***Запрос разрешений***

В `index.tsx` используем `usePermissions()` из `expo-media-library`:

```tsx
const [permissionResponse, requestPermission] =
  MediaLibrary.usePermissions({ writeOnly: true });

useEffect(() => {
  if (!permissionResponse?.granted) {
    requestPermission();
  }
}, []);
```

`writeOnly: true` запрашивает разрешение только на сохранение файлов.

***Создание ссылки на изображение***

Чтобы сделать скриншот нужной области, используем `useRef` и `captureRef`.

```tsx
const imageRef = useRef<ComponentRef<typeof View>>(null);
```

Передаём ссылку в `View`, который содержит изображение и стикер:

```tsx
<View ref={imageRef} collapsable={false}>
  <ImageViewer imgSource={PlaceholderImage} selectedImage={selectedImage} />
  {pickedEmoji && <EmojiSticker imageSize={40} stickerSource={pickedEmoji} />}
</View>
```

`collapsable={false}` не позволяет React Native удалить этот `View`, чтобы его можно было захватить.

***Создание и сохранение скриншота***

На Android и iOS используем `captureRef()` и `MediaLibrary.Asset.create()`:

```tsx
const localUri = await captureRef(imageRef, {
  height: 440,
  quality: 1,
});

await MediaLibrary.Asset.create(localUri);
```

`captureRef()` возвращает URI изображения, который затем сохраняется в галерею.

***Сохранение скриншота в Web***

В браузере вместо Media Library скачиваем изображение через ссылку:

```tsx
const dataUrl = await captureRef(imageRef, {
  format: 'jpg',
  quality: 0.95,
  result: 'data-uri',
});

const link = document.createElement('a');
link.download = 'sticker-smash.jpeg';
link.href = dataUrl;
link.click();
```

Для разделения платформ используем `Platform.OS`:

- Android/iOS — сохраняем через `MediaLibrary.Asset.create()`.
- Web — скачиваем JPEG-файл через HTML-ссылку.

**Результат:** кнопка Save создаёт скриншот изображения вместе со стикером и сохраняет его в галерею или скачивает на компьютер.

# Configure status bar, splash screen and app icon

***1. Configure the status bar***

Библиотека `expo-status-bar` уже установлена в проекте.

В `src/app/_layout.tsx` импортируем `StatusBar` и добавляем его после `Stack`:

```tsx
import { StatusBar } from 'expo-status-bar';

// Внутри GestureHandlerRootView:
<Stack>
  {/* screens */}
</Stack>
<StatusBar style="light" />
```

- `style="light"` — светлые иконки и текст статус-бара на тёмном фоне.

***2. App icon***

Иконка приложения находится в `assets/images/icon.png` (1024 × 1024).

В `app.json` путь задаётся свойством `icon`:

```json
"icon": "./assets/images/icon.png"
```

- Android использует `android.adaptiveIcon` с отдельными изображениями переднего плана, фона и монохромной иконки.
- iOS по умолчанию использует `./assets/expo.icon`. Чтобы использовать общую иконку, нужно удалить свойство `ios.icon`.
- В Expo Go иконка не отображается — её можно проверить после сборки приложения.

***3. Splash screen***

Splash screen — экран загрузки, который показывается до появления содержимого приложения.

Плагин `expo-splash-screen` уже настроен в `app.json`. Меняем цвет фона на тёмный:

```json
[
  "expo-splash-screen",
  {
    "backgroundColor": "#25292e",
    "image": "./assets/images/splash-icon.png",
    "imageWidth": 76
  }
]
```

- `backgroundColor` — цвет фона.
- `image` — изображение по центру экрана.
- `imageWidth` — ширина изображения.

**Важно:** проверить splash screen через Expo Go или development build нельзя. Для этого нужна preview- или production-сборка приложения.

# Learning resources

После создания приложения можно изучить дополнительные инструменты и технологии, которые использовались в проекте.

***Build your project into an app***

Для создания нового проекта используем `npx create-expo-app@latest`, затем [настраиваем среду разработки](https://docs.expo.dev/get-started/set-up-your-environment/).

Полезные ресурсы Expo:

- [Development tools](https://docs.expo.dev/develop/tools/) — инструменты разработки.
- [Development builds](https://docs.expo.dev/develop/development-builds/introduction/) — сборка для тестирования на устройстве или эмуляторе.
- [Development overview](https://docs.expo.dev/workflow/overview/) — основные этапы разработки приложения.
- [Expo Router](https://docs.expo.dev/router/introduction/) — навигация и маршрутизация.
- [Expo UI](https://docs.expo.dev/versions/latest/sdk/ui/) — нативные компоненты Android и iOS.
- [App icon и splash screen](https://docs.expo.dev/develop/user-interface/splash-screen-and-app-icon/) — настройка иконки и экрана загрузки.
- [App distribution](https://docs.expo.dev/deploy/build-project/) и [submission](https://docs.expo.dev/deploy/submit-to-app-stores/) — сборка и публикация приложения.
- [Debugging](https://docs.expo.dev/debugging/runtime-issues/) — поиск и исправление ошибок.

***Learning***

**React**

Важно изучить компоненты и API React:
- [Quick Start](https://react.dev/learn)
- [Hooks](https://react.dev/reference/react/hooks)

**React Native**

Основы и полезные API:
- [Getting Started](https://reactnative.dev/docs/getting-started)
- [View](https://reactnative.dev/docs/view) и [Text](https://reactnative.dev/docs/text)
- [Platform-specific code](https://reactnative.dev/docs/platform-specific-code)
- [Lists](https://reactnative.dev/docs/using-a-listview)
- [Height and Width](https://reactnative.dev/docs/height-and-width)
- [Flexbox](https://reactnative.dev/docs/flexbox)

**Gestures and animations**

- [React Native Gesture Handler](https://docs.swmansion.com/react-native-gesture-handler/docs/) — обработка жестов.
- [React Native Reanimated](https://docs.swmansion.com/react-native-reanimated/docs/fundamentals/getting-started) — анимации.

***Join the community***

Присоединиться к сообществу Expo и задавать вопросы можно в [Discord](https://chat.expo.dev/).
