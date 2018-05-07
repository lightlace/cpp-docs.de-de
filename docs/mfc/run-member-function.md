---
title: Ausführen von Memberfunktion | Microsoft Docs
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
ms.openlocfilehash: be1d7d90b4c13a23e2e3456e7371abbae61be4e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="run-member-function"></a>Ausführen von Memberfunktion
Framework-Anwendung verbringt die meiste Zeit in die [ausführen](../mfc/reference/cwinapp-class.md#run) Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md). Nach der Initialisierung können `WinMain` Aufrufe **ausführen** die Nachrichtenschleife zu verarbeiten.  
  
 **Führen Sie** durchläuft eine Nachrichtenschleife, überprüfen die Nachrichtenwarteschlange für verfügbaren Nachrichten. Wenn eine Nachricht verfügbar ist, wird **ausführen** Behandlung für die Aktion. Wenn keine Nachrichten verfügbar sind, also häufig "true" **ausführen** Aufrufe `OnIdle` zu jeder Zeit im Leerlauf Verarbeitungsvorgänge ausführen, das Sie oder das Framework ggf. ausgeführt. Wenn keine Nachrichten und keine leerlaufverarbeitung Vorgehensweise vorhanden sind, wartet die Anwendung erst etwas passiert. Wenn die Anwendung beendet wird, **ausführen** Aufrufe `ExitInstance`. Die Abbildung im [OnIdle-Memberfunktion](../mfc/onidle-member-function.md) veranschaulicht die Abfolge von Aktionen in der Nachrichtenschleife.  
  
 Die nachrichtenverteilung, hängt von der Art der Nachricht ab. Weitere Informationen finden Sie unter [, Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
