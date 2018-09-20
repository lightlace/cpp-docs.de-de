---
title: Firstprivate | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d070b8de3cf0382447c3b8e756140892dcd85edc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387119"
---
# <a name="firstprivate"></a>firstprivate

Gibt an, dass jeder Thread eine eigene Instanz einer Variablen zugewiesen werden soll, und die Variable mit dem Wert der Variablen initialisiert werden soll, da sie vor dem das parallele Konstrukt vorhanden ist.

## <a name="syntax"></a>Syntax

```
firstprivate(var)
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`var`|Die Instanzen in jeder Thread und die Variable wird mit dem Wert der Variablen an, initialisiert werden, da sie vor dem das parallele Konstrukt vorhanden ist. Wenn mehr als eine Variable angegeben ist, trennen Sie Namen durch ein Komma.|

## <a name="remarks"></a>Hinweise

## <a name="remarks"></a>Hinweise

`firstprivate` gilt für die folgenden Anweisungen:

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)

- [single](../../../parallel/openmp/reference/single.md)

Weitere Informationen finden Sie unter [2.7.2.2 Firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).

## <a name="example"></a>Beispiel

Ein Beispiel der Verwendung von `firstprivate`, siehe das Beispiel in [private](../../../parallel/openmp/reference/private-openmp.md).

## <a name="see-also"></a>Siehe auch

[Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)