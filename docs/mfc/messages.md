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
ms.workload: cplusplus
ms.openlocfilehash: d03eed129fd5a2a7c73f7c7948cb766813f63c34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="messages"></a>Mitteilungen
Die Nachrichtenschleife in der **ausführen** Memberfunktion der Klasse `CWinApp` ruft in der Warteschlange Nachrichten durch verschiedene Ereignisse generiert. Angenommen, klickt der Benutzer die Maus, sendet Windows mehrerer mausbezogenen Nachrichten wie z. B. `WM_LBUTTONDOWN` Wenn die linke Maustaste gedrückt wird und `WM_LBUTTONUP` Wenn die linke Maustaste losgelassen wird. Die Framework-Implementierung der Standardnachrichtenschleife einer Anwendung sendet die Nachricht an das entsprechende Fenster.  
  
 Die wichtigen Kategorien von Nachrichten werden in beschrieben [Meldungskategorien](../mfc/message-categories.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

