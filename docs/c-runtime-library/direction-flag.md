---
title: Richtungsflag | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.flags
dev_langs: C++
helpviewer_keywords: direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0a43bac113c013ecb93f5b6e84aa2075a052f8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="direction-flag"></a>Richtungsflag
Das Richtungsflag ist ein spezielles CPU-Flag für Intel 80x86-Prozessoren. Dies gilt für alle Assemblyanweisungen, die das REP-Präfix (Wiederholung) verwenden, z.B. MOVS, MOVSD, MOVSW und andere. Adressen, die entsprechenden Anweisungen bereitgestellt werden, werden erhöht, wenn das Richtungsflag deaktiviert ist.  
  
 Die C-Laufzeitroutinen setzen voraus, dass das Richtungsflag deaktiviert ist. Wenn Sie andere Funktionen mit den C-Laufzeitfunktionen verwenden, müssen Sie sicherstellen, dass die anderen Funktionen das Richtungsflag unbeeinflusst lassen oder in seinem ursprünglichen Zustand wiederherstellen. Die Erwartung, dass das Richtungsflag beim Einstieg deaktiviert ist, macht den Laufzeitcode schneller und effizienter.  
  
 Die C-Laufzeitbibliotheksfunktionen wie Zeichenfolgenbearbeitungs- und Pufferbearbeitungsroutinen erwarten, dass das Richtungsflag deaktiviert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)