---
title: Zuordnen von Meldungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message maps [MFC], about message maps
- mappings [MFC], commands
- commands [MFC], mapping
- command mapping [MFC]
- message handling [MFC], connecting to handler functions
- commands [MFC], connecting to handler functions
- mappings [MFC], messages
- messages [MFC], mapping
ms.assetid: 996f0652-0698-4b8c-b893-cdaa836d9d0f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 03a07410f6decb6497312a9f04b421bed367dfad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="mapping-messages"></a>Zuordnen von Meldungen
Jede Frameworkklasse, die Nachrichten oder Befehle empfangen kann hat ihre eigene "meldungszuordnung". Das Framework verwendet meldungszuordnungen Verbindung von Meldungen und Befehle zu Ihren jeweiligen Handlerfunktionen. Jede Klasse abgeleitete `CCmdTarget` eine meldungszuordnung haben können. Andere Artikel meldungszuordnungen ausführlich erläutert und beschrieben, wie sie verwendet.  
  
 Trotz der Name "meldungszuordnung," Nachricht, die Handhabung von Zuordnungen sowohl Meldungen und Befehle – alle drei Kategorien von Nachrichten in aufgeführten [Meldungskategorien](../mfc/message-categories.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

