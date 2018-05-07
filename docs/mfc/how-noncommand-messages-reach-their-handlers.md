---
title: Wie nicht befehlsbasierte Meldungen ihre Handler erreichen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3999c74bf7a612acb998e7a044c12948d7679d9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Wie nicht befehlsbasierte Meldungen ihre Handler erreichen
Im Gegensatz zu den Befehlen standard-Windows-Meldungen werden nicht durch eine Kette von Befehlsziele weitergeleitet jedoch werden in der Regel vom Fenster, Windows die Nachricht sendet, verarbeitet. Das Fenster möglicherweise einem Hauptrahmenfenster, ein untergeordnetes MDI-Fenster, ein Standardsteuerelement, ein Dialogfeld, eine Sicht oder eine andere Art von untergeordnetes Fenster.  
  
 Zur Laufzeit, jede Windows-Fenster mit einem Fensterobjekt angefügt ist (direkt oder indirekt von abgeleiteten `CWnd`), das über eigene zugeordnete Meldung Karten- und Handler Funktionen verfügt. Das Framework verwendet die meldungszuordnung – wie bei einem Befehl – eingehende Nachrichten an Handler zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

