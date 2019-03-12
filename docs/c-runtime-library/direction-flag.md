---
title: Richtungsflag
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
ms.openlocfilehash: ead32fa7f09e9dd98130855ecd87ba3b3d454ef5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740154"
---
# <a name="direction-flag"></a>Richtungsflag

Das Richtungsflag ist ein spezielles CPU-Flag für alle mit Intel x86 kompatiblen Prozessoren. Dies gilt für alle Assemblyanweisungen, die das REP-Präfix (Wiederholung) verwenden, z.B. MOVS, MOVSD, MOVSW und andere. Adressen, die entsprechenden Anweisungen bereitgestellt werden, werden erhöht, wenn das Richtungsflag deaktiviert ist.

Die C-Laufzeitroutinen setzen voraus, dass das Richtungsflag deaktiviert ist. Wenn Sie andere Funktionen mit den C-Laufzeitfunktionen verwenden, müssen Sie sicherstellen, dass die anderen Funktionen das Richtungsflag unbeeinflusst lassen oder in seinem ursprünglichen Zustand wiederherstellen. Die Erwartung, dass das Richtungsflag beim Einstieg deaktiviert ist, macht den Laufzeitcode schneller und effizienter.

Die C-Laufzeitbibliotheksfunktionen wie Zeichenfolgenbearbeitungs- und Pufferbearbeitungsroutinen erwarten, dass das Richtungsflag deaktiviert ist.

## <a name="see-also"></a>Siehe auch

[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)
