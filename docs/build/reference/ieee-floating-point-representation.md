---
title: IEEE-Gleitkommadarstellung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- float keyword
- real*8 value
- floating-point numbers, IEEE representation
- double data type, floating-point representation
- IEEE floating point representation
- real*10 value
- long double
- real*4 value
ms.assetid: 537833e8-fe05-49fc-8169-55fd0314b195
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17fae0cbb16208d5c7e7346f354f3501e4803d96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ieee-floating-point-representation"></a>IEEE-Gleitkommadarstellung
Microsoft Visual C++ ist konsistent mit den numerischen IEEE-Standards. Es gibt drei interne Varianten von reelle Zahlen ein. Echte\*4 und real\*8 in Visual C++ verwendet werden. Echte\*4 wird mit dem Wort deklariert **"float"**. Echte\*8 wird mit dem Wort deklariert **doppelte**. In der Windows-32-Bit-Programmierung die `long double` Datentyp zugeordnet **doppelte**. Es gibt allerdings Assemblysprache-Unterstützung für Berechnungen mit echten * 10-Datentyp.  
  
 Die Werte werden wie folgt gespeichert:  
  
|Wert|Gespeichert als|  
|-----------|---------------|  
|Real * 4|Vorzeichenbit, 8-Bit-Exponenten, 23-Bit-Mantisse|  
|Real * 8|Vorzeichenbit, 11-Bit-Exponenten, 52-Bit-Mantisse|  
|Real * 10|Vorzeichenbit, 15-Bit-Exponenten, 64-Bit-Mantisse|  
  
 Real * 4 und real\*8 Formate, es wird eine führende 1 in der Mantisse, die nicht im Arbeitsspeicher gespeichert, sodass die Mantissen eigentlich 24 bzw. 53 Bits lang sind, obwohl nur 23 oder 52 Bits gespeichert werden. Die tatsächlichen\*10 Format Bits gespeichert.  
  
 Die Exponenten werden mit der Hälfte ihres möglichen Werts gewichtet. Dies bedeutet, dass Sie die Gewichtung vom gespeicherten Exponenten zum Abrufen der tatsächlichen Exponenten subtrahiert werden soll. Wenn der gespeicherte Exponent kleiner als die Gewichtung ist, ist es tatsächlich einen negativen Exponenten.  
  
 Die Exponenten werden wie folgt gewichtet:  
  
|Exponent|Durch tendiert|  
|--------------|---------------|  
|8-Bit (real * 4)|127|  
|11-Bit (real * 8)|1023|  
|15-Bit (real * 10)|16383|  
  
 Diese Exponenten sind keine Zehnerpotenzen; Es handelt sich um Potenzen von 2. Gespeicherte 8-Bit-Exponenten können also bis zu 127 betragen. Der Wert 2 ** 127 entspricht ungefähr 10\*\*38, was die tatsächliche Grenze von Real\*4.  
  
 Die Mantisse wird als Binärbruch des Formulars gespeichert... 1.xxx.... Dieser Bruch hat einen Wert größer als oder gleich 1 und kleiner als 2. Beachten Sie die reellen Zahlen, die immer in normalisierter Form gespeichert werden. d. h. die Mantisse wird nach links verschoben, dass das höchstwertige Bit der Mantisse immer 1 ist. Da dieses Bit immer 1 ist, wird davon ausgegangen (nicht gespeichert) in die Real * 4 und real\*8 Formate. Der binäre (nicht) Dezimaltrennzeichen wird davon ausgegangen, dass rechts von der führenden 1 werden.  
  
 Das Format hat, für die verschiedenen Größen wie folgt:  
  
|Format|1-BYTE|2-BYTE|BYTE 3|4-BYTE|...|BYTE-n|  
|------------|------------|------------|------------|------------|---------|------------|  
|Real * 4|`SXXX XXXX`|`XMMM MMMM`|`MMMM MMMM`|`MMMM MMMM`|||  
|Real * 8|`SXXX XXXX`|`XXXX MMMM`|`MMMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
|Real * 10|`SXXX XXXX`|`XXXX XXXX`|`1MMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
  
 `S`Stellt das Vorzeichenbit der `X`des sind die Exponent Bits und die `M`des Mantissen-Bits sind. Beachten Sie, dass das höchstwertige Bit in Echtzeit voraussetzt, dass * 4 und real\*8 formatiert, aber als "1" in BYTE 3 des wahren vorhanden ist\*10 Format.  
  
 Um den binären Punkt ordnungsgemäß zu verschieben, Sie zuerst Binärkomma den Exponenten und anschließend die binäre Punkt nach rechts verschieben oder links die entsprechende Anzahl von Bits.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden sind einige Beispiele in Echtzeit * 4-Format:  
  
