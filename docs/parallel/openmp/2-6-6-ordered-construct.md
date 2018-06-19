---
title: 2.6.6 ordered-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa66d9fb8a0a9af2fc33497690bfe67a3ea5d717
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690344"
---
# <a name="266-ordered-construct"></a>2.6.6 ordered-Konstrukt
Die folgenden strukturierten Block ein **sortiert** Richtlinie in der Reihenfolge, in dem Iterationen würde, in eine sequenzielle Schleife ausgeführt werden, ausgeführt wird. Die Syntax der **sortiert** Richtlinie lautet wie folgt:  
  
```  
#pragma omp ordered new-linestructured-block  
```  
  
 Ein **sortiert** Richtlinie muss innerhalb der dynamischen Wertebereich einer **für** oder **für parallele** erstellen. Die **für** oder **für parallele** zu dem die Richtlinie die **sortiert** Konstrukt bindet benötigen eine **sortiert** -Klausel angegeben, wie beschrieben in [Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite "11". Bei der Ausführung eine **für** oder **für parallele** erstellen mit eine **sortiert** -Klausel, **sortiert** Konstrukte erfolgen streng in der die Reihenfolge, in dem sie eine sequenzielle Ausführung der Schleife ausgeführt werden würde.  
  
 Einschränkungen für die **sortiert** Richtlinie lauten wie folgt:  
  
-   Eine Iteration einer Schleife mit einer **für** Konstrukt muss nicht ausgeführt werden die gleiche geordnete-Direktive mehr als einmal und müssen Ausführung nicht mehr als eine **sortiert** Richtlinie.