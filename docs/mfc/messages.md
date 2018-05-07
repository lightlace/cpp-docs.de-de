---
title: Nachrichten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abd49410f9982788e9403f0cb83ca8656473417d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="messages"></a>Mitteilungen
Die Nachrichtenschleife in der **ausführen** Memberfunktion der Klasse `CWinApp` ruft in der Warteschlange Nachrichten durch verschiedene Ereignisse generiert. Angenommen, klickt der Benutzer die Maus, sendet Windows mehrerer mausbezogenen Nachrichten wie z. B. `WM_LBUTTONDOWN` Wenn die linke Maustaste gedrückt wird und `WM_LBUTTONUP` Wenn die linke Maustaste losgelassen wird. Die Framework-Implementierung der Standardnachrichtenschleife einer Anwendung sendet die Nachricht an das entsprechende Fenster.  
  
 Die wichtigen Kategorien von Nachrichten werden in beschrieben [Meldungskategorien](../mfc/message-categories.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

