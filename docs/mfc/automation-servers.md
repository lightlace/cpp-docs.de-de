---
title: Automatisierungsserver | Microsoft Docs
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
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a33cf8113825804ac831b518e371c4150f2620ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="automation-servers"></a>Automatisierungsserver
Automatisierung ermöglicht es, für die Anwendung in einer anderen Anwendung implementierten Objekte zu bearbeiten oder Objekte verfügbar zu machen, damit sie bearbeitet werden können. Ein Automatisierungsserver ist eine Anwendung, die programmierbare Objekte (Automatisierungsobjekte genannt) für andere Anwendungen verfügbar macht (aufgerufen [Automatisierungsclients](../mfc/automation-clients.md)). Automatisierungsserver werden manchmal als Automatisierungskomponenten bezeichnet.  
  
 Verfügbarmachen von Automation-Objekten ermöglicht es Clients, die für bestimmte Vorgänge zu automatisieren, indem Sie direkten Zugriff auf die Objekte und Funktionalität der Server verfügbar macht. Verfügbarmachen von Objekten auf diese Weise ist nützlich, wenn Anwendungen Funktionen bereitstellen, die für andere Anwendungen hilfreich sind. Beispielsweise kann ein Textverarbeitungsprogramm seine Funktion zur Rechtschreibprüfung verfügbar machen, damit er von anderen Programmen verwendet werden können. Verfügbarmachen von Objekten ermöglicht es daher Herstellern, ihre Anwendungen Funktionalität mithilfe der vordefinierten Funktionen von anderen Anwendungen zu verbessern.  
  
 Diese Automatisierung-Objekte besitzen Eigenschaften und Methoden als ihre externen Schnittstelle. Eigenschaften werden die Attribute des Automatisierungsobjekts benannt. Eigenschaften sind z. B. der Datenmember einer C++-Klasse. Methoden sind Funktionen, die Automatisierungsobjekte ergänzen. Methoden sind wie die öffentliche Memberfunktionen einer C++-Klasse.  
  
> [!NOTE]
>  Obwohl die Eigenschaften wie die C++-Datenmember sind, sind sie nicht direkt zugegriffen werden kann. Um transparenten Zugriff zu gewährleisten, können Sie eine interne Variable in das Automatisierungsobjekt mit ein Paar von Memberfunktionen Get/Set richten Sie, um darauf zugreifen.  
  
 Durch Verfügbarmachen von Anwendungsfunktionen über eine gemeinsame, klar definierte Schnittstelle, kann Automatisierung zum Erstellen von Anwendungen in einer einzelnen allgemeinen Programmiersprache wie Microsoft Visual Basic statt in verschiedenen, anwendungsspezifische-Makro Sprachen.  
  
##  <a name="_core_support_for_automation_servers"></a>Unterstützung für Automatisierungsserver  
 Visual C++ und MFC-Frameworks bieten umfassende Unterstützung für Automatisierungsserver. Sie behandeln Großteil der Aufwand beim Erstellen eines Automatisierungsservers Sie Ihre bemühungen auf die Funktionalität der Anwendung konzentrieren können.  
  
 Das Framework principal Mechanismus für die Unterstützung der Automatisierung ist die Dispatchzuordnung, einen Satz von Makros, die in die Deklarationen und Aufrufe erforderlich, um Methoden und Eigenschaften für OLE verfügbar machen erweitert wird. Eine typische Dispatchzuordnung sieht wie folgt:  
  
 [!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]  
  
 Das Fenster "Eigenschaften" und die Klassenansicht unterstützen Dispatchzuordnungen verwalten. Wenn Sie eine neue Methode oder Eigenschaft einer Klasse hinzufügen, fügt Visual C++ eine entsprechende `DISP_FUNCTION` oder `DISP_PROPERTY` Makro mit Parametern, der angibt, den Klassennamen, die externen und internen Namen der Methode oder Eigenschaft und Datentypen.  
  
 Die **Klasse hinzufügen** Dialogfeld vereinfacht auch die Deklaration von Automatisierungsklassen und die Verwaltung von deren Eigenschaften und Vorgänge. Wenn Sie das Dialogfeld "Klasse hinzufügen" verwenden, um eine Klasse zu Ihrem Projekt hinzuzufügen, geben Sie ihre Basisklasse auf. Wenn die Basisklasse Automation zulässt, zeigt das Dialogfeld Klasse hinzufügen Steuerelemente, die Sie verwenden, um die festlegen, ob die neue Klasse Automatisierung unterstützen soll, ob es "OLE erstellt" (d. h., ob Objekte der Klasse auf eine Anforderung von einem COM-Client erstellt werden können) an. , und den externen Namen für den COM-Client verwenden.  
  
 Die **Klasse hinzufügen** Dialogfeld erstellt dann eine Klassendeklaration, einschließlich der entsprechenden Makros für die OLE-Funktionen angegeben haben. Darüber hinaus wird das Codegerüst für die Implementierung von Memberfunktionen der Klasse hinzugefügt.  
  
 Die MFC-Anwendung-Assistent vereinfacht die Schritte zum Abrufen Ihrer automatisierungsserveranwendung Deaktivieren von Grund auf neu. Bei Auswahl der **Automatisierung** Kontrollkästchen aus der **erweiterte Funktionen** Seite, die MFC-Anwendung-Assistent fügt Ihrer Anwendung `InitInstance` Funktionsaufrufe erforderlich, um die Automatisierung registrieren Objekte und führen Sie die Anwendung als Automatisierungsserver.  
  
### <a name="what-do-you-want-to-do"></a>Was möchten Sie tun  
  
-   [Erfahren Sie mehr über die Benutzeroberflächenautomatisierungs-clients](../mfc/automation-clients.md)  
  
-   [Erfahren Sie mehr über CCmdTarget-Klasse](../mfc/reference/ccmdtarget-class.md)  
  
-   [Erfahren Sie mehr über COleDispatchDriver-Klasse](../mfc/reference/coledispatchdriver-class.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenautomatisierung](../mfc/automation.md)   
 [MFC-Anwendungs-Assistent](../mfc/reference/mfc-application-wizard.md)

