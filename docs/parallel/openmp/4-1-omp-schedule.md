---
title: 4.1 OMP_SCHEDULE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e13332077a40e741f56b5602ac5197bbdfef071
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691049"
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE
**OMP_SCHEDULE** gilt nur für **für** und **für parallele** Direktiven, die den Typ "Zeitplan" haben **Runtime**. Die Zeitplan-Typ und Block Größe für alle solchen Schleifen kann zur Laufzeit festgelegt werden, durch diese Umgebungsvariable festlegen, um den Zeitplan erkannten Typen und eine optionale *Chunk_size*.  
  
 Für **für** und **für parallele** Direktiven, die einen Zeitplantyp anders als **Runtime**, **OMP_SCHEDULE** wird ignoriert. Der Standardwert für diese Umgebungsvariable wird die Implementierung definiert. Wenn das optionale *Chunk_size* festgelegt ist, wird der Wert muss positiv sein. Wenn *Chunk_size* ist nicht festgelegt ist, wird der Wert 1 wird davon ausgegangen, außer im Fall von einem **statische** Zeitplan. Für eine **statische** Zeitplan, die Standardblockgröße festgelegt ist, die Schleife Iteration Speicherplatz geteilt durch die Anzahl der Threads, die auf die Schleife angewendet.  
  
 Beispiel:  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **für** -Direktive finden Sie unter [Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite "11".  
  
-   **für die parallele** -Direktive finden Sie unter [Abschnitt 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) auf Seite "16".