---
title: 2.5.1 parallel for-Konstrukt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7dcd763b68a78e11c3c33bf3d750a26e88ad02ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="251-parallel-for-construct"></a>2.5.1 parallel for-Konstrukt
Die **für parallele** Richtlinie ist eine Kurzform für eine **parallele** Bereich, nur einen einzigen enthält **für** Richtlinie. Die Syntax der **für parallele** Richtlinie lautet wie folgt:  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop  
```  
  
 Diese Direktive ermöglicht die Klauseln der der **parallele** Richtlinie und die **für** Richtlinie, mit Ausnahme der `nowait` -Klausel, identische Bedeutung und Einschränkungen. Die Semantik ist identisch mit der Angabe von explizit eine **parallele** Richtlinie unmittelbar gefolgt von einer **für** Richtlinie.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **Parallele** -Direktive finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8".  
  
-   **für** -Direktive finden Sie unter [Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite "11".  
  
-   Daten-Attribut-Klauseln finden Sie unter [2.7.2 Datenfreigabe Attribut Klauseln](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite "25".