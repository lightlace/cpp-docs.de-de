---
title: Nebeneffekte | Microsoft-Dokumentation
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
- expression evaluation, side effects
- side effects in expression evaluation
ms.assetid: d9b3004a-830e-43a0-bea5-8989d501d670
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e6e6dff87e447a3885906130b6a08286643d6a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="side-effects"></a>Nebeneffekte
Die Reihenfolge der Auswertung von Ausdrücken wird durch die spezifische Implementierung definiert, außer wenn die Sprache eine bestimmte Auswertungsreihenfolge sicherstellt (wie in [Precedence and Order of Evaluation](../c-language/precedence-and-order-of-evaluation.md) [Vorrang und Reihenfolge der Auswertung] beschrieben). Zum Beispiel treten Nebeneffekte in den folgenden Funktionsaufrufen auf:  
  
```  
add( i + 1, i = j + 2 );  
myproc( getc(), getc() );  
```  
  
 Die Argumente eines Funktionsaufrufs können in einer beliebigen Reihenfolge ausgewertet werden. Der Ausdruck `i + 1` kann vor `i = j + 2` ausgewertet werden bzw. `i = j + 2` kann vor `i + 1` ausgewertet werden. Das Ergebnis ist in jedem Fall unterschiedlich. Entsprechend ist es nicht möglich, sicherzustellen, welche Zeichen tatsächlich an `myproc` übergeben werden. Da unäre Inkrementier- und Dekrementiervorgänge Zuweisungen einschließen, können solche Vorgänge Nebeneffekte verursachen, wie im folgenden Beispiel gezeigt:  
  
```  
x[i] = i++;  
```  
  
 In diesem Beispiel ist der Wert von `x`, der geändert wird, unvorhersehbar. Der Wert des Index kann entweder der neue oder der alte Wert von `i` sein. Das Ergebnis variiert in verschiedenen Compilern oder Optimierungsebenen.  
  
 Da C nicht die Reihenfolge der Auswertung von Nebeneffekten definiert, sind beide Bewertungsverfahren, die oben besprochen wurden, korrekt und können implementiert werden. Um sicherzustellen, dass der Code portabel und eindeutig ist, vermeiden Sie Anweisungen, die von einer bestimmten Auswertungsreihenfolge für Nebeneffekte abhängen.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrucksauswertung](../c-language/expression-evaluation-c.md)