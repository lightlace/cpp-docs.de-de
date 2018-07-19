---
title: 2.6.4 atomic-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66f0dc8469d1d70b2697df1fe120f10142d90dbe
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688127"
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
  
-   `binop` ist kein überladenen Operators und ist von +, *, -, /, &, ^, &#124;, <\<, oder >>.  
  
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