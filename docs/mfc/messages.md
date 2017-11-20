---
title: Nachrichten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1766075663ef924e9a731169a09c3d396d643d2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="messages"></a>Mitteilungen
Die Nachrichtenschleife in der **ausführen** Memberfunktion der Klasse `CWinApp` ruft in der Warteschlange Nachrichten durch verschiedene Ereignisse generiert. Angenommen, klickt der Benutzer die Maus, sendet Windows mehrerer mausbezogenen Nachrichten wie z. B. `WM_LBUTTONDOWN` Wenn die linke Maustaste gedrückt wird und `WM_LBUTTONUP` Wenn die linke Maustaste losgelassen wird. Die Framework-Implementierung der Standardnachrichtenschleife einer Anwendung sendet die Nachricht an das entsprechende Fenster.  
  
 Die wichtigen Kategorien von Nachrichten werden in beschrieben [Meldungskategorien](../mfc/message-categories.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

