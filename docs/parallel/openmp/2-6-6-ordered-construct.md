---
title: 2.6.6 ordered-Konstrukt | Microsoft-Dokumentation
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
ms.openlocfilehash: 7b83c3dfc13b231a1314343a1dff496acf7a99b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412196"
---
# <a name="266-ordered-construct"></a>2.6.6 ordered-Konstrukt

Die folgenden vor einem strukturierten Block ein **sortiert** Richtlinie ausgeführt wird, in der Reihenfolge, in denen Iterationen in einer sequenziellen Schleife ausgeführt. Die Syntax der **sortiert** Richtlinie lautet wie folgt:

```
#pragma omp ordered new-linestructured-block
```

Ein **sortiert** Richtlinie im dynamischen Wertebereich liegen eine **für** oder **für parallele** zu erstellen. Die **für** oder **für parallele** , der die Richtlinie der **sortiert** Konstrukt Bindungen müssen einen **sortiert** -Klausel angegeben, wie in beschrieben [Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite "11". Bei der Ausführung eine **für** oder **für parallele** erstellen, mit eine **sortiert** -Klausel **sortiert** Konstrukte ausgeführt werden, ausschließlich in der die Reihenfolge, in dem sie in eine sequenzielle Ausführung der Schleife ausgeführt werden sollen.

Einschränkungen für die **sortiert** Richtlinie lauten wie folgt:

- Eine Iteration einer Schleife mit einem **für** Konstrukt muss nicht die gleiche ordered-Direktive mehr als einmal ausgeführt, und er nicht ausgeführt werden muss mehr als eine **sortiert** Richtlinie.