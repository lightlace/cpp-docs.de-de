---
title: Befehl Ziele | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb8d2bff69e95a089827c85ade6dc4bcd67eb7ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-targets"></a>Befehlsziele
Die Abbildung [Befehle im Framework](../mfc/user-interface-objects-and-command-ids.md) zeigt die Verbindung zwischen einer Benutzeroberfläche-Objekt, z. B. ein Menüelement, und die Ereignishandler-Funktion, die vom Framework aufgerufen, um den Befehl durchzuführen, wenn das Objekt geklickt wird.  
  
 Windows sendet Nachrichten, die nicht Command-Meldungen direkt in einem Fenster sind, deren Handler für die Nachricht dann aufgerufen wird. Allerdings das Framework leitet Befehle, um eine Reihe von Objekten geeignet – "Befehlsziele" aufgerufen, von denen normalerweise Ruft einen Handler für den Befehl. Die Handlerfunktionen funktionieren ebenso für Befehle und standard-Windows-Meldungen, aber die Mechanismen, die mit dem Namen unterscheiden, wie in beschrieben [wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

