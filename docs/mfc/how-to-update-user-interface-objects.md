---
title: 'Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 422be3d80614c526c7e634d22a0930458e4b4e26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-update-user-interface-objects"></a>Gewusst wie: Aktualisieren von Benutzeroberflächenobjekten
So haben Menüelemente und Symbolleisten-Schaltflächen in der Regel mehr als einen Statuswert an. Ein Menüelement ist z. B. (abgeblendet) abgeblendet, wenn sie nicht im aktuellen Kontext verfügbar ist. Menüelemente können auch aktiviert oder deaktiviert sein. Eine Symbolleisten-Schaltfläche kann auch deaktiviert werden, wenn nicht verfügbar oder kann überprüft werden.  
  
 Wer aktualisiert den Status der diese Elemente, die netzwerkbedingungen ändern logisch zu programmieren, wenn ein Menüelement ein Befehls generiert, das von behandelt wird, z. B. ein Dokument, ist es sinnvoll, das Dokument, das das Menüelement aktualisiert haben. Das Dokument enthält wahrscheinlich die Informationen auf der das Update basiert.  
  
 Wenn mehrere Objekte der Benutzeroberfläche (z. B. ein Menüelement und eine Symbolleisten-Schaltfläche) über einen Befehl verfügt, werden beide an die gleichen Handlerfunktion weitergeleitet. Benutzeroberflächen-Aktualisierungscode für alle Objekte in einer einzelnen Stelle entsprechende Benutzeroberfläche gekapselt.  
  
 Das Framework bietet eine geeignete Benutzeroberfläche zum automatischen Aktualisieren von Benutzeroberflächenobjekten. Sie können auswählen, das Aktualisieren auf andere Weise, aber die bereitgestellte Schnittstelle ist effizient und einfach zu verwenden.  
  
 Die folgenden Themen erläutern die Verwendung von Aktualisierungshandler:  
  
-   [Wann müssen updatehandler aufgerufen werden](../mfc/when-update-handlers-are-called.md)  
  
-   [ON_UPDATE_COMMAND_UI-Makro](../mfc/on-update-command-ui-macro.md)  
  
-   [Die CCmdUI-Klasse](../mfc/the-ccmdui-class.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Menüs](../mfc/menus-mfc.md)

