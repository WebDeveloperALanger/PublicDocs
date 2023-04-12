# Netzadresse und Broadcast ermitteln

## Kurzfassung

### Berechnung Netzadresse (mit logisch AND, OR)

    Netzadresse = SubNetMask AND IP 
    Broadcast = invertierte SubNetMask OR IP 

## a) ---
## b) 89.56.155.66 /19

Um die Netzadresse und den Broadcast einer IP-Adresse zu berechnen, 
müssen wir die IP-Adresse und die Subnetzmaske verwenden. 
In diesem Fall haben wir die IP-Adresse 89.56.155.66 und das Subnetz /19.

### Schritt 1: Subnetzmaske berechnen

/19 bedeutet, dass die ersten 19 Bits der Subnetzmaske gesetzt sind. 
Daher ist die Subnetzmaske:

    1111 1111 . 1111 1111 . 1110 0000 . 0000 0000

    Dezimal:
        255   .     255   .     224   .     0    

### Schritt 2: 

IP-Adresse und Subnetzmaske in binär umwandeln.
Als nächstes wandeln wir sowohl die IP-Adresse als auch die Subnetzmaske 
in ihre binäre Schreibweise um:

    IP
    0101 1001   .   0011 1000   .   1001 1011   .   0100 0010

    Subnetzmaske
    1111 1111   .   1111 1111   .   1110 0000   .   0000 0000

### Schritt 3: Netzadresse berechnen

Um die Netzadresse zu berechnen, führen wir eine logische UND-Operation 
zwischen der IP-Adresse und der Subnetzmaske durch:

    0101 1001   .   0011 1000   .   1001 1011   .   0100 0010  (ip)
    1111 1111   .   1111 1111   .   1110 0000   .   0000 0000  (subnet)
    0101 1001   .   0011 1000   .   1000 0000   .   0000 0000  = Netzadresse

### Schritt 4: Netzadresse in dezimal umwandeln
    89          .   48          .   128         .   66      = Netzadresse


### Schritt 5: Broadcast-Adresse berechnen
    
    Um die Broadcast-Adresse zu berechnen, 
    invertieren wir die Subnetzmaske und führen eine logische ODER-Operation 
    zwischen der IP-Adresse und der invertierten Subnetzmaske durch:

    invertierte Subnetzmaske 
    0000 0000   .   0000 0000   .   0001 1111   .   1111 1111
    IP
    0101 1001   .   0011 1000   .   1001 1011   .   0100 0010
    0101 1001   .   0011 1000   .   1001 1111   .   1111 1111 = Broadcast

### Schritt 6: Broadcast-Adresse in dezimal umwandeln
    0101 1001   .   0011 1000   .   1001 1111   .   1111 1111
    89          .   56          .   159         .   255       = Broadcast

### Zusammenfassung
    Netzadresse: 
    89 . 48 . 128 . 66
    Broadcast
    89 . 56 . 159 . 255






## c) 188.240.201.217 /29
Um die Netzadresse und den Broadcast einer IP-Adresse zu berechnen,
müssen wir die IP-Adresse und die Subnetzmaske verwenden.
IP /subnet maske

### Schritt 1: Subnetzmaske berechnen

/29 bedeutet, dass die ersten 29 Bits der Subnetzmaske gesetzt sind.
Daher ist die Subnetzmaske:

    Binär
    1111 1111   .   1111 1111   .   1111 1111   .   1111 1000 

    Dezimal
    255         .   255         .   255         .   248

### Schritt 2:

IP-Adresse und Subnetzmaske in binär umwandeln.
Als nächstes wandeln wir sowohl die IP-Adresse als auch die Subnetzmaske
in ihre binäre Schreibweise um:

    IP
    1011 1100   .   1111 0000   .   1100 1001   .   1101 1001
    Subnetzmaske
    1111 1111   .   1111 1111   .   1111 1111   .   1111 1000 


### Schritt 3: Netzadresse berechnen

Um die Netzadresse zu berechnen, führen wir eine logische UND-Operation
zwischen der IP-Adresse und der Subnetzmaske durch:

    1011 1100   .   1111 0000   .   1100 1001   .   1101 1001
    1111 1111   .   1111 1111   .   1111 1111   .   1111 1000
    1011 1100   .   1111 0000   .   1100 1001   .   1101 1000 = Netzadresse

### Schritt 4: Netzadresse in dezimal umwandeln
    
    1011 1100   .   1111 0000   .   1100 1001   .   1101 1000 = Netzadresse
    188         .   240         .   201         .   216

### Schritt 5: Broadcast-Adresse berechnen

Um die Broadcast-Adresse zu berechnen, 
invertieren wir die Subnetzmaske und führen eine logische ODER-Operation 
zwischen der IP-Adresse und der invertierten Subnetzmaske durch:

    invertierte Subnetzmaske
    0000 0000   .   0000 0000   .   0000 0000   .   0000 0111 
    1011 1100   .   1111 0000   .   1100 1001   .   1101 1001 (ip)
    1011 1100   .   1111 0000   .   1100 1001   .   1101 1111 = Broadcast

### Schritt 6: Broadcast-Adresse in dezimal umwandeln
    1011 1100   .   1111 0000   .   1100 1001   .   1101 1111 = Broadcast
    188         .   240         .   201         .   223

### Zusammenfassung
    Netzadresse: 
    188         .   240         .   201         .   216
    188         .   240         .   201         .   223
