# Uvodne vezbe

- Šta izučavamo?
  ```
    I) Kriptografija
    II) Zero Knowlage Proofs (Dokazi sa 0 znanja)
    III) Blockchain (Lanci Blokova) 
  ```
- **Kriptografija** - da osigura komunikaciju izmedju Alise i Boba (sifrovanje poruka)
```
Alisa        Bob        Eva       prisluskivanje + izmena podataka
  A     ->    B          E          T
```

- imamo **KLJUC**
  - Jedan kljuc za isfrovanje i desifrovanje

- **Simetricna (K)** - sa istim kljucem se vrsi i sifrovanje i desifrovanje
  - moramo da imamo isti kljuc
 
     
- **Asimetricna (PK - SK)** - koristimo jedan kljuc za sifrovanje, i poseban kljuc za desifrovanje
  - jako sporo
  - koristimo je u startu, kako bismo ustanovili identitet
    - potvrda identiteta
    - razmena kljuceva      

```
    A                   B
    Pka                 Pkb          (javni kljuc; svi znaju za njega)
    Ska                 Skb          (tajni kljuc i niko ne zna za njega sem Alise za svoj i Boba za svoj)
```

```
    A                    B            
    |                   /\
    V                    |

   {M}_Pkb      ->    {M}_Pkb Skb  
   {A^P}_Ska    ->    {A^P}_Ska Pka
```

- Alisa mora da potpise poruku kako bi Bob garantovao da je poruka stigla od Alise
- Potpis Alisa sifruje svojim tajnim kljucem
- Garantuje se da nema izmena

- Ako je poruka zakljucana Alisinim tajnim kljucem tada je i Alisa potpisala svojim kljucem
- Hocu da smanjim poruku

```
    M                      M 
    |
    V

   {Hm}_Ska               {Hm}_Ska Pka
                          Hm (MD5; SHA 256)   (i uporedjujemo da li je prethocna i ova identicne)

Hm - kriptografska hes funkcija (MD5; SHA256)
```

- Sifrovanje javnim i privatnim kljucem

- Izracunavanje hesa je veoma brzo

- **Sertifikacija** - garancija da je neciji javni kljuc bas njegov javni kljuc

- SYMANTEC

- Kako razmeniti kljuc za simetricnu kriptografiju ?
  - DH protokol
 
```

    A  23, 5           B  23,5
    Ž (p,q)            Ž (p,q)
    C  4=k             P  3
    N  4               Z  10
            \
            /     
    Z 10               N  4
    X 18               X  18 


zakljucavanje:
  q^k mod p
za sifrovanje

Alisa =>  (q^b)^a   mod p
Bob   =>  (q^a)^b   mod p 

```


<hr>

## Zero Knowlage Proofs 

- da ne otkrijem ni delic informacije o sebi kako bih mogao da udjem u zemlju
