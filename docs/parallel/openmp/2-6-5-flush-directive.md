---
title: 2.6.5 flush-Direktive | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad3b34195015f57955c5be685807ec43f0a8f8c6
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692336"
---
# <a name="265-flush-directive"></a>2.6.5 flush-Anweisung
Die **leeren** Richtlinie, ob explizit oder implizit, gibt einen "threadübergreifenden" Sequenzpunkt, an dem die Implementierung erforderlich ist, um sicherzustellen, dass alle Threads in einem Team eine konsistente Sicht der bestimmte Objekte (unten) in angegeben haben, Arbeitsspeicher. Dies bedeutet, dass vorherige auswertungen von Ausdrücken, die auf diese Objekte verweisen, abgeschlossen sind, und nachfolgende auswertungen wurden noch nicht gestartet. Z. B. Compiler müssen die Werte der Objekte von Registern wiederherstellen, in den Speicher und Hardware möglicherweise leeren Schreibzugriff Puffer in den Speicher und die Werte der Objekte aus dem Speicher erneut zu laden.  
  
 Die Syntax der **leeren** Richtlinie lautet wie folgt:  
  
```  
#pragma omp flush [(variable-list)]  new-line  
```  
  
 Wenn die Objekte, die eine Synchronisierung erfordern alle Variablen festgelegt werden können, und klicken Sie dann diese Variablen werden, in dem optionalen angegeben können *Variablenliste*. Wenn ein Zeiger im vorhanden ist die *Variablenliste*, der Zeiger selbst geleert wird, nicht das Objekt der Zeiger verweist auf.  
  
 Ein **leeren** ohne die Richtlinie ein *Variablenliste* aller freigegebenen Objekte außer kann nicht zugegriffen werden Objekte mit automatischer Speicherdauer synchronisiert. (Dies ist wahrscheinlich mehr Aufwand beim Nachrichtenübergabemechanismus gegenüber einer **leeren** mit einer *Variablenliste*.) Ein **leeren** ohne die Richtlinie ein *Variablenliste* wird impliziert, für die folgenden Direktiven:  
  
-   `barrier`  
  
-   Bei Eingang und das Ende von **kritisch**  
  
-   Bei Eingang und das Ende von `ordered`  
  
-   Bei Eingang und das Ende von **parallel**  
  
-   Beenden Sie at **für**  
  
-   Beenden Sie at **Abschnitte**  
  
-   Beenden Sie at **einzelne**  
  
-   Bei Eingang und das Ende von **für parallele**  
  
-   Bei Eingang und das Ende von **parallel Sections-**  
  
 Die Richtlinie wird nicht impliziert, wenn eine `nowait` -Klausel vorhanden ist. Es sollte beachtet werden, die **leeren** Richtlinie gilt nicht für eine der folgenden:  
  
-   Auf Eintrag **für**  
  
-   Auf Eintrag oder Beenden von **master**  
  
-   Auf Eintrag **Abschnitte**  
  
-   Auf Eintrag **einzelne**  
  
 Ein Verweis, der den Wert eines Objekts mit einem Volatile-qualified-Typ greift auf verhält, als wäre es ein **leeren** Richtlinie, die das Objekt am vorherigen Sequenzpunkt angeben. Ein Verweis, der den Wert eines Objekts mit einem Volatile-qualified-Typ ändert, verhält sich, als wäre es ein **leeren** Richtlinie, die dieses Objekt die nachfolgende Folge Zeitpunkt angeben.  
  
 Beachten Sie, dass, weil die **leeren** Richtlinie verfügt nicht über eine C-Language-Anweisung als Teil der Syntax, bestehen einige Einschränkungen auf die Platzierung innerhalb eines Programms. Finden Sie unter [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) für die formale Grammatik. Das folgende Beispiel veranschaulicht diese Einschränkungen.  
  
```  
/* ERROR - The flush directive cannot be the immediate  
*          substatement of an if statement.  
*/  
if (x!=0)  
   #pragma omp flush (x)  
...  
  
/* OK - The flush directive is enclosed in a  
*      compound statement  
*/  
if (x!=0) {  
   #pragma omp flush (x)  
}  
```  
  
 Einschränkungen für die **leeren** Richtlinie lauten wie folgt:  
  
-   Eine Variable, die im angegebenen eine **leeren** Richtlinie dürfen keinen Referenztyp darstellt.