---
title: 4.1 OMP_SCHEDULE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 330e5ea576e3cd779a7c17c21d00b6459f5e7043
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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