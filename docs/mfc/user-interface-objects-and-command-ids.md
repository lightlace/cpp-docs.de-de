---
title: "Benutzeroberflächenobjekte und Befehls-IDs | Microsoft Docs"
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
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e085c6d9e4d030c8db44e11e570ffa1033abee35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="user-interface-objects-and-command-ids"></a>Benutzeroberflächenobjekte und Befehls-IDs
Menüelemente, Symbolleistenschaltflächen und Tastenkombinationen sind "Benutzeroberflächenobjekten" kann beim Generieren von Befehlen. Jedes dieser Objekte der Benutzeroberfläche verfügt über eine ID. Sie ordnen ein Benutzeroberflächen-Objekt mit einem Befehl durch Zuweisen der gleichen ID des Objekts und der Befehl. Wie in beschrieben [Nachrichten](../mfc/messages.md), Befehle als spezielle Nachrichten implementiert werden. Die Abbildung "Befehle im Framework" unten zeigt, wie das Framework Befehle verwaltet. Wenn ein Objekt der Benutzeroberfläche generiert einen Befehl wie z. B. `ID_EDIT_CLEAR_ALL`, eines der Objekte in der Anwendung behandelt den Befehl – in der folgenden Abbildung dargestellt, des Document-Objekts `OnEditClearAll` Funktion wird über die Dokumentstruktur Nachricht aufgerufen.  
  
 ![Befehle im Framework](../mfc/media/vc385p1.gif "vc385p1")  
Befehle im Framework  
  
 Die Abbildung "Befehl aktualisieren im Framework" unten zeigt, wie MFC Benutzeroberflächenobjekte wie Menüelemente und Symbolleisten-Schaltflächen aktualisiert. Bevor Sie ein Dropdownmenü oder während der Leerlaufschleife im Fall von Schaltflächen der Symbolleiste, leitet MFC einen Update-Befehl. In der folgenden Abbildung ruft das Document-Objekt die Update-Befehlshandler `OnUpdateEditClearAll`, zum Aktivieren oder deaktivieren das Benutzeroberflächen-Objekt.  
  
 ![Befehl in das Framework aktualisieren](../mfc/media/vc385p2.png "vc385p2")  
Befehlsaktualisierung im Framework  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

