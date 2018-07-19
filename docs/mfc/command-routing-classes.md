---
title: Klassen zur Befehlsweiterleitung Befehl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.command
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3e05046ac6754dd585bb1fbf51420ef862af7be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341961"
---
# <a name="command-routing-classes"></a>Klassen zur Befehlsweiterleitung
Wie der Benutzer mit der Anwendung interagiert, indem Sie Menüs oder Steuerleiste Schaltflächen mit der Maus auswählen, sendet die Anwendung Nachrichten aus dem betroffenen Benutzeroberflächen-Objekt in eine entsprechende Befehlsziel Objekt an. Befehlszielklassen abgeleitet `CCmdTarget` enthalten [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), und die Klassen, die von ihnen abgeleitet. Das Framework unterstützt die automatische Befehlsrouting, sodass Befehle von der derzeit aktiven in der Anwendung am besten geeignete Objekt behandelt werden können.  
  
 Ein Objekt der Klasse `CCmdUI` an Ihre Befehlsziele Aktualisierungsbefehl UI übergeben wird ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) Handler, die den Zustand der Benutzeroberfläche für einen bestimmten Befehl aktualisieren können (z. B. zum Überprüfen oder entfernen die Überprüfung von Menüelementen). Sie rufen Memberfunktionen der `CCmdUI` Objekt, das den Zustand des UI-Objekts zu aktualisieren. Dieser Vorgang entspricht dem, ob das UI-Objekt, das einen bestimmten Befehl zugeordnet, ein Menüelement oder eine Schaltfläche oder beides ist.  
  
 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
 Dient als Basisklasse für alle Objektklassen, die empfangen und auf Nachrichten reagieren können.  
  
 [CCmdUI](../mfc/reference/ccmdui-class.md)  
 Stellt eine programmgesteuerte Schnittstelle für das Aktualisieren von Benutzeroberflächenobjekten z. B. Steuerleiste Schaltflächen oder Menüelemente bereit. Das Zielobjekt Befehl aktiviert, deaktiviert, überprüft und/oder löscht das Benutzeroberflächen-Objekt mit diesem Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

