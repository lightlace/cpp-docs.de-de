---
title: "IEEE-Gleitkommadarstellung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "double-Datentyp, Gleitkommadarstellung"
  - "float-Schlüsselwort"
  - "Gleitkommazahlen, IEEE-Darstellung"
  - "IEEE-Gleitkommadarstellung"
  - "long double"
  - "real*10-Wert"
  - "real*4-Wert"
  - "real*8-Wert"
ms.assetid: 537833e8-fe05-49fc-8169-55fd0314b195
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# IEEE-Gleitkommadarstellung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+ hält die numerischen Standards gemäß IEEE ein.  Es gibt drei interne Varianten von reellen Zahlen.  **Real\*4** und **Real\*8** werden in Visual C\+\+ verwendet.  Real\*4 wird mit dem Wort **float** deklariert.  Real\*8 wird mit dem Wort **double** deklariert.  In der 32\-Bit\-Programmierung für Windows wird der Datentyp `long double` dem Datentyp **double** zugeordnet.  Es gibt jedoch Assemblersprachunterstützung für Berechnungen mit dem Datentyp **Real\*10**.  
  
 Die Werte werden wie folgt gespeichert:  
  
|Wert|Gespeichert als|  
|----------|---------------------|  
|Real\*4|Vorzeichenbit, 8\-Bit\-Exponent, 23\-Bit\-Mantisse|  
|Real\*8|Vorzeichenbit, 11\-Bit\-Exponent, 52\-Bit\-Mantisse|  
|Real\*10|Vorzeichenbit, 15\-Bit\-Exponent, 64\-Bit\-Mantisse|  
  
 Bei den Formaten **Real\*4** und **Real\*8** wird in der Mantisse eine führende 1 angenommen, die nicht gespeichert wird, sodass die Mantissen eigentlich 24 oder 53 Bits lang sind, obwohl nur 23 oder 52 Bits gespeichert werden.  Im Format **Real\*10** werden alle Bits gespeichert.  
  
 Die Exponenten werden mit der Hälfte ihres möglichen Werts gewichtet.  Das bedeutet, dass die Gewichtung vom gespeicherten Exponenten subtrahiert wird, um den tatsächlichen Wert des Exponenten zu erhalten.  Wenn der gespeicherte Exponent kleiner als die Gewichtung ist, handelt es sich um einen negativen Exponenten.  
  
 Die Exponenten werden wie folgt gewichtet:  
  
|Exponent|Gewichtet mit|  
|--------------|-------------------|  
|8\-Bit \(Real\*4\)|127|  
|11\-Bit \(Real\*8\)|1023|  
|15\-Bit \(Real\*10\)|16383|  
  
 Diese Exponenten sind keine Zehnerpotenzen, sondern Zweierpotenzen.  Das bedeutet, dass der Wert eines gespeicherten 8\-Bit\-Exponenten maximal 127 betragen kann.  2\*\*127 entspricht ungefähr 10\*\*38, was die tatsächliche Obergrenze von Real\*4 darstellt.  
  
 Die Mantisse wird als Binärbruch im Format 1.XXX... gespeichert. .  Dieser Bruch hat einen Wert größer oder gleich 1 und kleiner als 2.  Reelle Zahlen werden immer im normierten Format gespeichert. Die Mantisse wird also immer nach links verschoben, sodass das höchstwertige Bit der Mantisse immer den Wert 1 hat.  Da dieses Bit immer 1 ist, wird dieser Wert in den Formaten Real\*4 und Real\*8 angenommen \(aber nicht gespeichert\).  Das Binärkomma \(nicht Dezimalkomma\) wird rechts von der führenden 1 angenommen.  
  
 Somit sieht das Format für die verschiedenen Längen folgendermaßen aus:  
  
|Format|BYTE 1|BYTE 2|BYTE 3|BYTE 4|...|BYTE n|  
|------------|------------|------------|------------|------------|---------|------------|  
|Real\*4|`SXXX XXXX`|`XMMM MMMM`|`MMMM MMMM`|`MMMM MMMM`|||  
|Real\*8|`SXXX XXXX`|`XXXX MMMM`|`MMMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
|Real\*10|`SXXX XXXX`|`XXXX XXXX`|`1MMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
  
 `S` stellt das Vorzeichenbit dar, `X` die Exponentenbits und `M` die Mantissenbits.  Beachten Sie, dass das höchstwertige Bit bei den Formaten **Real\*4** und **Real\*8** nur angenommen wird, beim Format **Real\*10** jedoch als 1 in BYTE 3 vorhanden ist.  
  
 Um das Binärkomma korrekt zu verschieben, müssen Sie zunächst die Gewichtung des Exponenten entfernen und dann das Binärkomma um die entsprechende Anzahl von Bits nach rechts oder nach links verschieben.  
  
