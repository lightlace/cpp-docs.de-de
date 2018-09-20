---
title: OMP_DYNAMIC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b02a2a4d660057ab83da39add7fd32bcff3e6d90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392137"
---
# <a name="ompdynamic"></a>OMP_DYNAMIC

Gibt an, ob die OpenMP zur Laufzeit die Anzahl der Threads in einem parallelen Bereich anpassen kann.

## <a name="syntax"></a>Syntax

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

## <a name="remarks"></a>Hinweise

Die `OMP_DYNAMIC` Umgebungsvariable kann überschrieben werden, indem die [Omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) Funktion.

Der Standardwert in der Visual C++-Implementierung des OpenMP-Standards ist `OMP_DYNAMIC=FALSE`.

Weitere Informationen finden Sie unter [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).

## <a name="example"></a>Beispiel

Der folgende Befehl legt die `OMP_DYNAMIC` -Umgebungsvariable auf "true":

```
set OMP_DYNAMIC=TRUE
```

Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_DYNAMIC` -Umgebungsvariablen angegeben:

```
set OMP_DYNAMIC
```

## <a name="see-also"></a>Siehe auch

[Umgebungsvariablen](../../../parallel/openmp/reference/openmp-environment-variables.md)