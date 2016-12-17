---
title: "2.6.4 atomic-Konstrukt"
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
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.4 atomic-Konstrukt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `atomic` Richtlinie stellt sicher, dass ein bestimmten Speicherbereich atomar aktualisiert wird, anstatt das Verfügbarmachen für die Möglichkeit, mehrere gleichzeitige Threads schreiben. Die Syntax der `atomic` Richtlinie lautet wie folgt:  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 Die Ausdrucksanweisung muss eine der folgenden Formen haben:  
  
 *X binop*= *Ausdruck*  
  
 x++  
  
 ++x  
  
 x--  
  
 --x  
  
 In den vorherigen Ausdrücken:  
  
-   *X* ist ein Lvalue-Ausdruck mit skalaren Typ.  
  
-   *Expr* ist ein Ausdruck mit skalaren Typ und keinen Verweis auf das Objekt von benannten *x*.  
  
-   `binop` kein überladener Operator und eines +, *, -, /, &, ^, &#124; <\<, oder >>.  
  
 Zwar Implementierung definiert, ob eine Implementierung ersetzt `atomic` Direktiven mit **kritische** Direktiven, die den gleichen eindeutigen *Namen*,  `atomic` Richtlinie ermöglicht bessere Optimierung. Häufig Hardware Anweisungen stehen zur Verfügung, die atomare Aktualisierung mit der geringsten Aufwand ausführen kann.  
  
 Nur für das Laden und Speichern des Objekts bezeichneten *x* atomar sind; die Auswertung der *Expr* ist nicht atomar. Um Racebedingungen zu vermeiden, sollten alle Updates des Speicherorts parallel mit geschützt werden die `atomic` Richtlinie, mit Ausnahme derjenigen, die bekanntermaßen frei von Racebedingungen.  
  
 Einschränkungen auf die `atomic` Richtlinie lauten wie folgt:  
  
-   Alle atomic Verweise auf den Speicherort X in der gesamten Anwendung sind erforderlich, um einen kompatiblen Typ aufweisen.  
  
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