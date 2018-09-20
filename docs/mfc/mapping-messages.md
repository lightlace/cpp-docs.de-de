---
title: Zuordnen von Meldungen | Microsoft-Dokumentation
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
ms.openlocfilehash: 7324da5eaff15d240cabbaede2c2982021361257
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410978"
---
# <a name="mapping-messages"></a>Zuordnen von Meldungen

Jedes Framework-Klasse, die Nachrichten oder Befehle empfangen kann verfügt über einen eigenen "Nachricht"zuordnen. Das Framework verwendet meldungszuordnungen Verbindung von Meldungen und Befehle mit Ihren jeweiligen Handlerfunktionen. Jede aus der Klasse abgeleitete `CCmdTarget` eine meldungszuordnung haben. Weitere Artikel meldungszuordnungen im Detail erläutert und beschrieben, wie Sie diese verwenden.

Trotz der Name "meldungszuordnung," Nachricht, die Handhabung von Zuordnungen sowohl Meldungen und Befehle – alle drei Kategorien von Nachrichten, die in aufgeführten [Meldungskategorien](../mfc/message-categories.md).

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

