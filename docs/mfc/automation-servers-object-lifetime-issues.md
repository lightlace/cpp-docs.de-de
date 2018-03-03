---
title: 'Automatisierungsserver: Probleme mit der Objektlebensdauer | Microsoft Docs'
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
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c9fab7af74dee482c5e8dffb327da9c037796fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="automation-servers-object-lifetime-issues"></a>Automatisierungsserver: Probleme mit der Objektlebensdauer
Wenn ein Automatisierungsclient erstellt oder ein OLE-Element aktiviert, übergibt der Server, der diesem Objekt einen Zeiger an dem Client. Der Client stellt einen Verweis auf das Objekt durch einen Aufruf an die OLE-Funktion her [IUnknown:: AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379). Dieser Verweis gültig ist, bis der Client ruft [IUnknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317). (Clientanwendungen, die geschrieben werden, mit der Microsoft Foundation Class Library-OLE-Klassen müssen diese Aufrufe nicht; das Framework ermöglicht dies.) Das OLE-System und der Server selbst möglicherweise Verweise auf das Objekt festlegen. Ein Server sollte kein Objekt zu zerstören als externe Verweise auf das Objekt gültig bleiben.  
  
 Das Framework verwaltet eine interne Anzahl die Anzahl der Verweise auf alle Serverobjekt, das von abgeleiteten [CCmdTarget](../mfc/reference/ccmdtarget-class.md). Diese Anzahl wird aktualisiert, wenn ein Automatisierungsclient oder andere Entität hinzufügt oder einen Verweis auf das Objekt frei.  
  
 Wenn der Verweiszähler 0 erreicht, wird das Framework Ruft die virtuelle Funktion [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease). Ruft die standardmäßige Implementierung dieser Funktion die **löschen** Operator, um das Objekt gelöscht werden.  
  
 Die Microsoft Foundation Class-Bibliothek bietet zusätzliche Funktionen zum Steuern des Anwendungsverhaltens aus, wenn externe Clients Verweise auf die Anwendung Objekte haben. Neben der Wartung Anzahl der Verweise auf jedes Objekt, Wartung von Servern eine globale Anzahl von aktiven Objekten. Die globalen Funktionen [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) und [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) die Anwendung die Anzahl von aktiven Objekten zu aktualisieren. Wenn diese Zahl ungleich NULL ist, wird die Anwendung nicht beendet, wenn der Benutzer aus dem Systemmenü oder über das Menü Datei beenden schließen auswählt. Stattdessen ist im Hauptfenster der Anwendung ausgeblendet (jedoch nicht zerstört) bis alle anstehenden Anforderungen abgeschlossen wurden. In der Regel `AfxOleLockApp` und `AfxOleUnlockApp` werden aufgerufen, Klassen, die Unterstützung der Automatisierung in den Konstruktoren und Destruktoren.  
  
 In einigen Fällen erzwingen Umständen den Server, beenden, während ein Client noch einen Verweis auf ein Objekt hat. Z. B. möglicherweise eine Ressource, von der der Server abhängig ist, nicht verfügbar, wenn der Server einen Fehler auftritt. Der Benutzer kann auch Serverdokument schließen, die Objekte enthält, auf die anderen Anwendungen Verweise haben.  
  
 In der Windows-SDK finden Sie unter `IUnknown::AddRef` und `IUnknown::Release`.  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisierungsserver](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)

