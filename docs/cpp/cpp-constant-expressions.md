---
title: "C++-Konstante Ausdrücke | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
caps.latest.revision: 8
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8333b761aa51de44c8225e5ace97885eaaed56da
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="c-constant-expressions"></a>C++-Ausdrücke (konstant)
Ein *konstant* Wert wird nicht verändert. C++ bietet zwei Schlüsselwörter, mit denen Sie den Zweck eines Objekts angeben können, der nicht dazu gedacht ist, geändert zu werden, und diese Absicht erzwingen soll.  
  
 C++ erfordert konstante Ausdrücke – Ausdrücke, die als Konstante ausgewertet werden – für Deklarationen von:  
  
-   Arraygrenzen  
  
-   Selektoren in case-Anweisungen  
  
-   Bitfeldlängenangabe  
  
-   Enumerationsinitialisierer  
  
 Die einzigen Operanden, die in konstanten Ausdrücken zulässig sind, lauten:  
  
-   Literale  
  
-   Enumerationskonstanten  
  
-   Werte, die als Konstanten deklariert sind und mit konstanten Ausdrücken initialisiert werden.  
  
-   `sizeof`-Ausdrücke  
  
 Konstanten, die keine Ganzzahlen sind, müssen (entweder explizit oder implizit) in ganzzahlige Typen konvertiert werden, um in einem konstanten Ausdruck zulässig zu sein. Daher ist der folgende Code gültig:  
  
```  
const double Size = 11.0;  
char chArray[(int)Size];  
```  
  
 Explizite Konvertierungen in ganzzahlige Typen sind in konstanten Ausdrücken zulässig; alle anderen Typen und abgeleiteten Typen sind nicht zulässig, sofern sie nicht als Operanden für den `sizeof`-Operator verwendet werden.  
  
 Der Kommaoperator sowie Zuweisungsoperatoren können nicht in konstanten Ausdrücken verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdruckstypen](../cpp/types-of-expressions.md)
