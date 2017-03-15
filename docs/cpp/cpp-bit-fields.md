---
title: "C++-Bitfelder"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bitfelder"
  - "Bitfelder"
  - "Felder [C++], Bit"
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# C++-Bitfelder
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klassen und Strukturen können Member enthalten, die weniger Speicher als ein ganzzahliger Typ belegen.  Diese Member werden als Bitfelder angegeben.  Im Folgenden finden Sie die Syntax für die *member\-declarator*\-Bitfeldangabe:  
  
## Syntax  
  
```  
  
declarator  : constant-expression  
```  
  
## Hinweise  
 Der \(optionale\) `declarator` ist der Name, über den der Zugriff auf den Member im Programm erfolgt.  Es muss ein ganzzahliger Typ sein \(einschließlich Enumerationstypen\).  *constant\-expression* gibt die Anzahl von Bits an, die der Member in der Struktur einnimmt.  Anonyme Bitfelder, also Bitfeldmember ohne Bezeichner, können zur Auffüllung verwendet werden.  
  
> [!NOTE]
>  Ein unbenanntes Bitfeld der Breite 0 \(null\) erzwingt die Ausrichtung des nächsten Bitfelds an der nächsten `type`\-Grenze, wobei `type` den Typ des Members angibt.  
  
 Das folgende Beispiel deklariert eine Struktur, die zwei Bitfelder enthält:  
  
```  
// bit_fields1.cpp  
// compile with: /LD  
struct Date {  
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned short nMonth    : 5;    // 0..12  (5 bits)  
   unsigned short nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 Das konzeptionelle Speicherlayout eines Objekts vom Typ `Date` wird in der folgenden Abbildung dargestellt.  
  
 ![Speicherlayout eines Datumsobjekts](../cpp/media/vc38uq1.png "vc38UQ1")  
Speicherlayout von Datumsobjekten  
  
 Beachten Sie, dass `nYear` 8 Bit lang ist und einen Überlauf der Wortgrenze des deklarierten Typs, **kurz ohne Vorzeichen**, verursachen würde.  Daher wird am Anfang eines neuen Typs **kurz ohne Vorzeichen** begonnen.  Es ist nicht notwendig, dass alle Bitfelder in ein Objekt des zugrunde liegenden Typs passen. Neue Speichereinheiten werden entsprechend der Anzahl von Bits, die in der Deklaration angefordert werden, zugeordnet.  
  
 **Microsoft\-spezifisch**  
  
 Die Daten, die als Bitfelder deklariert werden, werden beginnend mit dem niedrigsten Bitwert bis hin zum höchsten Bitwert aufgeführt, wie in der Abbildung oben dargestellt.  
  
 **Ende Microsoft\-spezifisch**  
  
 Wenn die Deklaration einer Struktur ein unbenanntes Feld mit der Länge 0 \(null\) enthält, wie im folgenden Beispiel gezeigt,  
  
```  
// bit_fields2.cpp  
// compile with: /LD  
struct Date {  
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned           : 0;    // Force alignment to next boundary.  
   unsigned nMonth    : 5;    // 0..12  (5 bits)  
   unsigned nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 folgt das Speicherlayout der in der folgenden Abbildung dargestellten Struktur.  
  
 ![Layout des Datumsobjekts mit Bitfeld der Länge 0 &#40;null&#41;](../cpp/media/vc38uq2.png "vc38UQ2")  
Layout des Datumsobjekts mit Bitfeld der Länge 0 \(null\)  
  
 Der zugrunde liegende Typ eines Bitfelds muss ein ganzzahliger Typ sein, wie unter [Grundlegende Typen](../cpp/fundamental-types-cpp.md) beschrieben.  
  
## Einschränkungen bei Bitfeldern  
 Die folgende Liste zeigt Einzelheiten zu fehlerhaften Operationen in Bitfeldern:  
  
1.  Verwenden der Adresse eines Bitfelds.  
  
2.  Initialisieren eines Verweises mit einem Bitfeld.  
  
## Siehe auch  
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)