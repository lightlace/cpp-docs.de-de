---
title: 4.4 OMP_NESTED | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1083269f31ebc710da24430635ff8381e3f2147a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419515"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED

Die `OMP_NESTED` Umgebungsvariablen aktiviert oder geschachtelte Parallelität deaktiviert, es sei denn, geschachtelte Parallelität aktiviert oder werden, durch den Aufruf deaktiviert der `o` **Mp_set_nested** Bibliotheksroutine. Wenn auf festgelegt **"true"**, geschachtelte Parallelität aktiviert ist; Wenn sie, um festgelegt ist **"false"**, geschachtelte Parallelität deaktiviert ist. Der Standardwert ist **"false"**.

Beispiel:

```
setenv OMP_NESTED TRUE
```

## <a name="cross-reference"></a>Referenz:

- `omp_set_nested` funktionieren, finden Sie unter [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite "40".