---
title: "Meldungszuordnungen (MFC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Meldungszuordnungen [C++], MFC"
  - "Nachrichten [C++], Windows"
  - "MFC [C++], Meldungen"
  - "Windows-Nachrichten [C++], Meldungszuordnungen"
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Meldungszuordnungen (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im diesem Abschnitt der Referenz werden alle [Meldungszuordnungsmakros](../../mfc/reference/message-map-macros-mfc.md) und alle [CWnd](../../mfc/reference/cwnd-class.md)\-Meldungszuordnungseinträge zusammen mit den entsprechenden Memberfunktionsprototypen aufgeführt:  
  
|Kategorie \(Category\)|**Beschreibung**|  
|----------------------------|----------------------|  
|[WM\_COMMAND\-Meldungshandler](../../mfc/reference/wm-command-message-handler.md)|Verarbeitet **WM\_COMMAND** Meldungen, die durch Benutzermenüauswahlen oder Menüzugriffstasten generiert wurden.|  
|[Meldungshandler für Benachrichtigungen von untergeordneten Fenstern](../../mfc/reference/child-window-notification-message-handlers.md)|Verarbeiten Benachrichtigungen von untergeordneten Fenstern.|  
|[WM\_\-Meldungshandler](../../mfc/reference/handlers-for-wm-messages.md)|Verarbeiten **WM\_**\-Meldungen, z. B. `WM_PAINT`.|  
|[Benutzerdefinierte Meldungshandler](../../mfc/reference/user-defined-handlers.md)|Verarbeiten benutzerdefinierte Meldungen.|  
  
 \(Eine Erläuterung der Terminologie und der Konventionen, die in dieser Referenz verwendet werden, finden Sie unter [Verwenden des Meldungszuordnungs\-Querverweises](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).\)  
  
 Da Windows ein meldungsorientiertes Betriebssystem ist, bezieht sich ein Großteil der Programmierung für die Windows\-Umgebung auf die Verarbeitung von Meldungen.  Bei jeder Tastatureingabe bzw. jedem Mausklick wird eine Meldung an die Anwendung gesendet, die das Ereignis dann verarbeiten muss.  
  
 Microsoft Foundation Class\-Bibliothek bietet ein Programmiermodell, das für die meldungsbasierte Programmierung optimiert wurde.  In diesem Modell wird mithilfe von "Meldungszuordnungen" festgelegt, welche Funktionen die verschiedenen Meldungen für eine bestimmte Klasse verarbeiten.  Meldungszuordnungen enthalten ein oder mehrere Makros, die angeben, welche Meldungen von welchen Funktionen verarbeitet werden.  Eine Meldungszuordnung, die ein `ON_COMMAND`\-Makro enthält, kann z. B. wie folgt aussehen:  
  
 [!CODE [NVC_MFCMessageMaps#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageMaps#16)]  
  
 Das `ON_COMMAND`\-Makro wird zur Verarbeitung von Befehlsmeldungen verwendet, die von Menüs, Schaltflächen und Zugriffstasten generiert werden.  [Makros](../../mfc/reference/message-map-macros-mfc.md) sind verfügbar, um Folgendes zuzuordnen:  
  
## Windows\-Meldungen  
  
-   Steuerelementbenachrichtigungen  
  
-   Benutzerdefinierte Meldungen  
  
## Befehlsmeldungen  
  
-   Registrierte benutzerdefinierte Meldungen  
  
-   Meldungen zur Benutzeroberflächen\-Aktualisierung  
  
## Meldungsbereiche  
  
-   Befehle  
  
-   Aktualisierungshandlermeldungen  
  
-   Steuerelementbenachrichtigungen  
  
 Meldungszuordnungsmakros sind zwar wichtig, Sie müssen sie im Allgemeinen jedoch nicht direkt verwenden.  Dies liegt daran, dass das Eigenschaftenfenster automatisch Meldungszuordnungseinträge in den Quelldateien erstellt, wenn Sie damit Meldungsverarbeitungsfunktionen zu Meldungen zuordnen.  Zum Bearbeiten oder Hinzufügen eines Meldungszuordnungseintrags können Sie jederzeit das Eigenschaftenfenster verwenden.  
  
> [!NOTE]
>  Meldungszuordnungsbereiche werden vom Eigenschaftenfenster nicht unterstützt.  Sie müssen diese Meldungszuordnungseinträge selbst schreiben.  
  
 Meldungszuordnungen sind jedoch ein wichtiger Teil der Microsoft Foundation Class\-Bibliothek,  und Sie sollten ihre Funktionsweise kennen. Weitere Informationen finden Sie in der zur Verfügung stehenden Dokumentation.  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)