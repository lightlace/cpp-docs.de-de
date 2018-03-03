---
title: Standardbefehle | Microsoft Docs
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
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbdb763b2d7da04267a195e5d534da9528f2b74d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="standard-commands"></a>Standardbefehle
Das Framework definiert viele Standardbefehls-Nachrichten. Die IDs für diese Befehle werden in der Regel in der Form:  
  
 **ID_** *Quelle*_*Element*  
  
 wobei *Quelle* ist in der Regel ein Menünamen und *Element* ist ein Menüelement. Die Befehls-ID für den neuen Befehl im Menü Datei ist z. B. `ID_FILE_NEW`. Standardbefehle-IDs werden in der Dokumentation fett angezeigt. Programmiererdefinierte IDs werden in einer Schriftart angezeigt, die sich aus dem umgebenden Text unterscheidet.  
  
 Im folgenden finden eine Übersicht über einige der wichtigsten Befehle unterstützt:  
  
 *Befehle im Menü Datei*  
 Neu, öffnen Sie, schließen Sie, zu speichern, speichern unter, Seite einrichten, Drucker einrichten, drucken, Seitenansicht, beenden und zuletzt verwendete Dateien.  
  
 *Befehle im Menü Bearbeiten*  
 Löschen, löschen Wiederholen alle "," Kopieren "," Ausschneiden "," Suchen "," einfügen, ersetzen, Alles markieren, rückgängig machen und wiederholen.  
  
 *Befehle im Menü "Ansicht"*  
 Die Symbolleiste und Statusleiste.  
  
 *Befehle im Menü "Fenster"*  
 Neue, anordnen, überlappend, untereinander, nebeneinander und teilen.  
  
 *Befehle im Menü "Hilfe"*  
 Index mit der Hilfe zu erhalten, und über.  
  
 *OLE-Befehle (Menü "Bearbeiten")*  
 Neues Objekt, Verknüpfungen bearbeiten, verknüpfen, einfügen, einfügen und *Typename* Objekt (Verbbefehle).  
  
 Das Framework bietet verschiedene Ebenen der Unterstützung für diese Befehle. Einige Befehle sind nur als definierten Befehls-IDs unterstützt, während andere Benutzer mit gründliche-Implementierungen unterstützt werden. Beispielsweise implementiert das Framework der Befehl zum Öffnen auf das Menü Datei durch Erstellen eines neuen Dokumentobjekts, ein geöffnetes Dialogfenster anzeigen und öffnen und Lesen der Datei. Im Gegensatz dazu müssen Sie implementieren die Befehle im Menü Bearbeiten selbst seit Befehle wie **ID_EDIT_COPY** abhängig von der Art der Daten, die Sie kopieren.  
  
 Weitere Informationen zu unterstützten Befehle und die Ebene der bereitgestellte Implementierung finden Sie unter [technischen Hinweis 22](../mfc/tn022-standard-commands-implementation.md). Der standard-Befehle werden in der Datei AFXRES definiert. H.  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenobjekte und Befehls-IDs](../mfc/user-interface-objects-and-command-ids.md)

