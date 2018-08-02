---
title: Auflösen mehrdeutiger Deklarationen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc5b5a2b7d8add493efc144931160afb7d15020
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467878"
---
# <a name="resolving-ambiguous-declarations-c"></a>Auflösen mehrdeutiger Deklarationen (C++)
Um explizite Konvertierungen von einem Typ zum anderen auszuführen, müssen Sie die Umwandlungen verwenden, die den angestrebten Typnamen angeben. Einige Typumwandlungen führen zu einer syntaktischen Mehrdeutigkeit. Die folgenden Typumwandlungen in Funktionstypen sind mehrdeutig:  
  
```cpp 
char *aName( String( s ) );  
```  
  
 Es ist unklar, ob es sich um eine Funktionsdeklaration oder eine Objektdeklaration mit einer Umwandlung im Funktionsstil als Initialisierer handelt: Es kann eine Funktion, die Rückgabe von Typ deklariert `char *` , akzeptiert ein Argument vom Typ `String`, oder deklarieren sie das Objekt `aName` und initialisieren Sie es mit dem Wert des `s` Umwandlung zum Typ `String`.  
  
 Wenn eine Deklaration als eine gültige Funktionsdeklaration betrachtet werden kann, wird sie als solche behandelt. Nur wenn sie keine Funktionsdeklaration sein kann – d. h., wenn sie syntaktisch falsch wäre – wird eine Anweisung daraufhin überprüft, ob sie eine Funktionsformattypumwandlung ist. Daher betrachtet der Compiler die Anweisung als Deklaration einer Funktion und ignoriert die Klammern um den `s`-Bezeichner. Andererseits sind die Anweisungen  
  
```cpp 
char *aName( (String)s );  
```  
  
 und  
  
```cpp 
char *aName = String( s );  
```  
  
 sind eindeutig Deklarationen von Objekten und eine benutzerdefinierte Konvertierung von Typ `String` eingeben `char *` wird aufgerufen, um die Initialisierung von `aName`.  