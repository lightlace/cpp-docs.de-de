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
ms.openlocfilehash: 5d7544d92d55ec4a1f6d15f3c1d4358970bf2deb
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928340"
---
# <a name="messages"></a>Mitteilungen
Die Nachrichtenschleife in der `Run` Memberfunktion der Klasse `CWinApp` ruft in der Warteschlange Nachrichten durch verschiedene Ereignisse generiert. Klickt der Benutzer die Maus, sendet Windows z. B. mehrere mausbezogenen Nachrichten, z. B. WM_LBUTTONDOWN, wenn die linke Maustaste gedrückt wird und WM_LBUTTONUP, wenn die linke Maustaste losgelassen wird. Die Framework-Implementierung der Standardnachrichtenschleife einer Anwendung sendet die Nachricht an das entsprechende Fenster.  
  
 Die wichtigen Kategorien von Nachrichten werden in beschrieben [Meldungskategorien](../mfc/message-categories.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

