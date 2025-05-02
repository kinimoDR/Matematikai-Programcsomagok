# Matematikai-Programcsomagok

## Projekt: Konvolúciós neurális hálózat 
## Készítette: Szeidemann Márton, Rákosy Dominik, Merencsics Martin Marcell

# Előnézet:
Projektünkben egy kezdő klasszifikációs modellt építettünk fel, főként a pytorch és numpy könyvtárak segítségével.
Modellünket körülbelül 2000 ételeket tartalmazó 224x224-es képen, 14 kategóriában tanítottuk.
A kód megírásához a Google Colab (Jupyter Notebook) felületet használtuk, mivel a tanítófázis futtatásának felgyorsításához igénybe kellett vennünk a rendszeren keresztül ingyenesen elérhető GPU támogatást, valamint megkönyítette a csoportos munkát.  
Egy 30 epochos futtatás után a végső modellünknek 76%-os pontosságot sikerült elérnie (ami azt jelenti, hogy a tanítás után egy számára ismeretlen tesztképről 76% eséllyel állapította meg helyesen, hogy mi van rajta).
A readme további részében ezen modell tanítási- és kiértékelési fázisáról készült statisztikai adatok találhatók; egy link, amely tartalmazza a teljes kódot; egy vázlatos leírás a program felépítéséről; valamint a projekt elkészítéséhez használt segédanyagok.

![Confusion matrix](Confusion_matrix.png)

![Predikciók az első 13 tesztképre](14_kép.png)

![Loss és accuracy változása]()

A kód elérési linkje: https://colab.research.google.com/drive/1vRqt2sXcfFtVR7j0cl4WLBtNMiMATbqg#scrollTo=eIOFKIQNOl1r
Vázlatos felépítése:
- Képek feltöltése
- Adathalmazok létrehozása 
- A konvolúciós neurális háló (CNN) definiálása
- Előkészületek a tanításhoz/futtatókörnyezet és optimalizáló beállítása
- Tanítás
- Kiértékelés 
- Statisztika
