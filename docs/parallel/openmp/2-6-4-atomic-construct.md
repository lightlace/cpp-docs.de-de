---
title: 2.6.4 atomic-Konstrukt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 629fff5b0bef507b775fbe1b5bfabadd50b790be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="264-atomic-construct"></a>2.6.4 atomic-Konstrukt
Die `atomic` Richtlinie stellt sicher, dass eine bestimmte Speicheradresse atomar aktualisiert wird, anstatt eine Offenlegung für die Möglichkeit, mehrere gleichzeitige Threads zu schreiben. Die Syntax der `atomic` Richtlinie lautet wie folgt:  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 Die Ausdrucksanweisung muss einen der folgenden Formate aufweisen:  
  
 *X binop*= *Expr*  
  
 x++  
  
 ++x  
  
 x--  
  
 --x  
  
 In den vorherigen Ausdrücken:  
  
-   *X* ist ein Lvalue-Ausdruck mit skalaren Typ.  
  
-   *Expr* ist ein Ausdruck mit skalaren Typ und keinen Verweis auf das Objekt vom angegebenen *x*.  
  
-   `binop`ist kein überladenen Operators und ist von +, *, -, /, &, ^, &#124; <\<, oder >>.  
  
 Obwohl es Implementierung definiert ist, gibt an, ob eine Implementierung ersetzt `atomic` Direktiven mit **kritische** Direktiven, die den gleichen eindeutigen *Name*, die `atomic` Richtlinie ermöglicht eine bessere Optimierung. Häufig Hardware Anweisungen stehen zur Verfügung, das atomarische Update mit der geringsten Aufwand ausführen kann.  
  
 Nur für das Laden und Speichern des Objekts, das vom angegebenen *x* sind atomar; die Auswertung der *Expr* ist nicht atomar. Um Racebedingungen zu vermeiden, sollten alle Updates des Speicherorts parallel mit geschützt werden die `atomic` Richtlinie, mit Ausnahme derjenigen, die bekanntermaßen frei von Racebedingungen.  
  
 Einschränkungen für die `atomic` Richtlinie lauten wie folgt:  
  
-   Alle atomic Verweise auf den Speicherort X in der gesamten Anwendung muss einen kompatiblen Typ sein.  
  
## <a name="examples"></a>Beispiele:  
  
```  
extern float a[], *p = a, b;  
/* Protect against races among multiple updates. */  
#pragma omp atomic  
a[index[i]] += b;  
/* Protect against races with updates through a. */  
#pragma omp atomic  
p[i] -= 1.0f;  
  
extern union {int n; float x;} u;  
/* ERROR - References through incompatible types. */  
#pragma omp atomic  
u.n++;  
#pragma omp atomic  
u.x -= 1.0f;  
```