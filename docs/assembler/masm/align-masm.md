---
title: ALIGN (MASM)
ms.date: 01/02/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: 22b18f2e238c780377b84fc2be3eb6678686bb73
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399277"
---
# <a name="align-masm"></a>ALIGN (MASM)

Die **align** -Direktive richtet das nächste Datenelement oder die Anweisung an eine Adresse aus, die ein Vielfaches des Parameters ist. Der-Parameter muss eine Potenz von 2 (z. b. 1, 2, 4 usw.) sein, die kleiner oder gleich der Segment Ausrichtung ist.

## <a name="syntax"></a>Syntax

> ⟦-*Nummer* **Ausrichten** ⟧

## <a name="remarks"></a>Hinweise

Mithilfe der **align** -Direktive können Sie den Anfangs Offset eines Datenelements oder einer Anweisung angeben. Ausgerichtete Daten können die Leistung verbessern, auf Kosten des verschwendeten Speicherplatzes zwischen Datenelementen. Eine hohe Leistungsverbesserung kann angezeigt werden, wenn sich Daten Zugriffe auf Grenzen in Cache Zeilen befinden. Der Zugriff auf natürliche Grenzen für Native Typen bedeutet weniger Zeit in der internen Hardware neuausrichtungs mikrocodierung.

Der Bedarf an ausgerichteten Anweisungen ist selten auf modernen Prozessoren, die ein flatadressierungs Modell verwenden, kann jedoch für Sprung Ziele in älteren Code für andere Adressierungs Modelle erforderlich sein.

Wenn Daten ausgerichtet sind, wird der übersprungene Speicherplatz mit Nullen aufgefüllt. Wenn Anweisungen ausgerichtet sind, wird der übersprungene Speicherplatz mit entsprechend großen NOP-Anweisungen gefüllt.

## <a name="see-also"></a>Siehe auch

[Auch](even.md)\
[Direktivenverweis](directives-reference.md)
