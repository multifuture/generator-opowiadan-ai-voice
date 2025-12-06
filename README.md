# 🧚 Generator Bajek AI dla Dzieci - LEAN Edition

> Spersonalizowana bajka z audio w 2 minuty! Prosta, szybka, magiczna. ✨

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-red.svg)](https://streamlit.io/)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-green.svg)](https://openai.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## ✨ Funkcje

### **Generowanie bajek:**
- 🎯 **Szybka personalizacja** - tylko imię, wiek, wartość edukacyjna
- 🎧 **Audio narration** - profesjonalny głos Nova (OpenAI TTS)
- ⚡ **Błyskawiczne** - bajka gotowa w ~20 sekund
- 💰 **Tanie** - ~$0.016 za kompletną bajkę z audio
- 📱 **Mobile-friendly** - prosty, jednoekranowy formularz
- 🛡️ **Bezpieczne** - wzmocnione filtry treści dla dzieci

### **Personalizacja:**
- 👶 **Wiek dziecka:** 3-5 lat, 6-8 lat, 9-12 lat (automatycznie dostosowany język)
- 💡 **10 wartości edukacyjnych:** Odwaga, Przyjaźń, Uczciwość, Dobroć, Wytrwałość...
- ✏️ **Pomysł na bajkę:** Opcjonalny (lub losowa magiczna przygoda)
- 🎵 **Ton:** Uniwersalny (ciepły, magiczny, z nutką humoru)

### **Output:**
- 📖 **Tekst bajki** - 250-500 słów (zależnie od wieku)
- 🎧 **Plik MP3** - audio narration do pobrania
- 📊 **Statystyki** - liczba słów, zdań, czas czytania
- 💾 **Download** - TXT + MP3

---

## 🚀 Demo na żywo

🔗 **[Zobacz demo](https://generator-bajek-ai.streamlit.app)** *(link po wdrożeniu)*

**Dostęp:** Bez logowania (wersja testowa)

---

## 📸 Screenshots

*(Dodaj screenshot tutaj - landing page i formularz)*

---

## 💡 Dlaczego LEAN?

### Problem z klasycznymi generatorami:
- ❌ Zbyt skomplikowane (5+ kroków)
- ❌ Drogie (GPT-4o + DALL-E 3)
- ❌ Wolne (60+ sekund)
- ❌ Decision fatigue (za dużo opcji)

### Rozwiązanie LEAN:
- ✅ **2 kroki:** Formularz → Generuj
- ✅ **Tanie:** GPT-4o-mini + TTS = $0.016/bajka
- ✅ **Szybkie:** ~20 sekund total
- ✅ **Proste:** Tylko kluczowe opcje
- ✅ **Audio:** Czytanie przed snem!

### Rezultat:
- 💰 **77% oszczędności** kosztów vs wersja Full
- ⚡ **67% szybsze** generowanie
- 🎯 **60% mniej kroków** w UI
- ✨ **100% jakości** bajek

---

## 🛠 Tech Stack

**AI Models:**
- OpenAI GPT-4o-mini (generowanie tekstu)
- OpenAI TTS (głos Nova, audio narration)

**Framework:**
- Streamlit 1.28+
- Python 3.11+

**Monitoring (opcjonalnie):**
- Langfuse (koszty, tokeny, analytics)

**Deployment:**
- Streamlit Cloud (darmowy)
- DigitalOcean App Platform ($5/m)

---

## 💻 Instalacja lokalna

### **1. Wymagania**

**System:**
- Python 3.11+ *(testowane na 3.11)*
- pip 23+
- Git

**Konta API:**
- [OpenAI API key](https://platform.openai.com/api-keys) - GPT-4o-mini + TTS
- [Langfuse account](https://cloud.langfuse.com) - opcjonalnie (monitoring)

**Koszty API:** *(przy 100 bajek/miesiąc)*
- GPT-4o-mini: ~$0.10/100 bajek
- OpenAI TTS: ~$1.50/100 bajek
- **TOTAL: ~$1.60/100 bajek** vs $7/100 w wersji Full

---

### **2. Sklonuj repozytorium**

```bash
git clone https://github.com/twoj-user/generator-bajek-ai-demo.git
cd generator-bajek-ai-demo
```

---

### **3. Zainstaluj zależności**

**Stwórz środowisko wirtualne:**

```bash
# Conda (zalecane)
conda create -n bajki_ai python=3.11
conda activate bajki_ai

# lub venv
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate   # Windows
```

**Zainstaluj pakiety:**

```bash
pip install -r requirements.txt
```

---

### **4. Konfiguracja API**

**Stwórz `.streamlit/secrets.toml`:**

```bash
mkdir .streamlit
touch .streamlit/secrets.toml  # Linux/Mac
# lub ręcznie w Windows
```

**Dodaj klucze:**

```toml
# OpenAI API (WYMAGANE)
OPENAI_API_KEY = "sk-proj-twoj_klucz_tutaj"

# Langfuse (OPCJONALNE - dla monitoringu)
LANGFUSE_PUBLIC_KEY = "pk-lf-twoj_klucz"
LANGFUSE_SECRET_KEY = "sk-lf-twoj_klucz"
LANGFUSE_HOST = "https://cloud.langfuse.com"
```

**⚠️ WAŻNE:** 
- Nie commituj `secrets.toml` do repo!
- Jest w `.gitignore`

---

### **5. Uruchom**

```bash
streamlit run app_demo_voice.py
```

Aplikacja otworzy się: `http://localhost:8501`

---

## 📦 Struktura projektu

```
generator-bajek-ai-demo/
├── app_demo_voice.py       # Główna aplikacja
├── requirements.txt        # Dependencies
├── README.md               # Ten plik
├── CHANGELOG.md            # Historia zmian
├── .gitignore              # Git ignore rules
└── .streamlit/
    └── secrets.toml        # API keys (NIE commitować!)
```

---

## 🎨 Customizacja

### **Zmiana głosu TTS:**

W pliku `app_demo_voice.py`, linia ~738:

```python
response = openai_client.audio.speech.create(
    model="tts-1",
    voice="nova",  # Zmień na: alloy, echo, fable, onyx, shimmer
    input=story_content
)
```

Dostępne głosy:
- `nova` - Kobiecy, ciepły (domyślny)
- `shimmer` - Kobiecy, energiczny
- `alloy` - Neutralny
- `echo` - Męski, spokojny

---

### **Zmiana długości bajek:**

Linia ~491:

```python
target_words = {
    "3-5 lat": "250-300",   # Zmień liczby
    "6-8 lat": "350-400", 
    "9-12 lat": "400-500"
}
```

---

### **Dodanie nowych wartości:**

Linia ~773:

```python
lesson_options = [
    "Odwaga",
    "Przyjaźń",
    "Twoja nowa wartość",  # Dodaj tutaj
    # ...
]
```

---

## 📊 Monitoring (Langfuse)

Jeśli skonfigurowałeś Langfuse, zobacz dashboard:

**[Langfuse Cloud](https://cloud.langfuse.com)**

**Co zobaczysz:**
- 💰 Koszty per bajka
- 🔢 Tokeny (input/output)
- ⏱️ Latency (czas odpowiedzi)
- 📝 Pełne prompty
- 📈 Trendy użycia

---

## 🔒 Bezpieczeństwo

**Zabezpieczenia treści:**
- 15+ zakazanych tematów
- Zero przemocy, śmierci, strachu
- Tylko pozytywne emocje
- Enhanced safety prompt
- Critical safety instruction

**Dla produkcji dodaj:**
- 🔐 Logowanie użytkowników
- 💳 System płatności
- 📊 Rate limiting per user
- 🛡️ Content moderation API

---

## 💡 Rozwój

**Możliwe rozszerzenia:**
- 🌍 Multi-language (EN, DE, FR)
- 🎨 Proste ilustracje (Stable Diffusion)
- 🎙️ Wybór głosu przez użytkownika
- 📖 Eksport do PDF
- 👥 Konta użytkowników
- 💾 Historia bajek w bazie danych
- ⭐ System ocen
- 📧 Email delivery

---

## 📊 Porównanie z wersją Full

| Cecha | Full (v1.0) | LEAN (v2.0) |
|-------|-------------|-------------|
| Model tekstu | GPT-4o | GPT-4o-mini |
| Obrazy | DALL-E 3 | ❌ |
| Audio | ❌ | OpenAI TTS |
| Kroki UI | 5 | 2 |
| Koszt/bajka | $0.07 | $0.016 |
| Czas | 60s | 20s |
| Use case | Kompletny | Szybki MVP |

---

## 🐛 Troubleshooting

**Błąd: "No module named 'openai'"**
```bash
pip install openai --upgrade
```

**Błąd: UTF-8 encoding (Windows)**
- Jest naprawione w kodzie (linie 13-19)
- Restart aplikacji powinien pomóc

**Langfuse nie działa**
- Sprawdź klucze w secrets.toml
- Aplikacja działa bez Langfuse (opcjonalnie)

**Audio się nie generuje**
- Sprawdź klucz OpenAI
- Sprawdź limity API (quota)

---

## 📝 Licencja

MIT License - swobodne użycie i modyfikacje.

---

## 👨‍💻 Autor

**Multi-Future**  
🌐 [multi-future.pl](https://multi-future.pl)  
💼 Data Science | AI Automation | Business Training
