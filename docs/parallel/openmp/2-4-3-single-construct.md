---
title: 2.4.3 single-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db3f9ca834fb3f35c95732698fd02e16f31b4225
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690581"
---
# <a name="243-single-construct"></a>2.4.3 single-Konstrukt
Die **einzelne** Richtlinie identifiziert ein Konstrukt, das angibt, dass die zugeordneten strukturierte Block nur einem Thread im Team (nicht unbedingt der master-Thread) ausgeführt wird. Die Syntax der **einzelne** Richtlinie lautet wie folgt:  
  
```  
#pragma omp single [clause[[,] clause] ...] new-linestructured-block  
```  
  
 Die-Klausel ist eine der folgenden:  
  
 **Private (** *Variablenliste* **)**  
  
 **Firstprivate (** *Variablenliste* **)**  
  
 **Copyprivate (** *Variablenliste* **)**  
  
 **nowait**  
  
 Besteht eine implizite Barriere nach der **einzelne** erstellen, es sei denn, eine **Nowait** -Klausel angegeben ist.  
  
 Einschränkungen für die **einzelne** Richtlinie lauten wie folgt:  
  
-   Nur ein einzelner **Nowait** -Klausel kann angezeigt werden, auf eine **einzelne** Richtlinie.  
  
-   Die **Copyprivate** Klausel darf nicht verwendet werden, mit der **Nowait** Klausel.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **private**, **Firstprivate**, und **Copyprivate** -Klausel finden Sie unter [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite "25".