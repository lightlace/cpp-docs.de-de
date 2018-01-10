---
title: Wie nicht befehlsbasierte Meldungen ihre Handler erreichen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33d0d65c9916cfc571ecfd623138938c0c883ba5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Wie nicht befehlsbasierte Meldungen ihre Handler erreichen
Im Gegensatz zu den Befehlen standard-Windows-Meldungen werden nicht durch eine Kette von Befehlsziele weitergeleitet jedoch werden in der Regel vom Fenster, Windows die Nachricht sendet, verarbeitet. Das Fenster möglicherweise einem Hauptrahmenfenster, ein untergeordnetes MDI-Fenster, ein Standardsteuerelement, ein Dialogfeld, eine Sicht oder eine andere Art von untergeordnetes Fenster.  
  
 Zur Laufzeit, jede Windows-Fenster mit einem Fensterobjekt angefügt ist (direkt oder indirekt von abgeleiteten `CWnd`), das über eigene zugeordnete Meldung Karten- und Handler Funktionen verfügt. Das Framework verwendet die meldungszuordnung – wie bei einem Befehl – eingehende Nachrichten an Handler zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

