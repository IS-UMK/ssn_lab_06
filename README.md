# SSN. Lab. 6. Kwantyzacja wektorowa

Zapoznaj się z zawartością notatnika Jupyter umieszczonego w repozytorium  i wykonaj zawarte w nim ćwiczenia.

Notatnik: [06_vq.ipynb](https://github.com/IS-UMK/ssn_lab_06/blob/master/06_vq.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/IS-UMK/ssn_lab_06/blob/master/06_vq.ipynb) [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/IS-UMK/ssn_lab_06/master?filepath=06_vq.ipynb)

---
## Zadanie 6: Gaz neuronowy

Zaimplementuj algorytm gazu neuronowego służącego do kwantyzacji wektorowej.  

**Algorytm gazu neuronowego**  
Parametry początkowe:
* $N$ ilość epok
* $k$ ilość neuronów (prototypów)
* $\eta_0$ początkowa wartość kroku uczenia
* $\lambda_0$ początkowa wartość promienia sąsiedztwa
* $\eta_{min}$ końcowa wartość kroku uczenia
* $\lambda_{min}$ końcowa wartość promienia sąsiedztwa
* $T$ ilość iteracji (ustalona automatycznie $N \times$ rozmiar zboru uczącego)

1. Zainicjuj wagi $\mathbf{w}_i$ neuronów  
2. Ustaw $t=0$ 
3. Powtarzaj $N$ razy:
4. <ul>Dla każdego $\mathbf{x}$ ze zbioru treningowego wykonaj</ul>
5. <ul><ul>wyznacz aktualny współczynnik uczenia  $\eta(t)=\eta_0\left(\frac{\eta_{\min }}{\eta_0}\right)^{\frac{t}{T}}$
    </ul></ul>
6. <ul><ul>wyznacz aktualny promień sąsiedztwa $\lambda(t)=\lambda_0\left(\frac{\lambda_{\min }}{\lambda_0}\right)^{\frac{t}{T}}$
    </ul></ul>

7. <ul><ul>uporządkuj neurony względem odległości od $\mathbf{x}$ </ul></ul>
8. <ul><ul>zaktualizuj wagi <br> 
   $\Delta \mathbf{w}_i=\eta(t) \cdot h_i(t) \cdot \left(\mathbf{x}-\mathbf{w}_i\right)\quad \text{gdzie} \quad h_i(t)=e^{-\frac{m(i)}{\lambda(t)}}$ <br> 
   $m(i) = 0, 1, \ldots, k-1$ oznacza pozycję neuronu $\mathbf{w}_i$ w rankingu odległości od najbliższego do najdalszego.
    </ul></ul>
1. <ul><ul>zwiększ $t = t + 1$</ul></ul>

Wykorzystaj algorytm gazu neuronowego do kompresji obrazu [dane/Lenna.png](dane/Lenna.png).  
Spróbuj dobrać parametr tak aby uzyskać jak najmniejszy błąd rekonstrukcji przy jak najmniejszym rozmiarze księgo kodów (ilości prototypów). 

Rozwiązanie w postaci notatnika Jupyter (``.ipynb``) lub skryptu w języku Python (``.py``) w repozytorium GitHub.





