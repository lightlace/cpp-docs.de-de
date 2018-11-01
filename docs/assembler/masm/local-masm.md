---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c8ea49b9862159a5a56bfb3d2c3cd0c1f4cd7413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596871"
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