## Beispiele  
 Es folgen einige Beispiele im Format **Real\*4**:  
  
-   Im folgenden Beispiel ist das Vorzeichenbit 0 \(null\), und der gespeicherte Exponent hat den Wert 128 bzw. binär 100 0000 0, was 127 plus 1 entspricht.  Die gespeicherte Mantisse ist \(1.\) 000 0000 ... 0000 0000 mit der implizierten führenden 1 und dem Binärkomma ergibt den tatsächlichen Mantissenwert 1.  
  
    ```  
                        SXXX XXXX XMMM MMMM ... MMMM MMMM  
    2   =  1  * 2**1  = 0100 0000 0000 0000 ... 0000 0000 = 4000 0000  
    ```  
  
-   Dasselbe wie bei \+2, außer dass das Vorzeichenbit gesetzt ist.  Das gilt für alle Gleitkommazahlen im IEEE\-Format.  
  
    ```  
    -2  = -1  * 2**1  = 1100 0000 0000 0000 ... 0000 0000 = C000 0000  
    ```  
  
-   Dieselbe Mantisse, der Exponent erhöht sich um 1 \(gewichteter Wert ist 129 bzw. binär 100 0000 1\).  
  
    ```  
    4  =  1  * 2**2  = 0100 0000 1000 0000 ... 0000 0000 = 4080 0000  
    ```  
  
-   Derselbe Exponent, die Mantisse ist jedoch um die Hälfte ihres Werts \(1\) größer. 100 0000 ...0000 0000 bedeutet 1 1\/2, da es sich um einen Binärbruch handelt \(die Werte der Bruchzahlen sind 1\/2, 1\/4, 1\/8 usw.\).  
  
    ```  
    6  = 1.5 * 2**2  = 0100 0000 1100 0000 ... 0000 0000 = 40C0 0000  
    ```  
  
-   Derselbe Exponent wie bei den anderen Zweierpotenzen, die Mantisse ist jedoch um Eins kleiner als Zwei bei 127 bzw. binär 011 1111 1.  
  
    ```  
    1  = 1   * 2**0  = 0011 1111 1000 0000 ... 0000 0000 = 3F80 0000  
    ```  
  
-   Der gewichtete Exponent ist 126, binär 011 1111 0, und die Mantisse ist \(1\). 100 0000 ... 0000 0000, d. h. 1 1\/2.  
  
    ```  
    .75 = 1.5 * 2**-1 = 0011 1111 0100 0000 ... 0000 0000 = 3F40 0000  
    ```  
  
-   Genau dasselbe wie Zwei, außer dass in der Mantisse das Bit für 1\/4 gesetzt ist.  
  
    ```  
    2.5 = 1.25 * 2**1 = 0100 0000 0010 0000 ... 0000 0000 = 4020 0000  
    ```  
  
-   1\/10 ist binär ein Endlosbruch.  Die Mantisse ist knapp 1,6, und der gewichtete Exponent besagt, dass 1,6 durch 16 zu teilen ist \(d. h. binär 011 1101 1 und dezimal 123\).  Der echte Exponent ist 123 – 127 \= –4, der Multiplikationsfaktor ist also 2\*\*–4 \= 1\/16.  Beachten Sie, dass die gespeicherte Mantisse im letzten Bit gerundet ist. Dadurch wird versucht, eine praktisch nicht darstellbare Zahl so genau wie möglich darzustellen. \(Der Grund dafür, dass 1\/10 und 1\/100 binär nicht genau darstellbar sind, ist vergleichbar mit dem Grund dafür, dass 1\/3 dezimal nicht genau darstellbar ist.\)  
  
    ```  
    0.1 = 1.6 * 2**-4 = 0011 1101 1100 1100 ... 1100 1101 = 3DCC CCCD  
    ```  
  
-   `0  = 1.0 * 2**-128 = all zeros--a special case.`  
  
## Siehe auch  
 [Warum Gleitkommazahlen an Genauigkeit verlieren können](../../build/reference/why-floating-point-numbers-may-lose-precision.md)