# Aplikacja webowa Flask z CI/CD

## **Opis projektu**

Ten projekt przedstawia prostą aplikację webową napisaną w Flask, skonteryzowaną za pomocą Dockera, oraz zautomatyzowaną z użyciem pipeline CI/CD w GitHub Actions. Aplikacja jest przykładem realizacji zasad DevOps, takich jak kontrola wersji, automatyzacja procesów i konteneryzacja.

### **Funkcjonalności**

- **Endpointy**:
  - `/` – Wyświetla "Hello World".
  - `/hello/<name>` – Wyświetla powitanie "Hello `<name>`".
- **Pipeline CI/CD**:
  - Automatyczne budowanie i testowanie przy każdym Pull Request.
  - Budowanie obrazu Dockera i wypychanie go do GitHub Container Registry (GHCR) po mergu do gałęzi `main`.

---

## **Struktura projektu**

```
.
├── main.py            # Kod aplikacji Flask
├── Dockerfile         # Plik konfiguracyjny Dockera
├── .github/workflows
│   └── pipelines.yml  # Konfiguracja pipeline CI/CD
├── README.md          # Dokumentacja projektu
```

## **Instrukcja uruchomienia**

### **1. Uruchamianie lokalne przez repo**

1. Sklonuj repozytorium:

   ```bash
   git clone https://github.com/miceyjuice/cykl-test.git
   cd cykl-test
   ```

2. Zainstaluj wymagane zależności:

   ```bash
   pip install flask
   ```

3. Uruchom aplikację:

   ```bash
   python main.py
   ```

4. Otwórz przeglądarkę i przejdź na adres:
   - http://localhost:5000/ dla Hello World
   - http://localhost:5000/hello/{name} dla spersonalizowanego powitania.

### **2. Uruchamianie za pomocą Dockera**

1. Pobierz obraz Dockera

   ```bash
   docker pull ghcr.io/miceyjuice/cykl-test:latest
   ```

2. Zainstaluj wymagane zależności:

   ```bash
   pip install flask
   ```

3. Uruchom obraz:

   ```bash
   docker run -p 5000:5000 ghcr.io/miceyjuice/cykl-test:latest
   ```

4. Otwórz przeglądarkę i przejdź na adres:
   - http://localhost:5000/ dla Hello World
   - http://localhost:5000/hello/{name} dla spersonalizowanego powitania.
