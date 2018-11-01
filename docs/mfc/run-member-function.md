---
title: Ausführen von Memberfunktion
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: 8e6e74b8f0fd62f96d6d846bbba867f9189550ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666855"
---
# <a name="run-member-function"></a>Ausführen von Memberfunktion

Eine Framework-Anwendung verbringt die meiste Zeit in die [ausführen](../mfc/reference/cwinapp-class.md#run) Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md). Nach der Initialisierung `WinMain` Aufrufe `Run` die Nachrichtenschleife zu verarbeiten.

`Run` durchläuft eine Meldungsschleife, überprüfen die Nachrichtenwarteschlange für verfügbaren Nachrichten. Wenn eine Nachricht verfügbar ist `Run` für die Aktion sendet. Wenn keine Nachrichten verfügbar sind, was häufig ist "true" `Run` Aufrufe `OnIdle` möchten Sie alle Leerlauf-Ablaufzeitpunkt Verarbeitungsschritte, die Sie oder das Framework benötigen. Wenn keine Nachrichten und keine leerlaufverarbeitung Sie vorhanden sind, wartet die Anwendung erst etwas passiert. Wenn die Anwendung beendet wird, `Run` Aufrufe `ExitInstance`. In der Abbildung in [OnIdle-Memberfunktion](../mfc/onidle-member-function.md) zeigt die Abfolge der Aktionen in der Nachrichtenschleife.

Die nachrichtenverteilung, hängt von der Art der Nachricht ab. Weitere Informationen finden Sie unter [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md).

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
