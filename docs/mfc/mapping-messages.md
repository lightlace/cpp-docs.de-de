---
title: Zuordnen von Meldungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f521145599a3d734a22dd3b2707ad4dd16df8e80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345985"
---
# <a name="mapping-messages"></a>Zuordnen von Meldungen
Jede Frameworkklasse, die Nachrichten oder Befehle empfangen kann hat ihre eigene "meldungszuordnung". Das Framework verwendet meldungszuordnungen Verbindung von Meldungen und Befehle zu Ihren jeweiligen Handlerfunktionen. Jede Klasse abgeleitete `CCmdTarget` eine meldungszuordnung haben können. Andere Artikel meldungszuordnungen ausführlich erläutert und beschrieben, wie sie verwendet.  
  
 Trotz der Name "meldungszuordnung," Nachricht, die Handhabung von Zuordnungen sowohl Meldungen und Befehle – alle drei Kategorien von Nachrichten in aufgeführten [Meldungskategorien](../mfc/message-categories.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

