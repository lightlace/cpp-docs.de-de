---
title: Befehlsziele
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: 3f3305e7b67f4c001861c79c76c3b43a0c5a8ef0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506879"
---
# <a name="command-targets"></a>Befehlsziele

In der Abbildung [Befehle im Framework](../mfc/user-interface-objects-and-command-ids.md) zeigt die Verbindung zwischen einem Benutzeroberfläche-Objekt, z. B. ein Menüelement, und die Handlerfunktion, die vom Framework aufgerufen, um den Befehl ausführen, wenn das-Objekt geklickt wird.

Windows sendet Nachrichten ohne Command-Meldungen direkt an ein Fenster, dessen Handler für die Nachricht dann aufgerufen wird. Jedoch das Framework leitet Befehle, um eine Reihe von möglichen Objekten – "Befehlsziele" aufgerufen, von denen normalerweise einen Handler für den Befehl aufruft. Die Handlerfunktionen in gleicher Weise für sowohl Befehle als auch standard-Windows-Meldungen, unterscheiden sich jedoch die Mechanismen, mit dem sie aufgerufen werden, wie unter [wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

