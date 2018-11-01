---
title: 2.5.1 parallel for-Konstrukt | Microsoft-Dokumentation
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
ms.openlocfilehash: cfff3b0c17dd098b5d802af61a7ca1f81cb02845
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373960"
---
# <a name="251-parallel-for-construct"></a>2.5.1 parallel for-Konstrukt

Die **für parallele** Richtlinie ist eine Abkürzung für eine **parallele** Bereich, nur eine einzige enthält **für** Richtlinie. Die Syntax der **für parallele** Richtlinie lautet wie folgt:

```
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Mit dieser Direktive können alle Klauseln der der **parallele** Richtlinie und die **für** , außer die Richtlinie der `nowait` -Klausel, wobei identische Bedeutung und den gleichen Einschränkungen. Die Semantik ist identisch mit explizit angeben, ein **parallele** unmittelbar nach der Richtlinie eine **für** Richtlinie.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **Parallele** -Anweisung finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.

- **für** -Anweisung finden Sie unter [Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite "11".

- Daten-Attribut-Klauseln, finden Sie unter [2.7.2 Datenfreigabe-Attribut Klauseln](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.