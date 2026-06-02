# 🦙 Установка Ollama для Nova AI

## ⚡ БЫСТРАЯ УСТАНОВКА (Windows)

### Шаг 1: Скачать и установить

**Вариант A: Через winget (рекомендуется)**
```powershell
winget install Ollama.Ollama
```

**Вариант B: Вручную**
1. Зайди на https://ollama.com/download
2. Скачай установщик для Windows
3. Запусти `OllamaSetup.exe`
4. Нажми "Install"

### Шаг 2: Проверка установки

Открой PowerShell и введи:
```powershell
ollama --version
```

Должно показать версию, например: `ollama version 0.5.x`

### Шаг 3: Скачать модель

```powershell
ollama pull llama3.1:8b
```

Это займёт ~5 минут (модель ~4.7GB)

### Шаг 4: Запуск

Ollama запускается автоматически при установке!

Проверь что работает:
```powershell
ollama list
```

Должно показать:
```
NAME              ID           SIZE
llama3.1:8b       46e0c10c0... 4.7 GB
```

### Шаг 5: Тест

```powershell
ollama run llama3.1:8b "Привет! Как дела?"
```

---

## 🍎 MACOS

```bash
# Установка
brew install ollama

# Или скачай с https://ollama.com/download

# Скачать модель
ollama pull llama3.1:8b

# Запуск (автоматически)
ollama serve
```

---

## 🐧 LINUX

```bash
# Установка
curl -fsSL https://ollama.com/install.sh | sh

# Скачать модель
ollama pull llama3.1:8b

# Запуск
ollama serve
```

---

## ✅ ПРОВЕРКА ЧТО OLLAMA РАБОТАЕТ

### 1. Проверь процесс
Ollama должен работать в фоне.

**Windows:** Открой Диспетчер задач → найди "ollama"

**Mac/Linux:** 
```bash
ps aux | grep ollama
```

### 2. Проверь порт
Ollama использует порт `11434`

Открой в браузере: http://localhost:11434

Должно показать: `Ollama is running`

### 3. Проверь API
```powershell
curl http://localhost:11434/api/tags
```

Должен вернуться JSON со списком моделей.

---

## 🚀 ИСПОЛЬЗОВАНИЕ В NOVA AI

1. **Убедись что Ollama запущен**
2. **Открой Nova AI** (index.html)
3. **⚙️ Настройки**
4. **AI Провайдер → Ollama**
5. **🧪 Тест подключения**
6. **✅ Готово!**

---

## 🐛 УСТРАНЕНИЕ ПРОБЛЕМ

### "ollama не является внутренней или внешней командой"

Ollama не в PATH. Попробуй:

**Windows:**
```powershell
# Полный путь
"C:\Program Files\Ollama\ollama.exe" --version

# Или добавь в PATH
$env:Path += ";C:\Program Files\Ollama"
```

### "Connection refused" / "Не удалось подключиться"

Ollama не запущен. Запусти:

```powershell
ollama serve
```

Или перезапусти компьютер (Ollama запускается автоматически).

### "модель не найдена"

Скачай модель:

```powershell
ollama pull llama3.1:8b
```

### "недостаточно памяти"

llama3.1:8b требует ~8GB RAM.

**Альтернативы (меньше RAM):**
```powershell
# 2GB RAM
ollama pull phi3:mini

# 4GB RAM
ollama pull mistral:7b

# 1GB RAM
ollama pull tinyllama:1.1b
```

---

## 🎯 АЛЬТЕРНАТИВЫ OLLAMA

Если Ollama не работает, используй облачные API:

### 1. Hugging Face (БЕСПЛАТНО)
- https://huggingface.co/settings/tokens
- Не требует установки
- Работает сразу

### 2. Google Gemini (БЕСПЛАТНЫЙ TIER)
- https://makersuite.google.com/app/apikey
- 60 запросов/минуту бесплатно
- Высокое качество

### 3. OpenAI (ПЛАТНО)
- https://platform.openai.com/api-keys
- Лучшее качество
- ~$0.50/1000 запросов

---

## 📊 СРАВНЕНИЕ

| Провайдер | Установка | RAM | Интернет | Цена |
|-----------|-----------|-----|----------|------|
| **Ollama** | ✅ Да | 8GB | ❌ Нет | Бесплатно |
| **Hugging Face** | ❌ Нет | 0 | ✅ Да | Бесплатно |
| **Gemini** | ❌ Нет | 0 | ✅ Да | Бесплатно* |
| **OpenAI** | ❌ Нет | 0 | ✅ Да | Платно |

*Gemini: 60 запросов/мин бесплатно

---

## 💡 СОВЕТЫ

1. **Для начала** используй Hugging Face (не требует установки)
2. **Для приватности** установи Ollama
3. **Для лучшего качества** используй OpenAI/Gemini
4. **Для слабого ПК** выбери маленькую модель (phi3:mini)

---

## 🔗 ПОЛЕЗНЫЕ ССЫЛКИ

- Официальный сайт: https://ollama.com
- Документация: https://github.com/ollama/ollama
- Модели: https://ollama.com/library
- Discord: https://discord.gg/ollama

---

**Удачи! 🦙**
