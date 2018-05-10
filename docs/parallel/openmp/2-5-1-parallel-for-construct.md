---
title: 2.5.1 parallel for-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef2732c4f8713466d282346ea240bd3c41886ce0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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