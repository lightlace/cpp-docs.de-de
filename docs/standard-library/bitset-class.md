---
title: "bitset-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bitset/std::bitset"
  - "std::bitset"
  - "std.bitset"
  - "bitset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitset-Klasse"
ms.assetid: 28b86964-87b4-429c-8124-b6c251b6c50b
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# bitset-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Typ von Objekt, das eine Sequenz speichert, die aus einer festen Anzahl von Bits besteht, die eine kompakte Möglichkeit bieten, Flags für eine Menge von Elementen oder Bedingungen bereitzustellen.  Die bitset\-Klasse unterstützt Vorgänge für Objekte des Typs „bitset“, die eine Auflistung von Bits enthalten und zeitlich konstanten Zugriff auf jedes Bit ermöglichen.  
  
## Syntax  
  
```  
  
     template <size_t   
     N  
     >  
class bitset  
```  
  
#### Parameter  
 *N*  
 Gibt die Anzahl von Bits im bitset\-Objekt als ganze Zahl ungleich null des Typs **size\_t** an, die zum Zeitpunkt der Kompilierung bekannt sein muss.  
  
## Hinweise  
 Im Gegensatz zur ähnlichen [vector\<bool\>\-Klasse](../standard-library/vector-bool-class.md) hat die bitset\-Klasse keine Iteratoren, und sie ist kein Container für eine Standardvorlagenbibliothek.  Sie unterscheidet sich auch dadurch von „vector\<bool\>“, dass sie eine bestimmte Größe hat, die zum Zeitpunkt der Kompilierung entsprechend der Größe festgelegt ist, die durch den Vorlagenparameter **N** angegeben ist, wenn **bitset\<N\>** deklariert ist.  
  
 Ein Bit ist festgelegt, wenn es den Wert 1 hat, und zurückgesetzt, wenn es den Wert 0 hat.  Ein Bit zu wechseln oder umzuschalten bedeutet, dass sein Wert von 1 in 0 oder von 0 in 1 geändert wird.  Die **N** Bits in einer Bitmenge sind durch ganzzahlige Werte von 0 bis **N** \- 1 indiziert, wobei 0 die erste Bitposition und **N**\- 1 die letzte Bitposition indiziert.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[bitset](../Topic/bitset::bitset.md)|Erstellt ein `bitset<N>`\-Objekt und initialisiert die Bits mit 0 \(Null\), mit einem angegebenen Wert oder mit Werten, die aus Zeichen einer Zeichenfolge ermittelt wurden.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[element\_type](../Topic/bitset::element_type.md)|Ein Typ, der gleichbedeutend mit dem Datentyp `bool` ist und verwendet werden kann, um auf Elementbits in einem `bitset`\-Objekt zu verweisen.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[all](../Topic/bitset::all.md)|Testet alle Bits in diesem `bitset`\-Objekt, um zu ermitteln, ob sie alle auf `true` festgelegt sind.|  
|[alle](../Topic/bitset::any.md)|Die Memberfunktion überprüft, ob jedes Bit in der Sequenz auf 1 festgelegt ist.|  
|[count](../Topic/bitset::count.md)|Die Memberfunktion gibt die Anzahl von Bits zurück, die in der Bitsequenz festgelegt sind.|  
|[flip](../Topic/bitset::flip.md)|Schaltet den Wert aller Bits in einem `bitset`\-Objekt oder ein einzelnes Bit an einer angegebenen Position um.|  
|[Keine](../Topic/bitset::none.md)|Überprüft, ob keines der Bits in einem `bitset`\-Objekt auf 1 festgelegt wurde.|  
|[zurücksetzen](../Topic/bitset::reset.md)|Setzt alle Bits in einem `bitset`\-Objekt oder ein Bit an einer angegebenen Position auf 0 zurück.|  
|[Festlegen](../Topic/bitset::set.md)|Legt alle Bits in einem `bitset`\-Objekt oder ein Bit an einer angegebenen Position auf 1 fest.|  
|[size](../Topic/bitset::size.md)|Gibt die Anzahl von Bits eines `bitset`\-Objekts zurück.|  
|[Test](../Topic/bitset::test.md)|Überprüft, ob das Bit an einer angegebenen Position in einem `bitset`\-Objekt auf 1 festgelegt ist.|  
|[to\_string](../Topic/bitset::to_string.md)|Konvertiert ein `bitset`\-Objekt in eine Zeichenfolgendarstellung.|  
|[to\_ullong](../Topic/bitset::to_ullong.md)|Gibt die Summe der Bitwerte im `bitset`\-Objekt als einen `unsigned long long`\-Wert zurück.|  
|[to\_ulong](../Topic/bitset::to_ulong.md)|Konvertiert ein `bitset`\-Objekt in den `unsigned long`\-Wert, der die Sequenz der enthalten Bits erzeugen würde, wenn er zum Initialisieren des `bitset`\-Objekts verwendet werden würde.|  
  
