---
title: ALIGN (MASM)
ms.date: 01/02/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: eb42b1952b3fd59438f0dd4c29d48c91c4d8864d
ms.sourcegitcommit: cce52b2232b94ce8fd8135155b86e2d38a4e4562
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54031225"
---
# <a name="align-masm"></a>ALIGN (MASM)

Die **AUSRICHTEN** Richtlinie entspricht, der nächsten Datenelement oder der Anweisung auf eine Adresse, die ein Vielfaches von als Parameter. Der Parameter muss eine Potenz von 2 sein (z. B. 1, 2, 4 und So weiter), kleiner oder gleich der Segment-Ausrichtung.

## <a name="syntax"></a>Syntax

> ALIGN [[*Anzahl*]]

## <a name="remarks"></a>Hinweise

Die **AUSRICHTEN** -Direktive ermöglicht Ihnen die Angabe der Anfangsoffset für ein Datenelement oder einer Anweisung. Ausgerichtete Daten können Leistung auf Kosten der Platz vergeudet zwischen Datenelementen verbessern. Wenn von Datenzugriffen an Grenzen sind, die in Cachezeilen passen können die erheblichen leistungsverbesserungen in angezeigt werden. Greift auf an natürlichen Begrenzungen für systemeigene Typen bedeutet weniger Zeit in die interne Hardware generierungswert Microcode.

Die Notwendigkeit von ausgerichteten Anweisungen kommt selten vor, bei modernen Prozessoren, die eine flache Adressierungsmodell verwenden, aber möglicherweise in älterem Code für andere Adressierung Modelle für Sprungziele erforderlich.

Wenn Daten ausgerichtet sind, wird der übersprungene Platz mit Nullen aufgefüllt. Wenn Anweisungen ausgerichtet sind, wird der übersprungene Speicherplatz mit NOP-Anweisungen geeignete Größe gefüllt.

## <a name="see-also"></a>Siehe auch

[EVEN](even.md)<br/>
[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>