---
title: "Anwendungseinstellungen, MFC-DLL-Assistent"
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
  - "vc.appwiz.mfc.dll.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-DLL-Assistent, Anwendungseinstellungen"
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Anwendungseinstellungen, MFC-DLL-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des MFC\-DLL\-Assistenten entwerfen Sie grundlegende Features für ein neues MFC\-DLL\-Projekt und fügen sie hinzu.  
  
## DLL\-Typ  
 Wählen Sie den zu erstellenden DLL\-Typ aus.  
  
 **Reguläre DLL, die eine öffentliche MFC\-DLL verwendet**  
 Wählen Sie diese Option, um die MFC\-Bibliothek als gemeinsam genutzte DLL mit dem Programm zu verknüpfen.  Bei Verwendung dieser Option können MFC\-Objekte von der DLL und der aufrufenden Anwendung nicht gemeinsam genutzt werden.  Das Programm sendet zur Laufzeit Aufrufe an die MFC\-Bibliothek.  Durch diese Option benötigt das Programm weniger Festplatten\- und Arbeitsspeicherkapazität, wenn es aus mehreren ausführbaren Dateien zusammengestellt wurde, die die MFC\-Bibliothek nutzen.  Sowohl Win32\- als auch MFC\-Programme können Funktionen in der DLL aufrufen.  Die MFC\-DLL muss mit diesem Projekttyp weitergegeben werden.  
  
 **Reguläre DLL, die mit MFC statisch verknüpft ist**  
 Wählen Sie diese Option, um das Programm zur Buildzeit statisch mit der MFC\-Bibliothek zu verknüpfen.  Sowohl Win32\- als auch MFC\-Programme können Funktionen in der DLL aufrufen.  Diese Option vergrößert zwar den Programmumfang, die MFC\-DLL braucht jedoch mit diesem Projekttyp nicht weitergegeben zu werden.  MFC\-Objekte können nicht von der DLL und der aufrufenden Anwendung gemeinsam genutzt werden.  
  
 **MFC\-Erweiterungs\-DLL**  
 Wählen Sie diese Option, wenn Ihr Programm zur Laufzeit Aufrufe an die MFC\-Bibliothek senden soll und wenn MFC\-Objekte von der DLL und der aufrufenden Anwendung gemeinsam genutzt werden sollen.  Durch diese Option benötigt das Programm weniger die Festplatten\- und Arbeitsspeicherkapazität, wenn es aus mehreren ausführbaren Dateien zusammengestellt wurde, die die MFC\-Bibliothek nutzen.  Nur MFC\-Programme können Funktionen in der DLL aufrufen.  Die MFC\-DLL muss mit diesem Projekttyp weitergegeben werden.  
  
## Zusätzliche Features  
 Legen Sie fest, ob die MFC\-DLL die Automatisierung und Windows\-Sockets unterstützen soll.  
  
 **Automatisierung**  
 Aktivieren Sie **Automatisierung**, um dem Programm die Bearbeitung der in einem anderen Programm implementierten Objekte zu ermöglichen.  Durch die Auswahl von **Automatisierung** wird das Programm auch anderen Automatisierungsclients zur Verfügung gestellt.  Weitere Informationen finden Sie unter [Automatisierung](../../mfc/automation.md).  
  
 **Windows\-Sockets**  
 Wählen Sie diese Option, um anzugeben, dass das Programm Windows\-Sockets unterstützt.  Windows\-Sockets ermöglichen es Ihnen, Programme zu schreiben, die über TCP\/IP\-Netzwerke kommunizieren.  
  
 Nachdem die MFC\-DLL mit Windows\-Sockets\-Unterstützung erstellt wurde, wird die Socketunterstützung durch [CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md) initialisiert, und die MFC\-Headerdatei **StdAfx.h** enthält die Datei **AfxSock.h**.  
  
## Siehe auch  
 [MFC\-DLL\-Assistent](../../mfc/reference/mfc-dll-wizard.md)   
 [Erstellen eines MFC\-DLL\-Projekts](../../mfc/reference/creating-an-mfc-dll-project.md)