---
title: LOKAL (MASM) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8105bc8168ce28d468a1378c5cf7889907a7c9f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685062"
---
# <a name="local-masm"></a>LOCAL (MASM)

In der ersten Anweisung, innerhalb eines Makros **lokalen** definiert, die für jede Instanz des Makros eindeutig sind.

## <a name="syntax"></a>Syntax

> LOKALE *Localname* [[, *Localname*]]...

> LOKALE *Bezeichnung* [[[*Anzahl*]]] [[:*Typ*]] [[, *Bezeichnung* [[[*Anzahl*]]] [[ *Typ*]]]]...

## <a name="remarks"></a>Hinweise

In der zweiten Anweisung, in der Definition einer Prozedur (**PROC**), **lokalen** erstellt stapelbasierten Variablen, die für die Dauer der Prozedur vorhanden sind. Die *Bezeichnung* möglicherweise als einfache Variable oder ein Array mit *Anzahl* Elemente.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>