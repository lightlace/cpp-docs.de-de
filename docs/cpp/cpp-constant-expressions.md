---
title: C++-Konstante Ausdrücke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06a07c9d37994b4214da9b2eb53d02104525d7c4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408111"
---
# <a name="c-constant-expressions"></a>C++-Ausdrücke (konstant)
Ein *Konstanten* Wert ist, die sich nicht ändert. C++ bietet zwei Schlüsselwörter, mit denen Sie den Zweck eines Objekts angeben können, der nicht dazu gedacht ist, geändert zu werden, und diese Absicht erzwingen soll.  
  
C++ erfordert konstante Ausdrücke – Ausdrücke, die als Konstante ausgewertet werden – für Deklarationen von:  
  
 -   Arraygrenzen  
      
 -   Selektoren in case-Anweisungen  
      
 -   Bitfeldlängenangabe  
      
 -   Enumerationsinitialisierer  
  
Die einzigen Operanden, die in konstanten Ausdrücken zulässig sind, lauten:  
  
 -   Literale  
      
 -   Enumerationskonstanten  
      
 -   Werte, die als Konstanten deklariert sind und mit konstanten Ausdrücken initialisiert werden.  
      
 -   **"sizeof"** Ausdrücke  
  
Konstanten, die keine Ganzzahlen sind, müssen (entweder explizit oder implizit) in ganzzahlige Typen konvertiert werden, um in einem konstanten Ausdruck zulässig zu sein. Daher ist der folgende Code gültig:  
  
```cpp 
const double Size = 11.0;  
char chArray[(int)Size];  
```  
  
Explizite Konvertierungen in ganzzahlige Typen sind in Konstanten Ausdrücken zulässig; Alle anderen Typen und abgeleiteten Typen sind nicht zulässig, außer bei Verwendung als Operanden für die **"sizeof"** Operator.  
  
Der Kommaoperator sowie Zuweisungsoperatoren können nicht in konstanten Ausdrücken verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdruckstypen](../cpp/types-of-expressions.md)