### Memberklassen  
  
|||  
|-|-|  
|[Verweis](../Topic/bitset::reference.md)|Eine Proxyklasse, die Verweise auf Bits bereitstellt, die in einem `bitset`\-Objekt enthalten sind, das als unterstützende Klasse für den `operator[]` der `bitset`\-Klasse dazu verwendet wird, auf einzelne Bits zuzugreifen sowie einzelne Bits zu verarbeiten.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator\!\=](../Topic/bitset::operator!=.md)|Überprüft ein `bitset`\-Zielobjekt auf Ungleichheit mit einem angegebenen `bitset`\-Objekt.|  
|[operator&\=](../Topic/bitset::operator&=.md)|Kombiniert zwei Bitmengen in einem logischen `AND`\-Vorgang.|  
|[Operator \<\<](../Topic/bitset::operator%3C%3C.md)|Verschiebt die Bits in einem `bitset`\-Objekt um eine angegebene Anzahl von Positionen nach links und gibt das Ergebnis in einem neuen `bitset`\-Objekt zurück.|  
|[operator\<\<\=](../Topic/bitset::operator%3C%3C=.md)|Verschiebt die Bits in einem `bitset`\-Objekt um eine angegebene Anzahl von Positionen nach links und gibt das Ergebnis im selben `bitset`\-Objekt zurück.|  
|[operator\=\=](../Topic/bitset::operator==.md)|Überprüft ein `bitset`\-Zielobjekt auf Gleichheit mit einem angegebenen `bitset`\-Objekt.|  
|[Operator \>\>](../Topic/bitset::operator%3E%3E.md)|Verschiebt die Bits in einem `bitset`\-Objekt um eine angegebene Anzahl von Positionen nach rechts und gibt das Ergebnis in einem neuen `bitset`\-Objekt zurück.|  
|[Operator\>\>\=](../Topic/bitset::operator%3E%3E=.md)|Verschiebt die Bits in einem `bitset`\-Objekt um eine angegebene Anzahl von Positionen nach rechts und gibt das Ergebnis im selben `bitset`\-Objekt zurück.|  
|[operator&#91;&#93;](../Topic/bitset::operator.md)|Gibt einen Verweis auf ein Bit an einer angegebenen Position eines `bitset`\-Objekts zurück, wenn das `bitset` geändert werden kann. Gibt andernfalls den Wert zurück, den das Bit an dieser Position hat.|  
|[Operator^\=](../Topic/bitset::operator%5E=.md)|Kombiniert zwei Bitmengen in einem Exklusiv\-`OR`\-Vorgang.|  
|[Operator&#124;\=](../Topic/bitset::operator%7C=.md)|Kombiniert zwei Bitmengen in einem Inklusiv\-`OR`\-Vorgang.|  
|[Operator~](../Topic/bitset::operator~.md)|Schaltet alle Bits in einem `bitset`\-Zielobjekt um und gibt das Ergebnis zurück.|  
  
## Anforderungen  
 **Header:** \<bitset\>  
  
 **Namespace:** std