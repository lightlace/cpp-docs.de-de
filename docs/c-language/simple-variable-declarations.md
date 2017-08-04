---
title: Einfache Variablendeklarationen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- untyped variables
- declaring variables, simple
ms.assetid: b07adf9d-9e79-4b64-8a34-e6fe1c7eccec
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 03d3939ef04a6a1a8bc5e3cd3ec5bfe56236ca0f
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="simple-variable-declarations"></a>Einfache Variablendeklarationen
Die Deklaration einer einfachen Variable, die einfachste Form eines direkten Deklarators, gibt den Namen und den Typ der Variable an. Sie gibt auch die Speicherklasse und den Datentyp für die Variable an.  
  
 Variablendeklarationen erfordern Speicherklassen oder Typen (oder beides). Nicht typisierte Variablen (wie `var;`) generieren Warnungen.  
  
## <a name="syntax"></a>Syntax  
 `declarator`:  
 *pointer* opt  
  
 *direct-declarator*  
  
 *direct-declarator*:  
 *identifier*  
  
 *identifier*:  
 *nondigit*  
  
 *identifier nondigit*  
  
 *identifier digit*  
  
 Bei arithmetischen Typen, Struktur-, Union-, Enumerations- und void-Typen sowie für durch `typedef`-Namen dargestellte Typen können einfache Deklaratoren in einer Deklaration verwendet werden, da der Typspezifizierer alle Typisierungsinformationen bereitstellt. Zeiger-, Array- und Funktionstypen benötigen komplexere Deklaratoren.  
  
 Sie können eine Liste mit durch Komma (**,**) getrennten Bezeichnern verwenden, um mehrere Variablen in der gleichen Deklaration anzugeben. Alle Variablen, die in der Deklaration definiert sind, weisen denselben Basistyp auf. Zum Beispiel:  
  
```  
int x, y;        /* Declares two simple variables of type int */  
int const z = 1; /* Declares a constant value of type int */  
```  
  
 Die Variablen `x` und `y` können einen beliebigen Wert des Satzes enthalten, der vom `int`-Typ für eine bestimmte Implementierung definiert wird. Das einfache Objekt `z` wird auf den Wert 1 initialisiert und ist nicht änderbar.  
  
 Falls die Deklaration von `z` für eine nicht initialisierte statische Variable oder für den Dateibereich bestimmt wäre, erhielte sie den Anfangswert 0, und dieser Wert wäre nicht änderbar.  
  
```  
unsigned long reply, flag; /* Declares two variables  
                              named reply and flag     */  
```  
  
 In diesem Beispiel haben beide Variablen `reply` und `flag` einen `unsigned long`-Typ und enthalten Ganzzahlwerte ohne Vorzeichen.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)
