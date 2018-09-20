---
title: 4.3 OMP_DYNAMIC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c15fa9d8c9d86b736bfc577a3b17e9809ec9baaf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439197"
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC

Die **OMP_DYNAMIC** Umgebungsvariablen aktiviert oder deaktiviert die dynamische Anpassung der Anzahl der Threads, die für die Ausführung von parallelen Bereichen verfügbar, wenn die dynamische Anpassung explizit aktiviert oder deaktiviert werden, durch den Aufruf der **Omp_set_dynamic** Bibliotheksroutine. Muss sein Wert **"true"** oder **"false"**.

Wenn auf festgelegt **"true"**, die Anzahl der Threads, die verwendet werden, für die Ausführung von paralleler Bereichen kann angepasst werden, von der Laufzeitumgebung Systemressourcen optimal zu nutzen.  Wenn auf festgelegt **"false"**, dynamische Anpassung ist deaktiviert. Die standardbedingung wird die Implementierung definiert.

Beispiel:

```
setenv OMP_DYNAMIC TRUE
```

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- Weitere Informationen zu parallelen Bereichen, finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.

- **Omp_set_dynamic** funktionieren, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.