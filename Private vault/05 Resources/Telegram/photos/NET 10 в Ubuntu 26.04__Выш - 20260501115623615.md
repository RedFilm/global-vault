


## **====2026-05-01-11 56:23:618====**


**Forwarded from [Библиотека шарписта | C#, F#, .NET, ASP.NET](https://t.me/csharpproglib/7003)**

[[photo_1508914979_0 - 20260501115623607.jpg]]

🤩 **.NET 10 в Ubuntu 26.04**

Вышел Ubuntu 26.04 LTS. Вместе с ним официальная поддержка .NET 10 прямо из стандартного репозитория. 

Две команды и SDK готов:
```
sudo apt update
sudo apt install dotnet-sdk-10.0
```

Проверить, что всё работает:
```
dotnet run - << 'EOF'
using System.Runtime.InteropServices;

Console.WriteLine($"Hello {RuntimeInformation.OSDescription} from .NET {RuntimeInformation.FrameworkDescription}");
EOF
```

Вывод будет примерно таким:
```
Hello Ubuntu Resolute Raccoon from .NET .NET 10.0.5
```

Это так называемый **file-based app**. Он передаётся через `stdin` напрямую в `dotnet run`. Стандартный unix-подход.

Контейнеры

Образы с тегом `resolute` уже доступны. Если вы использовали `-noble`, достаточно поменять суффикс:
```
sed -i "s/noble/resolute/g" Dockerfile.chiseled
```

После этого собрать и запустить с ограничениями ресурсов:
```
docker build --pull -t aspnetapp -f Dockerfile.chiseled .
docker run --rm -it -p 8000:8080 -m 50mb --cpus .5 aspnetapp
```

Chiseled-образы остались, ничего не убрали

**Native AOT**

Если нужен маленький бинарь с быстрым стартом — `dotnet-sdk-aot-10.0` теперь в репозитории Ubuntu.

Установка:
```
apt install -y dotnet-sdk-aot-10.0 clang
```

Публикация простого приложения:
```
dotnet publish app.cs
```

Результат:
```
1.4M    artifacts/app/app
3.0M    artifacts/app/app.dbg
```

Запуск занял **3 миллисекунды**. Для веб-сервиса с `PublishAot=true` итоговый размер около 13 МБ вместе с метаданными `System.Text.Json`.

.NET 8 и 9 не входят в основной репозиторий Ubuntu 26.04, но доступны через отдельный PPA от Canonical:
```
apt install -y software-properties-common
add-apt-repository ppa:dotnet/backports
```

После подключения появятся пакеты `dotnet-sdk-8.0`, `dotnet-sdk-9.0` и соответствующие `aspnetcore-runtime-*`. Поддержка там на уровне "best-effort", то есть официально, но без гарантий уровня LTS.

**Что важно**

Ubuntu 26.04 принёс три заметных изменения на уровне ОС:

• Linux 7.0 — команда .NET начнёт тестирование, как только получит VM.

• Постквантовая криптография — поддержка уже есть в .NET 10.

• Удаление cgroup v1. Переход на cgroup v2 в .NET сделали несколько лет назад, так что сломаться ничего не должно.

Если переходите на Ubuntu 26.04 в продакшне, то всё основное готово с первого дня.

➡️ [**Блог разработчиков**](https://clc.to/XizCjA)

📍 Навигация: [**Вакансии**](https://clc.to/_cHBcg)** •** [**Задачи**](http://t.me/csharpproglib) • [**Собесы**](https://clc.to/B3RB2g)

🐸 [**Библиотека шарписта**](http://t.me/csharpproglib)

#async_news