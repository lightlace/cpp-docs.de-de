---
title: 2.4.2 sections-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20b24c5b7d2458294da6280acb2ba7e8be5961fb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="242-sections-construct"></a>2.4.2 sections-Konstrukt
Die **Abschnitte** Richtlinie identifiziert ein noniterative Arbeit sharing-Konstrukt, das einen Satz von Konstrukte angibt, die zwischen Threads in einem Team unterteilt werden. Jeder Abschnitt wird von einem Thread im Team einmal ausgeführt. Die Syntax der **Abschnitte** Richtlinie lautet wie folgt:  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block ]  
...  
}  
```  
  
 Die-Klausel ist eine der folgenden:  
  
 **Private (** *Variablenliste* **)**  
  
 **Firstprivate (** *Variablenliste* **)**  
  
 **Lastprivate (** *Variablenliste* **)**  
  
 **Verringerung (** *Operator* **:***Variablenliste* **)**  
  
 **nowait**  
  
 Jeder Abschnitt vorangestellt ist ein **Abschnitt** Richtlinie, obwohl die **Abschnitt** Richtlinie ist für den ersten Abschnitt optional. Die **Abschnitt** Direktiven müssen innerhalb der lexikalische Wertebereich angezeigt werden die **Abschnitte** Richtlinie. Besteht eine implizite Barriere am Ende einer **Abschnitte** erstellen, es sei denn, eine **Nowait** angegeben ist.  
  
 Einschränkungen für die **Abschnitte** Richtlinie lauten wie folgt:  
  
-   Ein **Abschnitt** Richtlinie muss nicht außerhalb der lexikalische Wertebereich angezeigt werden. die **Abschnitte** Richtlinie.  
  
-   Nur ein einzelner **Nowait** -Klausel kann angezeigt werden, auf eine **Abschnitte** Richtlinie.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **private**, **Firstprivate**, **Lastprivate**, und **Verringerung** -Klausel finden Sie unter [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite "25".