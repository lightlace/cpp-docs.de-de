---
title: 2.5.2 parallel Sections-Konstrukt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3a76a950d547effccf0b50fa04799814597bc5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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