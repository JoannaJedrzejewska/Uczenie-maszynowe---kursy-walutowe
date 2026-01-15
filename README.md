# Dokumentacja Techniczna
Projekt dostarcza gotowy pipeline służący do prognozowania kierunku zmian na rynku Forex oraz zmienności (indeks NEER). System unikalnie łączy dane rynkowe z danymi alternatywnymi w postaci mikroekspresji twarzy decydentów EBC, ekstrahowanych za pomocą Computer Vision.

## Struktura Plików
Projekt składa się z dwóch głównych notatników Jupyter:

1.  **`ML_kursy_walutowe_finalny_projekt.ipynb`**: Zawiera pełny kod uczenia maszynowego. Obejmuje testy modeli, walidację krzyżową, zaawansowaną inżynierię cech (lagi behawioralne), analizę pewności (Confidence Analysis) oraz logikę generowania prognoz.
2.  **`Bazy_danych_oraz_źródła.ipynb`**: Dokumentacja techniczna źródeł danych. Zawiera spis bibliotek, opis źródeł ekonomicznych (ECB) oraz behawioralnych. Przedstawiono tu również proces czyszczenia i łączenia danych oraz algorytm generowania próbki badawczej.

## Instrukcja Uruchomienia
W repozytorium udostępniono zbiory danych w formacie `.csv`. Ze względu na ochronę danych i rozmiar bazy, domyślnie dołączona jest próbka danych.

> Aby poprawnie uruchomić kod w notatniku ML, należy w komórkach wczytujących dane zamienić nazwę pliku **`final_data.csv`** na **`final_fx_facial_sample.csv`**.

> Plik `final_fx_facial_sample.csv` jest reprezentatywną próbką przygotowaną na potrzeby publikacji. Z uwagi na mniejszą liczbę obserwacji, **wyniki uzyskane po uruchomieniu kodu na próbce mogą różnić się od wyników przedstawionych w raporcie i dokumentacji**.

## Pre-trained Models
System zawiera gotowe, wytrenowane modele wyłonione w drodze eliminacji, zarchiwizowane w folderze `saved_models_hybrid/`. 
Modele są zintegrowane z obiektami pomocniczymi (Scalery, PCA, Lasso), co pozwala na natychmiastowe generowanie prognoz.

## Wymagania
*   **Język**: Python 3.12+
*   **Analiza Danych**: biblioteki `pandas`, `numpy`, `scipy`.
*   **Machine Learning**: biblioteka `scikit-learn` (MLP, RandomForest, GradientBoost, SVC, Ridge, Lasso, PCA).
*   **Statystyka**: biblioteka `statsmodels` (Testy Przyczynowości Grangera).
*   **Wizualizacja**: biblioteki `matplotlib`, `seaborn`.
*   **Operacjonalizacja**: biblioteki `joblib`, `os`, `shutil`.
