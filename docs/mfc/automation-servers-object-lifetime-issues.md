---
title: "Automatisierungsserver: Probleme mit der Objektlebensdauer | Microsoft Docs"
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
  - "Automatisierungsserver, Objektlebensdauer"
  - "Lebensdauer, Automatisierungsserver"
  - "Objekte [C++], Lebensdauer"
  - "Server, Lebensdauer der Automatisierung"
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Automatisierungsserver: Probleme mit der Objektlebensdauer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Automatisierungsclient ein OLE\-Element erstellt oder aktiviert wird, übergibt der Server den Client ein Zeiger auf dieses Objekt.  Der Client erstellt einen Verweis auf das Objekt durch einen Aufruf der OLE\-Funktion [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  Dieser Verweis ist gültig, bis der Client [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317). \(Die Clientanwendungen, die das OLE\-Klassen der Microsoft Foundation Class\-Bibliothek geschrieben werden, müssen diese Aufrufe, nicht auszuführen; das Framework dies jetzt.\) Das OLE\-System und Server selbst stellen möglicherweise Verweise auf das Objekt ein.  Ein Server sollte ein Objekt nicht zerstört, solange externe Verweise auf das Objekt bestehen bleiben.  
  
 Das Framework verwaltet eine interne die Anzahl von Verweisen auf jedem Serverobjekt bei, die von [CCmdTarget](../mfc/reference/ccmdtarget-class.md) abgeleitet wird.  Diese Anzahl wird aktualisiert, wenn ein Automatisierungsclient oder Entität einen Verweis auf das Objekt hinzugefügt oder freigibt.  
  
 Wenn der Verweiszähler 0 wird, ruft das Framework die virtuelle Funktion [CCmdTarget::OnFinalRelease](../Topic/CCmdTarget::OnFinalRelease.md) auf.  Die Standardimplementierung von diesem Funktionsaufrufe der Operator **löschen**, um dieses Objekts zu löschen.  
  
 Die Microsoft Foundation Class\-Bibliothek stellt zusätzliche Funktionen für das Steuern des Anwendungsverhaltens bereit, wenn Clients externe Verweise auf Objekte der Anwendung verfügen.  Außer dem Beibehalten einer Anzahl Verweise für jedes Objekt, behalten Server eine globale Anzahl aktive Objekte bei.  Die globalen Funktionen [AfxOleLockApp](../Topic/AfxOleLockApp.md) und [AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md) aktualisieren die Anzahl von aktiven Objekten.  Wenn diese Anzahl nicht 0 ist, wird die Anwendung nicht, wenn der Benutzer vom Abschluss Systemmenü oder Beendigung der im Menü Datei auswählt.  Stattdessen wird das Hauptfenster der Anwendung ausgeblendet \(aber nicht zerstört\) bis alle ausstehenden Clientanforderungen abgeschlossen wurden.  In der Regel werden `AfxOleLockApp` und `AfxOleUnlockApp` in den Konstruktoren sowie Destruktoren bzw. von Klassen dieser Unterstützungsautomatisierung aufgerufen.  
  
 Manchmal erzwingen Umstände den Server, um zu beenden, während ein Client noch einen Verweis auf ein Objekt verfügt.  Beispielsweise auf denen eine Ressource der Server abhängig ist, kann nicht verfügbar werden und Server führen, einen Fehler stößt.  Der Benutzer schließt auch ein Serverdokument, das Objekte enthält, auf die andere Anwendungen Verweise haben.  
  
 In [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] finden Sie unter `IUnknown::AddRef` und `IUnknown::Release`.  
  
## Siehe auch  
 [Automatisierungsserver](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)