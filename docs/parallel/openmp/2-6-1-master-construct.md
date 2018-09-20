---
title: 2.6.1 master-Konstrukt | Microsoft-Dokumentation
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
ms.openlocfilehash: 8d82ae673e428c635172f35f9b0f682aa65dc2b8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445632"
---
# <a name="261-master-construct"></a>2.6.1 master-Konstrukt

Die **master** -Direktive identifiziert ein Konstrukt, das einem strukturierten Block gibt an, die durch die master-Thread des Teams ausgeführt wird. Die Syntax der **master** Richtlinie lautet wie folgt:

```
#pragma omp master new-linestructured-block
```

Andere Threads in das Team werden den zugeordneten strukturierten Block nicht ausgeführt werden. Es gibt keine implizite Hindernisse, die entweder zu Beginn oder nach Beendigung der master-Konstrukt.