---
title: 2.5.2 parallel Sections-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6f7a84e322cb273733c6a724ee2563928df8362
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="252-parallel-sections-construct"></a>2.5.2 parallel sections-Konstrukt
Die **parallel Sections-** Richtlinie stellt eine Verknüpfung Form zum Angeben einer **parallele** mit nur einem einzelnen Region **Abschnitte** Richtlinie. Die Semantik ist identisch mit der Angabe von explizit eine **parallele** Richtlinie unmittelbar gefolgt von einer **Abschnitte** Richtlinie. Die Syntax der **parallel Sections-** Richtlinie lautet wie folgt:  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block  ]  
   ...  
}  
```  
  
 Die *Klausel* kann eine der Klauseln, die vom akzeptiert die **parallele** und **Abschnitte** Direktiven, mit Ausnahme der **Nowait** Klausel.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **Parallele** -Direktive finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8".  
  
-   **Abschnitte** -Direktive finden Sie unter [Abschnitt 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) auf Seite "14".