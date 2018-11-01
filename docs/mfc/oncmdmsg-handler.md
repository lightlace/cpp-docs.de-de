---
title: OnCmdMsg-Handler | Microsoft-Dokumentation
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
ms.openlocfilehash: 6691e4935d46b32bc8f433823888bb7f53a36890
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398832"
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg-Handler

Um das routing von Befehlen zu erreichen, das Ziel jedes Befehls ruft die `OnCmdMsg` Memberfunktion das Ziel des nächsten Befehls in der Sequenz. Befehl zielt verwenden `OnCmdMsg` zu bestimmen, ob sie einen Befehl behandeln können und um sie zu einem anderen Befehlsziel weiterzuleiten, wenn sie nicht verarbeitet werden können.

Kann jede Befehlsziel Klasse überschreiben, die `OnCmdMsg` Member-Funktion. Die Außerkraftsetzungen können jede Klasse Senden von Befehlen für ein bestimmtes Ziel für die nächsten. Ein Rahmenfenster, z. B. immer leitet Befehle für die aktuelle untergeordnete Fenster oder eine Sicht, wie in der Tabelle gezeigt [standardmäßige Befehlsweiterleitung](../mfc/command-routing.md).

Der Standardwert `CCmdTarget` Implementierung `OnCmdMsg` verwendet die meldungszuordnung der Befehlsziel Klasse für eine Handlerfunktion für jede Nachricht die Suche nach Erhalt des – auf die gleiche Weise, dass die standard-Nachrichten durchsucht werden. Wenn es sich um eine Übereinstimmung findet, wird den Handler. Meldungszuordnung Suche wird in erläutert [wie das Framework sucht Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md).

## <a name="see-also"></a>Siehe auch

[So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

