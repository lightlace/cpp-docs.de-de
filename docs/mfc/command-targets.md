---
title: Befehlsziele
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: ed3d6a68967dc7f4244f887ae34760fdb99fa7f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388513"
---
# <a name="command-targets"></a>Befehlsziele

In der Abbildung [Befehle im Framework](../mfc/user-interface-objects-and-command-ids.md) zeigt die Verbindung zwischen einem Benutzeroberfläche-Objekt, z. B. ein Menüelement, und die Handlerfunktion, die vom Framework aufgerufen, um den Befehl ausführen, wenn das-Objekt geklickt wird.

Windows sendet Nachrichten ohne Command-Meldungen direkt an ein Fenster, dessen Handler für die Nachricht dann aufgerufen wird. Jedoch das Framework leitet Befehle, um eine Reihe von möglichen Objekten – "Befehlsziele" aufgerufen, von denen normalerweise einen Handler für den Befehl aufruft. Die Handlerfunktionen in gleicher Weise für sowohl Befehle als auch standard-Windows-Meldungen, unterscheiden sich jedoch die Mechanismen, mit dem sie aufgerufen werden, wie unter [wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)
