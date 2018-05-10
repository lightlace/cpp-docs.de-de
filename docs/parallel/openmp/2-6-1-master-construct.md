---
title: 2.6.1 master-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a60a8df380fdcc0052d8fe2d070c8d926bcb28f8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="261-master-construct"></a>2.6.1 master-Konstrukt
Die **master** Richtlinie identifiziert ein Konstrukt, das einem strukturierten Block gibt an, die durch die master-Thread der vom Team ausgeführt wird. Die Syntax der **master** Richtlinie lautet wie folgt:  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 Andere Threads in das Team den zugeordneten strukturierten Block nicht ausgeführt. Es gibt keine implizite Barriere entweder bei eintritt, oder Beenden der master-Konstrukt.