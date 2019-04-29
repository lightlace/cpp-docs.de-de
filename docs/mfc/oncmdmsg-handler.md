---
title: OnCmdMsg-Handler
ms.date: 11/04/2016
f1_keywords:
- OnCmdMsg
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
ms.openlocfilehash: 6ed2e4c09e2fe413d29ad9953dbb8a03c106e86c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385296"
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg-Handler

Um das routing von Befehlen zu erreichen, das Ziel jedes Befehls ruft die `OnCmdMsg` Memberfunktion das Ziel des nächsten Befehls in der Sequenz. Befehl zielt verwenden `OnCmdMsg` zu bestimmen, ob sie einen Befehl behandeln können und um sie zu einem anderen Befehlsziel weiterzuleiten, wenn sie nicht verarbeitet werden können.

Kann jede Befehlsziel Klasse überschreiben, die `OnCmdMsg` Member-Funktion. Die Außerkraftsetzungen können jede Klasse Senden von Befehlen für ein bestimmtes Ziel für die nächsten. Ein Rahmenfenster, z. B. immer leitet Befehle für die aktuelle untergeordnete Fenster oder eine Sicht, wie in der Tabelle gezeigt [standardmäßige Befehlsweiterleitung](../mfc/command-routing.md).

Der Standardwert `CCmdTarget` Implementierung `OnCmdMsg` verwendet die meldungszuordnung der Befehlsziel Klasse für eine Handlerfunktion für jede Nachricht die Suche nach Erhalt des – auf die gleiche Weise, dass die standard-Nachrichten durchsucht werden. Wenn es sich um eine Übereinstimmung findet, wird den Handler. Meldungszuordnung Suche wird in erläutert [wie das Framework sucht Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md).

## <a name="see-also"></a>Siehe auch

[So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)
