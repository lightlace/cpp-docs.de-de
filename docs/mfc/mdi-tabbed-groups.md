---
title: "MDI-Gruppen im Registerkartenformat | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mdi, Gruppen im Registerkartenformat"
  - "Gruppen im Registerkartenformat"
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# MDI-Gruppen im Registerkartenformat
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die mit den im Gruppenfunktion des Multiple Document Interface \(MDI\) aktiviert Multiple Document Interface \(MDI\)\- Anwendungen, eine oder mehrere Fenster in Registerform \(oder Gruppen der Fenster im Registerkartenformat, bekannt als *Gruppen im Registerkartenformat*\) im MDI\-Clientbereich anzuzeigen.  Die Fenster in Registerform können vertikal oder horizontal ausgerichtet werden.  Wenn eine Anwendung mehr als eine MDI mit den versehene Gruppe hostet, werden die Gruppen von Splittern getrennt.  
  
## Features  
 Die die folgenden Funktionen von MDI mit als Registerkarten Gruppen:  
  
-   Eine Anwendung kann dynamisch erstellen Fenster im Registerkartenformat.  
  
-   Eine Anwendung kann horizontal oder vertikal ausrichten Fenster im Registerkartenformat.  
  
-   Gruppen der Fenster im Registerkartenformat werden von den Splittern getrennt.  Der Benutzer kann die Größe Gruppen im Registerkartenformat, indem den Splitter verwendet.  
  
-   Der Benutzer kann zwischen Gruppen einzelne Registerkarten ziehen.  
  
-   Der Benutzer kann einzelne Registerkarten ziehen, um neue Gruppen zu erstellen.  
  
-   Der Benutzer kann Registerkarten verschieben oder neue Gruppen erstellen, indem ein Kontextmenü verwendet.  
  
-   Eine Anwendung kann das Layout von Fenstern speichern und laden im Registerkartenformat.  
  
-   Eine Anwendung kann die Liste von MDI\-Dokumenten speichern und laden.  
  
-   Eine Anwendung kann auf einzelne Gruppen Zugriff im Registerkartenformat und die Parameter ändern.  
  
### Mithilfe der MDI mit als Registerkarten Gruppen  
 Die die folgenden Aufgaben, die im Allgemeinen mit MDI mit als Registerkarten Gruppen ausgeführt werden:  
  
-   So MDI zu aktivieren angegebene Gruppen für ein Hauptrahmenfenster, aufrufen mit den [CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md).  Der zweite Parameter dieser Methode ist eine Instanz der Klasse `CMDITabInfo`.  Sie können die Standardparameter verwenden oder ändern, bevor Sie `CMDIFrameWndEx::EnableMDITabbedGroups` aufrufen.  
  
-   Um die Eigenschaften einer MDI mit als Registerkarten Gruppe zur Laufzeit ändern, ein `CMDITabInfo`\-Objekt erstellen oder ändern und `CMDIFrameWndEx::EnableMDITabbedGroups` erneut aufrufen  
  
-   Um eine Liste von MDI abzurufen angegebene Fenster, mit den `CMDIFrameWndEx::GetMDITabGroups` aufrufen.  
  
-   Um ein neues MDI erstellen angegebene Gruppe neben einer aktiven Gruppe im Registerkartenformat, rufen `CMDIFrameWndEx::MDITabNewGroup` mit den.  
  
-   Um den Eingabefokus zum vorherigen oder nächsten Fenster einer Gruppe zu verschieben im Registerkartenformat, rufen Sie `CMDIFrameWndEx::MDITabMoveToNextGroup` auf.  
  
-   So bestimmen Sie, ob ein Fenster ein Member eines MDI mit als Registerkarten Gruppenaufrufs `CMDIFrameWndEx::IsMemberOfMDITabGroup` ist.  
  
-   So bestimmen Sie, ob MDI\-Registerkarten oder MDI mit den versehene Gruppen für ein Hauptrahmenfenster aktiviert werden, rufen Sie `CMDIFrameWndEx::AreMDITabs`.  So bestimmen nur ob MDI mit den Gruppen versehene aktiviert werden, rufen Sie `CMDIFrameWndEx::IsMDITabbedGroup`.  
  
-   Um ein Kontextmenü anzuzeigen wenn der Benutzer auf eine Registerkarte klicken oder in einer MDI mit anderen als Registerkarten Gruppe zieht, überschreiben Sie `CMDIFrameWndEx::OnShowMDITabContextMenu` in von `CMDIFrameWndEx` abgeleiteten Klasse.  Wenn Sie diese Methode nicht implementieren, wird die Anwendung nicht das Kontextmenü angezeigt.  
  
-   Um das Layout von MDI zu speichern angegebene Gruppen in einer Anwendung mit den `CMDIFrameWndEx::SaveMDIState`, aufrufen.  So vorher gespeichertes MDI zu laden angegebene Gruppenprofil, rufen `CMDIFrameWndEx::LoadMDIState` mit den.  Sie können diese Methoden aufrufen, um die Liste der geöffneten Dokumenten in einer MDI\-Anwendung zu laden oder zu speichern.  Weitere Informationen über Einsparungs\- und Ladenmdi Zustand, finden Sie unter [CMDIFrameWndEx::LoadMDIState](../Topic/CMDIFrameWndEx::LoadMDIState.md).  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [CMDIFrameWndEx\-Klasse](../mfc/reference/cmdiframewndex-class.md)   
 [CMDIChildWndEx\-Klasse](../mfc/reference/cmdichildwndex-class.md)   
 [CMDITabInfo Class](../mfc/reference/cmditabinfo-class.md)