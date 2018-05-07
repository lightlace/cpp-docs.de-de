---
title: OnCmdMsg-Handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnCmdMsg
dev_langs:
- C++
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0657b05619a966ed171630d00adcd9303af7e18b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg-Handler
Um das routing von Befehlen zu erreichen, jede Befehlsziel Ruft die `OnCmdMsg` Memberfunktion, der das Ziel des Befehls in der Sequenz. Befehl zielt auf die Verwendung `OnCmdMsg` um zu bestimmen, ob sie einen Befehl verarbeiten können und auf einem anderen Befehlsziel weiterzuleiten, wenn sie nicht behandeln können.  
  
 Jede Befehlsziel Klasse überschreibt möglicherweise die `OnCmdMsg` Memberfunktion. Die Außerkraftsetzungen können jede Klasse Route-Befehle für ein bestimmtes Ziel weiter. Einem Rahmenfenster z. B. immer leitet Befehle auf seine aktuellen untergeordneten Fensters oder Sicht, in der Tabelle dargestellten [standardmäßige Befehlsweiterleitung](../mfc/command-routing.md).  
  
 Die Standardeinstellung `CCmdTarget` Implementierung von `OnCmdMsg` verwendet die meldungszuordnung der Befehlsziel Klasse für eine Ereignishandler-Funktion für jede Befehlsnachricht die Suche nach Empfang – in die gleiche Weise wie standard-Nachrichten durchsucht werden. Wenn eine Übereinstimmung gefunden wird, ruft er den Handler. Meldungszuordnung suchen finden [wie das Framework sucht Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md).  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

