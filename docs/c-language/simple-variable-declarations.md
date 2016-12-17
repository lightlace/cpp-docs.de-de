---
title: "Einfache Variablendeklarationen"
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
  - "Deklarieren von Variablen, Einfach"
  - "Nicht typisierte Variablen"
ms.assetid: b07adf9d-9e79-4b64-8a34-e6fe1c7eccec
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Einfache Variablendeklarationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Deklaration einer einfachen Variable, die einfachste Form eines direkten Deklarators, gibt den Namen und den Typ der Variable an.  Sie gibt auch die Speicherklasse und den Datentyp für die Variable an.  
  
 Variablendeklarationen erfordern Speicherklassen oder Typen \(oder beides\).  Nicht typisierte Variablen \(wie `var;`\) generieren Warnungen.  
  
## Syntax  
 `declarator`:  
 *pointer*  opt  
  
 *direct\-declarator*  
  
 *direct\-declarator*:  
 *identifier*  
  
 *identifier*:  
 *nondigit*  
  
 *Bezeichner, keine Ziffer*  
  
 *Bezeichner, Ziffer*  
  
 Bei arithmetischen Typen, Struktur\-, Union\-, Enumerations\- und void\-Typen sowie für durch `typedef`\-Namen dargestellte Typen können einfache Deklaratoren in einer Deklaration verwendet werden, da der Typspezifizierer alle Typisierungsinformationen bereitstellt.  Zeiger\-, Array\- und Funktionstypen benötigen komplexere Deklaratoren.  
  
 Sie können eine Liste mit durch Komma \(**,**\) getrennten Bezeichnern verwenden, um mehrere Variablen in der gleichen Deklaration anzugeben.  Alle Variablen, die in der Deklaration definiert sind, weisen denselben Basistyp auf.  Beispiel:  
  
```  
int x, y;        /* Declares two simple variables of type int */  
int const z = 1; /* Declares a constant value of type int */  
```  
  
 Die Variablen `x` und `y` können einen beliebigen Wert des Satzes enthalten, der vom `int`\-Typ für eine bestimmte Implementierung definiert wird.  Das einfache Objekt `z` wird auf den Wert 1 initialisiert und ist nicht änderbar.  
  
 Falls die Deklaration von `z` für eine nicht initialisierte statische Variable oder für den Dateibereich bestimmt wäre, erhielte sie den Anfangswert 0, und dieser Wert wäre nicht änderbar.  
  
```  
unsigned long reply, flag; /* Declares two variables  
                              named reply and flag     */  
```  
  
 In diesem Beispiel haben beide Variablen `reply` und `flag` einen `unsigned long`\-Typ und enthalten Ganzzahlwerte ohne Vorzeichen.  
  
## Siehe auch  
 [Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)