---
title: Standard (OpenMP) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ea32f473d96c8f48c6628d8f71212269bd6d345
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392610"
---
# <a name="default-openmp"></a>default (OpenMP)

Gibt das Verhalten ohne bereichseinschränkung Variablen in einem parallelen Bereich an.

## <a name="syntax"></a>Syntax

```
default(shared | none)
```

## <a name="remarks"></a>Hinweise

`shared`, die gilt Wenn die `default` Klausel nicht angegeben ist, bedeutet, dass jede Variable in einem parallelen Bereich behandelt wird, als ob es angegeben wurden, mit der [freigegebenen](../../../parallel/openmp/reference/shared-openmp.md) Klausel. `none` bedeutet, dass alle Variablen, die in einem parallelen Bereich, die mit keinen begrenzten Gültigkeitsbereich haben, verwendet der [private](../../../parallel/openmp/reference/private-openmp.md), [freigegebenen](../../../parallel/openmp/reference/shared-openmp.md), [Verringerung](../../../parallel/openmp/reference/reduction.md), [Firstprivate](../../../parallel/openmp/reference/firstprivate.md), oder [Lastprivate](../../../parallel/openmp/reference/lastprivate.md) -Klausel bewirkt, dass ein Compilerfehler ausgegeben.

`default` gilt für die folgenden Anweisungen:

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)

Weitere Informationen finden Sie unter [2.7.2.5 Standard](../../../parallel/openmp/2-7-2-5-default.md).

## <a name="example"></a>Beispiel

Finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md) ein Beispiel der Verwendung von `default`.

## <a name="see-also"></a>Siehe auch

[Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)