-   Im folgenden Beispiel wird das signierte Bit 0 (null), und der gespeicherte Exponent ist, 128 bzw. 100 0000 0 binär 127 plus 1 entspricht. Die gespeicherte Mantisse ist (1). 000 0000 ... 0000 0000, die einen impliziten führenden 1 und binäre Punkt ist, daher ist die tatsächliche Mantisse eins hat.  
  
    ```  
                        SXXX XXXX XMMM MMMM ... MMMM MMMM  
    2   =  1  * 2**1  = 0100 0000 0000 0000 ... 0000 0000 = 4000 0000  
    ```  
  
-   Entspricht + 2 mit dem Unterschied, dass das signierte Bit festgelegt ist. Dies gilt für alle IEEE Format Gleitkommazahlen.  
  
    ```  
    -2  = -1  * 2**1  = 1100 0000 0000 0000 ... 0000 0000 = C000 0000  
    ```  
  
-   Dieselbe Mantisse Exponent erhöht wird, um eins (gewichteter Wert ist 129 bzw. binär 100 0000 1.  
  
    ```  
    4  =  1  * 2**2  = 0100 0000 1000 0000 ... 0000 0000 = 4080 0000  
    ```  
  
-   Derselbe Exponent Mantisse ist größer, um die Hälfte: (1). 100 0000... 0000 0000, da dies Binärbruch, ist die 1 1/2 (die Dezimalstellen sind die Werte sind 1/2, 1/4, 1/8 usw.) ist.  
  
    ```  
    6  = 1.5 * 2**2  = 0100 0000 1100 0000 ... 0000 0000 = 40C0 0000  
    ```  
  
-   Derselbe Exponent als andere Potenzen von zwei, Mantisse ist jeweils weniger als zwei 127 oder binär 011 1111 1.  
  
    ```  
    1  = 1   * 2**0  = 0011 1111 1000 0000 ... 0000 0000 = 3F80 0000  
    ```  
  
-   Der gewichtete Exponent ist 126 011 1111 0 binär, und die Mantisse ist (1). 100 0000 ... 0000 0000, 1 1/2.  
  
    ```  
    .75 = 1.5 * 2**-1 = 0011 1111 0100 0000 ... 0000 0000 = 3F40 0000  
    ```  
  
-   Genauso wie zwei, außer wird das Bit, das 1/4 stellt in der Mantisse festgelegt.  
  
    ```  
    2.5 = 1.25 * 2**1 = 0100 0000 0010 0000 ... 0000 0000 = 4020 0000  
    ```  
  
-   1/10 ist einem sich wiederholenden Bruchteil Binär. Die Mantisse wird knapp 1,6, und der gewichtete Exponent besagt, dass 1,6 durch 16 geteilt wird (es ist binär, also 123 Dezimal 011 1101 1). Der "true" Exponent ist 123-127 = 4, was bedeutet, dass der Faktor, multiplizieren "2 **-4 = 1/16". Beachten Sie, die die gespeicherte Mantisse im letzten Bit aufgerundet wird – Versuch, die nicht darstellbare Zahl so genau wie möglich darzustellen. (Der Grund, 1/10 und 1 bzw. 100 werden im Binärformat nicht exakt darstellbar ist vergleichbar mit dem Grund dafür, dass 1/3 Dezimal nicht exakt darstellbar ist.)  
  
    ```  
    0.1 = 1.6 * 2**-4 = 0011 1101 1100 1100 ... 1100 1101 = 3DCC CCCD  
    ```  
  
-   `0  = 1.0 * 2**-128 = all zeros--a special case.`  
  
## <a name="see-also"></a>Siehe auch  
 [Warum Gleitkommazahlen an Genauigkeit verlieren können](../../build/reference/why-floating-point-numbers-may-lose-precision.md)