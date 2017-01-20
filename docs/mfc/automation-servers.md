---
title: "Automatisierungsserver"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automatisierungsserver"
  - "COM-Komponenten, Automatisierungsserver"
  - "Dispatchzuordnungen, Automatisierungsserver"
  - "Server, Automatisierung"
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Automatisierungsserver
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Automatisierung ermöglicht es, sodass die Anwendung die Objekte behandelt, die in einer anderen Anwendung implementiert werden oder Objekte verfügbar gemacht werden, sodass sie bearbeitet werden.  Ein Automatisierungsserver ist eine Anwendung, die die Objekte \(programmierbaren aufgerufen Automatisierungsobjekte\) anderen Anwendungen verfügbar macht \( [Automatisierungsclients](../mfc/automation-clients.md)\) aufgerufen.  Automatisierungsserver werden manchmal Automationkomponenten aufgerufen.  
  
 Verfügbarmachen von Automatisierungsobjekten können Clients, um bestimmte Verfahren automatisieren, indem es direkt auf die Objekte zugreift und Funktionalität, die der Server bereitstellt.  Verfügbarmachen Objekte diese Methode ist nützlich ein, wenn Anwendungen Funktionen bereitstellen, die für andere Anwendungen nützlich.  Beispielsweise könnte ein Textverarbeitungsprogramm die Rechtschreibprüfungsfunktionalität xxxx 2, damit andere Anwendungen sie verwenden können.  Belichtung von Objekten können somit Anbieter, um die Funktionalität ihrer Anwendungen verbessern, indem die fertige Funktionalität anderer Anwendungen.  
  
 Diese Automatisierungsobjekte verfügen über Eigenschaften und Methoden als die externe Schnittstelle.  Eigenschaften sind benannte Attribute des Automatisierungsobjekts.  Eigenschaften sind mit die Datenmember von eine C\+\+\-Klasse.  Methoden sind Funktionen, die an Automatisierungsobjekten arbeiten.  Methoden entsprechen den öffentlichen Memberfunktionen von eine C\+\+\-Klasse.  
  
> [!NOTE]
>  Obwohl Eigenschaften wie C\+\+\-Datenmember sind, sind sie nicht direkt zugreifen.  Um transparenten Zugriff gewähren, richten Sie eine interne Variable im Automatisierungsobjekt mit einem Paar aus abrufen bzw. Funktionen des festgelegten Members um darauf zuzugreifen.  
  
 Durch das Verfügbarmachen der Anwendungsfunktionalität durch eine allgemeine, gut definierte Schnittstelle, Automatisierung, ist es möglich, Anwendungen in einem einzelnen allgemeinen Programmiersprache wie Microsoft Visual Basic und in den verschiedenen, anwendungsspezifische Makrosprachen zu erstellen.  
  
##  <a name="_core_support_for_automation_servers"></a> Unterstützung für Automatisierungsserver  
 Visual C\+\+ und das MFC\-Framework bieten umfassende Unterstützung für Automatisierungsserver.  Sie behandeln viele des Aufwands, der wenn sie einen Automatisierungsserver beteiligte, erstellen, sodass Sie die Ergebnisse auf der Funktionalität der Anwendung konzentrieren.  
  
 Der grundlegende Mechanismus des Frameworks für unterstützende Automatisierung ist die Dispatchzuordnung, aus Makros, die in Deklarationen und in Aufrufen erweitert, die benötigt werden, um Methoden und Eigenschaften für OLE verfügbar zu machen.  Eine typische Dispatchzuordnung sieht wie folgt aus:  
  
 [!CODE [NVC_MFCAutomation#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAutomation#1)]  
  
 Das Eigenschaftenfenster und die Klassenansicht die in Wartungsdispatchzuordnungen.  Wenn Sie eine neue Methode oder Eigenschaft einer Klasse hinzufügen, fügt Visual C\+\+ entsprechenden `DISP_FUNCTION` oder ein `DISP_PROPERTY`\-Makro mit den Parametern hinzu, die den Klassennamen angeben, extern und interne Namen der Methode oder Eigenschaft und Datentypen.  
  
 Das **Klasse hinzufügen** Dialogfeld vereinfacht auch die Deklaration von Automatisierungsklassen und Verwalten ihrer Eigenschaften und Vorgänge.  Wenn Sie das Hinzufügens\-Klassendialogfeld verwenden, um dem Projekt eine Klasse hinzuzufügen, geben Sie dessen Basisklasse an.  Wenn die Basisklasse Automatisierung können, die Hinzufügens\-Klassendialogfeld\-Anzeigesteuerungen, die Sie verwenden, um anzugeben, ob die neue Klasse Automatisierung, ob "erstellbares OLE" ist, also, ob Objekte der Klasse auf einer Anforderung von COM\-Clients erstellt werden können\) und den externen Namen unterstützen sollte, sodass der COM\-Client verwendet.  
  
 Das **Klasse hinzufügen** Dialogfeld erstellt dann eine Klassendeklaration, einschließlich der entsprechenden Makros zum OLE\-Funktionen, die Sie angegeben haben.  Es fügt auch den Codeskelett für Implementierung der Memberfunktionen der Klasse hinzu.  
  
 Der MFC\-Anwendungs\-Assistent die Schritte vereinfacht, wenn dieses Ihre Automatisierungsserveranwendung aus dem Boden gehören, abruft.  Wenn Sie das Kontrollkästchen **Automatisierung** aus der Seite **Erweiterte Funktionen** auswählen, fügt der MFC\-Anwendungs\-Assistent `InitInstance`\-Funktion der Anwendung hinzu die Aufrufe, die erforderlich sind, die Automatisierungsobjekte zu registrieren und die Anwendung als Automatisierungsserver auszuführen.  
  
### Was möchten Sie tun?  
  
-   [Verdeutlichen Automatisierungsclients](../mfc/automation-clients.md)  
  
-   [Vertrautmachen Klasse CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
  
-   [Vertrautmachen Klasse COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)  
  
## Siehe auch  
 [Automatisierung](../mfc/automation.md)   
 [MFC\-Anwendungs\-Assistent](../mfc/reference/mfc-application-wizard.md)