---
title: Ausführen von Memberfunktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 446b1b6fc2a5265e2c4eb8a608ff8b4f0028c57d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408231"
---
# <a name="run-member-function"></a>Ausführen von Memberfunktion

Eine Framework-Anwendung verbringt die meiste Zeit in die [ausführen](../mfc/reference/cwinapp-class.md#run) Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md). Nach der Initialisierung `WinMain` Aufrufe `Run` die Nachrichtenschleife zu verarbeiten.

`Run` durchläuft eine Meldungsschleife, überprüfen die Nachrichtenwarteschlange für verfügbaren Nachrichten. Wenn eine Nachricht verfügbar ist `Run` für die Aktion sendet. Wenn keine Nachrichten verfügbar sind, was häufig ist "true" `Run` Aufrufe `OnIdle` möchten Sie alle Leerlauf-Ablaufzeitpunkt Verarbeitungsschritte, die Sie oder das Framework benötigen. Wenn keine Nachrichten und keine leerlaufverarbeitung Sie vorhanden sind, wartet die Anwendung erst etwas passiert. Wenn die Anwendung beendet wird, `Run` Aufrufe `ExitInstance`. In der Abbildung in [OnIdle-Memberfunktion](../mfc/onidle-member-function.md) zeigt die Abfolge der Aktionen in der Nachrichtenschleife.

Die nachrichtenverteilung, hängt von der Art der Nachricht ab. Weitere Informationen finden Sie unter [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md).

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
