---
title: "C-Speicherklassen"
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
  - "C"
helpviewer_keywords: 
  - "Lebensdauer, Variablen"
  - "Bezeichner, Speicherklasse"
  - "Statische Variablen, Lebensdauer"
  - "Speicherklassenspezifizierer, C-Speicherklassen"
  - "Speicherklassen"
  - "Speicherdauer"
ms.assetid: 893fb929-f7a9-43dc-a0b3-29cb1ef845c1
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# C-Speicherklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die "Speicherklasse" einer Variablen bestimmt, ob das Element eine "globale" oder "lokale" Lebensdauer hat.  Diese zwei Angaben zur Lebensdauer werden von C als "static" oder "automatic" aufgerufen. Ein Element mit einer globalen Lebensdauer ist während der gesamten Ausführung des Programms vorhanden und verfügt über einen Wert.  Alle Funktionen haben eine globale Lebensdauer.  
  
 Automatischen Variablen oder Variablen mit lokaler Lebensdauer wird jedes Mal neuer Speicherplatz zugeordnet, wenn die Ausführungssteuerung an den Block übergeben wird, in dem sie definiert sind.  Wenn die Ausführung zurückkehrt, haben die Variablen keine sinnvollen Werte mehr.  
  
 C stellt die folgenden Speicherklassenspezifizierer bereit:  
  
## Syntax  
 *storage\-class\-specifier*:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **\_\_declspec** \( *extended\-decl\-modifier\-seq* \) \/\* Microsoft\-spezifisch \*\/  
  
 Mit Ausnahme von `__declspec` können Sie in einer Deklaration nur einen *storage\-class\-specifier* im *declaration\-specifier* verwenden.  Wenn keine Speicherklassenspezifikation vorhanden ist, erstellen die Deklarationen in einem Block automatische Objekte.  
  
 Elemente, die mit dem **auto**\- oder **register**\-Spezifizierer deklariert werden, verfügen über eine lokale Lebensdauer.  Elemente, die mit dem **static**\- oder `extern`\-Spezifizierer deklariert werden, verfügen über eine globale Lebensdauer.  
  
 Da sich `typedef` und `__declspec` semantisch von den anderen vier *storage\-class\-specifier*\-Terminalen unterscheiden, werden diese gesondert behandelt.  Spezifische Informationen zu `typedef` finden Sie unter [Typedef\-Deklarationen](../c-language/typedef-declarations.md).  Spezifische Informationen zu `__declspec` finden Sie unter [Speicherklassenattribute \(erweitert\)](../c-language/c-extended-storage-class-attributes.md).  
  
 Die Platzierung der Variablen\- und Funktionsdeklarationen innerhalb der Quelldateien wirkt sich auch auf die Speicherklasse und die Sichtbarkeit aus.  Deklarationen außerhalb von sämtlichen Funktionsdefinitionen treten auf "externer Ebene" auf. Deklarationen innerhalb von Funktionsdefinitionen treten auf "interner Ebene" auf.  
  
 Die genaue Bedeutung von jedem Speicherklassenspezifizierer hängt von zwei Faktoren ab:  
  
-   Ob die Deklaration auf der externen oder internen Ebene auftritt  
  
-   Ob das deklarierte Element eine Variable oder eine Funktion ist  
  
 Unter [Speicherklassenspezifizierer für Deklarationen der externen Ebene](../c-language/storage-class-specifiers-for-external-level-declarations.md) und [Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md) finden Sie eine Beschreibung der *storage\-class\-specifier*\-Terminale in der jeweiligen Deklarationsart und eine Erläuterung des Standardverhaltens, wenn der *storage\-class\-specifier* in einer Variable weggelassen wird.  Unter [Speicherklassenspezifizierer mit Funktionsdeklarationen](../c-language/storage-class-specifiers-with-function-declarations.md) finden Sie eine Erläuterung zu Speichernklassenspezifizierern, die mit Funktionen verwendet werden.  
  
## Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)