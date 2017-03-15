---
title: "Wann m&#252;ssen Updatehandler aufgerufen werden? | Microsoft Docs"
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
  - "Befehlsrouting, Updatebefehle"
  - "Befehlsrouting, Updatehandler"
  - "Deaktivieren von Menüelementen"
  - "Deaktivieren von Symbolleisten-Schaltflächen"
  - "Menüelemente, Aktivieren"
  - "Menüs [C++], Initialisieren"
  - "Menüs [C++], Aktualisieren bei Kontextänderungen"
  - "Schaltflächen der Symbolleiste [C++], Aktivieren"
  - "Symbolleisten-Steuerelemente [MFC], Aktualisiert während OnIdle-Methode"
  - "Symbolleisten [C++], Aktualisieren"
  - "Updatehandler"
  - "Updatehandler, Aufrufen"
  - "Aktualisieren von Benutzeroberflächenobjekten"
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Wann m&#252;ssen Updatehandler aufgerufen werden?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nehmen wir der Benutzer die Maus im Menü Datei an, die eine Meldung `WM_INITMENUPOPUP` generiert.  Der Aktualisierungsmechanismus des Framework aktualisiert zusammen alle Elemente im Menü Datei, bevor das Menü unten zurückgestellt, damit der Benutzer sie finden kann.  
  
 Aufgabe, die Frameworkrouten\-Updatebefehle für alle Menüelemente im Popupmenü entlang dem Standardbefehlsrouting.  Befehlsziele im Routing haben die Möglichkeit, alle Menüelemente zu aktualisieren, indem der Updates\-Befehl mit einem entsprechenden Eintrag in der Meldungszuordnung des Formulars \( `ON_UPDATE_COMMAND_UI`\) entsprechen und eine "Aktualisierungshandler" Funktion aufrufen.  Somit für ein Menü mit sechs Menüelementen, werden sechs Aktualisierungsbefehle gesendet.  Wenn ein Aktualisierungshandler für die Befehls\-ID des Menüelements vorhanden, wird jedoch aufgerufen, um die Aktualisierung durchzuführen.  Wenn nicht, überprüft das Framework das Vorhandensein eines Handlers für diese Befehls\-ID und aktiviert oder deaktiviert das Menüelement nach Bedarf.  
  
 Wenn das Framework `ON_UPDATE_COMMAND_UI` einen Eintrag nicht während des Befehlsroutings findet, können es automatisch das Benutzeroberflächeobjekt, wenn ein Eintrag mit `ON_COMMAND` an derselben Befehl ID gibt  Andernfalls deaktiviert das Benutzeroberflächeobjekt.  Um sicherzustellen, dass ein Benutzeroberflächeobjekt aktiviert ist, stellen Sie einen Handler für den Befehl, den das Objekt generiert bereit oder erstellen Sie einen Aktualisierungshandler dafür bereit.  Siehe die Abbildung im Thema [Benutzeroberfläche\-Objekte und Befehls\-IDs](../mfc/user-interface-objects-and-command-ids.md).  
  
 Es ist möglich, das Standarddeaktivieren von Benutzeroberflächenobjekten zu deaktivieren.  Weitere Informationen finden Sie im [m\_bAutoMenuEnable](../Topic/CFrameWnd::m_bAutoMenuEnable.md)\-Member der `CFrameWnd`\-Klasse in der *MFC\-Referenz*.  
  
 Menüinitialisierung ist im Framework automatisch und wird ausgelöst, wenn die Anwendung eine Meldung empfängt. `WM_INITMENUPOPUP` Während der Leerlaufschleife sucht das Framework Befehlsrouting für Schaltflächenaktualisierungshandler, ebenso wie es für Menüs bewirkt.  
  
## Siehe auch  
 [Gewusst wie: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)