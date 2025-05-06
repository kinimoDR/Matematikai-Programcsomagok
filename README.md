# Matematikai-Programcsomagok

## Projekt: Konvolúciós neurális hálózat 
## Készítette: Szeidemann Márton, Rákosy Dominik, Merencsics Martin Marcell

# Előnézet:
Projektünkben egy kezdő klasszifikációs modellt építettünk fel, főként a PyTorch és NumPy könyvtárak segítségével. Modellünket körülbelül 14 000 darab, 224×224‑es felbontású ételfotón (FOOD‑14 adathalmaz) tanítottuk, 14 különböző kategóriára.

A kód megírásához a Google Colab (Jupyter Notebook) felületét használtuk, mert a tanítófázis futtatásának felgyorsításához igénybe vettük a rendszeren keresztül ingyenesen elérhető GPU‑t, és a kollaboratív munka is egyszerűbb volt.

30 epochos tanítás után a végső modell 76 % pontosságot ért el (azaz egy számára ismeretlen tesztképen körülbelül 76 % eséllyel mondta meg helyesen, hogy mi látható rajta).

A README további részében megtalálod:

- a modell tanítási és kiértékelési fázisának legfontosabb statisztikáit,

- a teljes notebookhoz vezető linket,

- a program felépítésének rövid vázlatát,

- valamint az általunk használt segédanyagok listáját.

**Előfeltételek**

- Python 3.10 vagy újabb

- PyTorch 2.0 vagy újabb (CUDA 11.x, ha GPU‑t használsz)

- NumPy

- scikit‑learn (kiértékeléshez, például confusion matrix)

- matplotlib és seaborn (grafikonokhoz)

- tqdm (progress‑bar‑ok)

**Futtatás és használat**

- Colab‑ban: https://colab.research.google.com/github/<felhasznalo>/<repo>/blob/main/Matprogrind2.ipynb
    - Válaszd a Runtime > Change runtime type > GPU opciót, majd Run all.

- Lokálisan: <br>

  git clone https://github.com/<felhasznalo>/<repo>.git <br>
  cd <repo> <br>
pip install -r requirements.txt <br>
jupyter notebook Matprogrind2.ipynb <br>

**Inference gyorsan (parancssorból):**
    python predict.py path/to/image.jpg
    A predict.py a notebookból kivágott inferencia‑függvényre épül, és a képernyőre kiírja a top‑1 (és opcionálisan top‑3) találatot.
### Vázlatos felépítése:
- Képek feltöltése
- Adathalmazok létrehozása 
- A konvolúciós neurális háló (CNN) definiálása
- Előkészületek a tanításhoz/futtatókörnyezet és optimalizáló beállítása
- Tanítás
- Kiértékelés 
- Statisztika

**Modell és eredmények**
- Architektúra: 10 konvolúciós réteg, max‑pool, batch norm és ReLU blokkok, majd 2 fully‑connected réteg; a kimenet 14 neuronos softmax.
- Paraméterek: kb. 5,6 millió tanulható paraméter
- Optimalizáló: AdamW (tanulási ráta 1e‑4, weight_decay 1e‑2)
- Learning‑rate scheduler: exponenciális (gamma 0,95 epochonként)
- Early Stopping: patience 10, legjobb checkpoint models/cnn.pt
- Batch size: 64
- Bemeneti normalizálás: RGB képek, torchvision.transforms.Normalize([0.5, …])

**Metrikák**
- Pontosság (top‑1): 76 %
- Átlagos top‑3: 93 %
- Macro‑F1: 0,74

### A kód elérési linkje: 
https://colab.research.google.com/drive/1vRqt2sXcfFtVR7j0cl4WLBtNMiMATbqg#scrollTo=eIOFKIQNOl1r

Confusion matrix:
![Confusion matrix](Confusion_matrix.png)

Predikciók az első 13 tesztképre:
![Predikciók az első 13 tesztképre](13_kep.png)

Loss és accuracy változása:
![Loss és accuracy változása](Loss_es_accuracy.png)

### Segédanyagok listája:
- FOOD-14 adathalmaz
- A Pytorch dokumentációja: https://pytorch.org/docs/stable/index.html
- Rácz Dániel előadás-sorozata: https://github.com/DamasdiGabor/matprog2024-25/blob/main/MATPROG_Eloadas_6es7.pdf
- Iván által összeállított gyakorlati segédanyag: https://colab.research.google.com/drive/18JwxaWra64n_LHgA1oOuF2pxozM6n8jE
- ChatGPT
