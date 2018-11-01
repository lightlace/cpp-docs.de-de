---
title: 4.4 OMP_NESTED
ms.date: 11/04/2016
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
ms.openlocfilehash: e45b8901c56923ab37ca387a5f057c5b41af21f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453620"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED

Die `OMP_NESTED` Umgebungsvariablen aktiviert oder geschachtelte Parallelität deaktiviert, es sei denn, geschachtelte Parallelität aktiviert oder werden, durch den Aufruf deaktiviert der `o` **Mp_set_nested** Bibliotheksroutine. Wenn auf festgelegt **"true"**, geschachtelte Parallelität aktiviert ist; Wenn sie, um festgelegt ist **"false"**, geschachtelte Parallelität deaktiviert ist. Der Standardwert ist **"false"**.

Beispiel:

```
setenv OMP_NESTED TRUE
```

## <a name="cross-reference"></a>Referenz:

- `omp_set_nested` funktionieren, finden Sie unter [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite "40".