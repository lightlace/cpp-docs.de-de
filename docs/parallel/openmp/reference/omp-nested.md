---
title: OMP_NESTED | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c90878ce96cf1639c983be899ba13eccf1f040e8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376533"
---
# <a name="ompnested"></a>OMP_NESTED

Gibt an, ob geschachtelte Parallelität aktiviert ist, es sei denn, geschachtelte Parallelität aktiviert oder deaktiviert ist, `omp_set_nested`.

## <a name="syntax"></a>Syntax

```
set OMP_NESTED[=TRUE | =FALSE]
```

## <a name="remarks"></a>Hinweise

Die `OMP_NESTED` Umgebungsvariable kann überschrieben werden, indem die [Omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) Funktion.

Der Standardwert in der Visual C++-Implementierung des OpenMP-Standards ist `OMP_DYNAMIC=FALSE`.

Weitere Informationen finden Sie unter [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).

## <a name="example"></a>Beispiel

Der folgende Befehl legt die `OMP_NESTED` -Umgebungsvariable auf "true":

```
set OMP_NESTED=TRUE
```

Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_NESTED` -Umgebungsvariablen angegeben:

```
set OMP_NESTED
```

## <a name="see-also"></a>Siehe auch

[Umgebungsvariablen](../../../parallel/openmp/reference/openmp-environment-variables.md)