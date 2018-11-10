---
title: Richtungsflag
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
ms.openlocfilehash: ae2936c4e07a434a49d931ed60a7d7dee74e3177
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534877"
---
# <a name="direction-flag"></a>Richtungsflag

Das Richtungsflag ist ein spezielles CPU-Flag für Intel 80x86-Prozessoren. Dies gilt für alle Assemblyanweisungen, die das REP-Präfix (Wiederholung) verwenden, z.B. MOVS, MOVSD, MOVSW und andere. Adressen, die entsprechenden Anweisungen bereitgestellt werden, werden erhöht, wenn das Richtungsflag deaktiviert ist.

Die C-Laufzeitroutinen setzen voraus, dass das Richtungsflag deaktiviert ist. Wenn Sie andere Funktionen mit den C-Laufzeitfunktionen verwenden, müssen Sie sicherstellen, dass die anderen Funktionen das Richtungsflag unbeeinflusst lassen oder in seinem ursprünglichen Zustand wiederherstellen. Die Erwartung, dass das Richtungsflag beim Einstieg deaktiviert ist, macht den Laufzeitcode schneller und effizienter.

Die C-Laufzeitbibliotheksfunktionen wie Zeichenfolgenbearbeitungs- und Pufferbearbeitungsroutinen erwarten, dass das Richtungsflag deaktiviert ist.

## <a name="see-also"></a>Siehe auch

[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)