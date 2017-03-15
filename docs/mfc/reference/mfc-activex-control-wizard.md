---
title: "MFC-ActiveX-Steuerelement-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], MFC"
  - "MFC-ActiveX-Steuerelement-Assistent"
  - "MFC ActiveX-Steuerelemente [C++], Assistenten"
  - "OLE-Steuerelemente [C++]"
  - "OLE-Steuerelemente [C++], Erstellen"
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MFC-ActiveX-Steuerelement-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein ActiveX\-Steuerelement ist ein bestimmter Typ eines [Automatisierungsservers](../../mfc/automation-servers.md) und stellt eine wiederverwendbare Komponente dar.  Die Anwendung, in der das ActiveX\-Steuerelement sich befindet, ist der [Automatisierungsclient](../../mfc/automation-clients.md) dieses Steuerelements.  Wenn Sie eine solche wiederverwendbare Komponente erstellen möchten, sollten Sie das Steuerelement mit diesem Assistenten erstellen.  Weitere Informationen finden Sie unter [MFC\-ActiveX\-Steuerelemente](../../mfc/mfc-activex-controls.md).  
  
 Alternativ können Sie mit dem [MFC\-Anwendungs\-Assistenten](../../mfc/reference/mfc-application-wizard.md) eine Automatisierungsserver\-MFC\-Anwendung erstellen.  
  
 Ein mit diesem Assistenten erstelltes ActiveX\-Steuerelement kann über eine Benutzeroberfläche verfügen oder unsichtbar sein.  Sie können diese Option auf der Seite [Steuerelementeinstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) des Assistenten festlegen.  Ein Zeitgeber\-Steuerelement ist ein Beispiel für ein ActiveX\-Steuerelement, das normalerweise unsichtbar sein sollte.  
  
 ActiveX\-Steuerelemente können über eine komplexe Benutzeroberfläche verfügen.  Einige Steuerelemente können wie gekapselte Formulare aufgebaut sein, z. B. als einzelnes Steuerelement mit vielen Feldern, von denen jedes ein eigenes Windows\-Steuerelement darstellt.  Ein KFZ\-Teile\-Objekt, das als MFC\-ActiveX\-Steuerelement implementiert ist, kann beispielsweise eine formularähnliche Benutzeroberfläche darstellen, in der die Benutzer die Teilenummer, die Teilebezeichnung sowie andere Informationen lesen und bearbeiten können.  Weitere Informationen finden Sie unter [MFC\-ActiveX\-Steuerelemente](../../mfc/mfc-activex-controls.md).  
  
 Wie Sie einen Container für ActiveX\-Objekte erstellen, erfahren Sie unter [Erstellen eines MFC\-ActiveX\-Steuerelementcontainers](../../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
 Das MFC\-Startprogramm enthält C\+\+\-Quelldateien \(CPP\-Format\), Ressourcendateien \(RC\-Format\) und eine Projektdatei \(VCPROJ\-Format\).  Der in diesen Startdateien generierte Code basiert auf MFC.  
  
 Die folgende Beispielliste enthält Tasks und Erweiterungstypen für ActiveX\-Steuerelemente:  
  
-   [MFC\-ActiveX\-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [Hinzufügen vordefinierter Ereignisse zu einem ActiveX\-Steuerelement](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [Hinzufügen benutzerdefinierter Ereignisse](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [Hinzufügen vordefinierter Methoden](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [Hinzufügen benutzerdefinierter Methoden](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [Hinzufügen vordefinierter Eigenschaften](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [Hinzufügen benutzerdefinierter Eigenschaften](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Programmieren von ActiveX\-Steuerelementen in einem ActiveX\-Steuerelementcontainer](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## Übersicht  
 Auf dieser Assistentenseite werden die aktuellen Anwendungseinstellungen des MFC\-ActiveX\-Steuerelementprojekts beschrieben, das Sie gerade erstellen.  Der Assistent erstellt ein Projekt standardmäßig wie folgt:  
  
-   Mit dem Standardprojekt werden weder eine Laufzeitlizenz noch Hilfedateien erstellt.  Sie können diese Standardeinstellungen auf der Seite [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) ändern.  Die Seite **Übersicht** enthält nur die Optionen, die auf dieser Seite des ActiveX\-Steuerelement\-Assistenten ausgewählt werden.  
  
-   Das Projekt umfasst eine Steuerelementklasse und eine Eigenschaftenseitenklasse, deren Namen vom Projektnamen abgeleitet sind.  Sie können den Projektnamen sowie die Dateinamen auf der Seite [Steuerelementnamen](../../mfc/reference/control-names-mfc-activex-control-wizard.md) bearbeiten.  
  
-   Das Steuerelement basiert nicht auf vorhandenen Windows\-Steuerelementen; es wird aktiviert, sobald es sichtbar wird und verfügt über eine Benutzeroberfläche und ein Dialogfeld **Info**.  Sie können diese Standardeinstellungen auf der Seite [Steuerelementeinstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) ändern.  
  
## Siehe auch  
 [Erstellen und Verwalten von Visual C\+\+\-Projekten](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C\+\+\-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Konzepte](../../atl/active-template-library-atl-concepts.md)