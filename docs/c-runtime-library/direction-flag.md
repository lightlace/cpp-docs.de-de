---
title: Richtungsflag | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3737304d2443b4f67f00a03e23a0529ad5bcbfe3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="direction-flag"></a>Richtungsflag
Das Richtungsflag ist ein spezielles CPU-Flag für Intel 80x86-Prozessoren. Dies gilt für alle Assemblyanweisungen, die das REP-Präfix (Wiederholung) verwenden, z.B. MOVS, MOVSD, MOVSW und andere. Adressen, die entsprechenden Anweisungen bereitgestellt werden, werden erhöht, wenn das Richtungsflag deaktiviert ist.  
  
 Die C-Laufzeitroutinen setzen voraus, dass das Richtungsflag deaktiviert ist. Wenn Sie andere Funktionen mit den C-Laufzeitfunktionen verwenden, müssen Sie sicherstellen, dass die anderen Funktionen das Richtungsflag unbeeinflusst lassen oder in seinem ursprünglichen Zustand wiederherstellen. Die Erwartung, dass das Richtungsflag beim Einstieg deaktiviert ist, macht den Laufzeitcode schneller und effizienter.  
  
 Die C-Laufzeitbibliotheksfunktionen wie Zeichenfolgenbearbeitungs- und Pufferbearbeitungsroutinen erwarten, dass das Richtungsflag deaktiviert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)