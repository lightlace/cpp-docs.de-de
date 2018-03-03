---
title: 2.4.3 single-Konstrukt | Microsoft Docs
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
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72dc551986f149bda668c438ac5f51d01d530c51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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