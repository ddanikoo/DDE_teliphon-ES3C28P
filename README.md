# DDE_telifon

**Version:** 0.9.0  
**Author:** Дамзин Даниэль Дмитриевич  
**Board:** ES3C28P (ESP32-S3)

Custom firmware that turns the ES3C28P into a compact handheld device with a full touch UI.

## Features

- Persistent status bar (Wi-Fi signal, SSID, battery %, NTP clock)
- Bilingual interface (English / Russian)
- Deep sleep with power-button wake-up
- PSRAM-aware memory management for stable HTTPS and media

## Applications

| App | Description |
|-----|-------------|
| **Launcher** | Scrollable app list |
| **Calculator** | Basic arithmetic |
| **DeepSeek** | AI chat (API key from NVS or SD) |
| **Games** | Hockey 1vs1, Block Blast, Snake, Arkanoid |
| **Radio** | Internet radio |
| **Recorder** | Voice recorder to SD |
| **SD Browser** | View TXT, JPG, play WAV & AVI |
| **Files to SD** | Upload files from phone via Wi-Fi + QR |
| **Settings** | Wi-Fi, brightness, network test, Music LED, idle timeout, timezone, AVI FPS |

## Hardware

- Display: 2.8" ILI9341 (320×240)
- Touch: FT6336G
- Audio: ES8311 + amplifier
- Storage: SD_MMC + LittleFS
- Power button on GPIO21 (deep sleep / wake)

## Build

Arduino IDE / PlatformIO with ESP32 Arduino core ≥ 2.x.  
Required libraries: Adafruit GFX, Adafruit ILI9341, JPEGDEC, ESP32-audioI2S (patched), etc.  
See `board_config.h` for pin definitions.

## Notes

- API key for DeepSeek can be placed in `/deepseek.key` on the SD card or entered in the UI.
- Large buffers (chat history, file lists, framebuffers) are allocated in PSRAM.
- Idle timeout and brightness are stored in NVS.

---

# DDE_telifon

**Версия:** 0.9.0  
**Автор:** Дамзин Даниэль Дмитриевич  
**Плата:** ES3C28P (ESP32-S3)

Прошивка, превращающая ES3C28P в компактное сенсорное устройство с полноценным интерфейсом.

## Возможности

- Постоянный статусбар (сигнал Wi-Fi, SSID, заряд батареи, часы по NTP)
- Двуязычный интерфейс (русский / английский)
- Глубокий сон с пробуждением кнопкой питания
- Аккуратная работа с PSRAM для стабильного HTTPS и медиа

## Приложения

| Приложение | Описание |
|------------|----------|
| **Лаунчер** | Прокручиваемый список приложений |
| **Калькулятор** | Базовые вычисления |
| **DeepSeek** | AI-чат (ключ API из NVS или с SD) |
| **Игры** | Хоккей 1vs1, Block Blast, Змейка, Арканоид |
| **Радио** | Интернет-радио |
| **Диктофон** | Запись голоса на SD |
| **Браузер SD** | TXT, JPG, воспроизведение WAV и AVI |
| **Файлы на SD** | Загрузка файлов с телефона по Wi-Fi + QR |
| **Настройки** | Wi-Fi, яркость, тест сети, Music LED, таймер бездействия, часовой пояс, FPS в AVI |

## Оборудование

- Дисплей: 2.8" ILI9341 (320×240)
- Сенсор: FT6336G
- Аудио: ES8311 + усилитель
- Память: SD_MMC + LittleFS
- Кнопка питания на GPIO21 (глубокий сон / пробуждение)

## Сборка

Arduino IDE / PlatformIO, ядро ESP32 Arduino ≥ 2.x.  
Нужные библиотеки: Adafruit GFX, Adafruit ILI9341, JPEGDEC, ESP32-audioI2S (с патчем) и др.  
Распиновка — в `board_config.h`.

## Примечания

- Ключ DeepSeek можно положить в файл `/deepseek.key` на SD или ввести в интерфейсе.
- Крупные буферы (история чата, списки файлов, кадровые буферы) выделяются в PSRAM.
- Таймер бездействия и яркость сохраняются в NVS.

