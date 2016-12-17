---
title: "Anwendungseinstellungen, ATL-Projekt-Assistent"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.atl.com.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekt-Assistent, Anwendungseinstellungen"
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
caps.latest.revision: 17
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Anwendungseinstellungen, ATL-Projekt-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf der Seite **Anwendungseinstellungen** des ATL\-Projekt\-Assistenten können Sie grundlegende Features entwerfen und einem neuen ATL\-Projekt hinzufügen.  
  
## Servertyp  
 Wählen Sie unter drei Servertypen einen Server aus:  
  
 **Dynamic Link Library \(DLL\)**  
 Wählen Sie diese Option, um einen prozessinternen Server zu erstellen.  
  
 **Ausführbare Datei \(EXE\)**  
 Wählen Sie diese Option, um einen lokalen prozessexternen Server zu erstellen.  Diese Option bietet keine Unterstützung für MFC oder COM\+ 1.0 bzw.  für das Zusammenführen von Proxy\-\/Stubcode.  
  
 **Dienst \(EXE\)**  
 Wählen Sie diese Option, um eine Windows\-Anwendung zu erstellen, die beim Starten von Windows im Hintergrund ausgeführt wird.  Diese Option bietet keine Unterstützung für MFC oder COM\+ 1.0 bzw. für das Zusammenführen von Proxy\-\/Stubcode.  
  
## Zusätzliche Optionen  
  
> [!NOTE]
>  Alle zusätzlichen Optionen sind nur für DLL\-Projekte verfügbar.  
  
 **Merging von Proxy\-\/Stubcode zulassen**  
 Das Aktivieren des Kontrollkästchens **Merging von Proxy\-\/Stubcode zulassen** stellt eine bequeme Möglichkeit dar, wenn das Marshallen von Schnittstellen erforderlich ist.  Durch diese Option wird der von MIDL generierte Proxy\- und Stubcode in derselben ausführbaren Datei abgelegt wie der Server.  
  
 **Support\-MFC**  
 Wählen Sie diese Option, um festzulegen, dass das Objekt MFC\-Unterstützung umfasst.  Durch diese Option wird das Projekt mit den MFC\-Bibliotheken verknüpft, sodass Sie auf alle darin enthaltenen Klassen und Funktionen zugreifen können.  
  
 **COM\+ 1.0\-Unterstützung**  
 Wählen Sie diese Option, um die Projektbuildeinstellungen so zu ändern, dass COM\+ 1.0\-Komponenten unterstützt werden.  Zusätzlich zur Standardliste der Bibliotheken fügt der Assistent die komponentenspezifische COM\+ 1.0\-Bibliothek **comsvcs.lib** hinzu:  
  
 Zusätzlich wird **mtxex.dll** verzögert auf dem Hostsystem geladen, nachdem die Anwendung gestartet wurde.  
  
-   **Unterstützung für Komponentenregistrierung**, wenn das ATL\-Projekt Unterstützung für COM\+ 1,0 Komponenten enthält, können Sie diese Option festlegen.  Über die Komponentenregistrierung kann das COM\+ 1.0\-Objekt eine Komponentenliste abrufen, Komponenten registrieren oder die Registrierung von Komponenten \(einzeln oder gesamt\) aufheben.  
  
## Siehe auch  
 [ATL\-Projekt\-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)   
 [Standardmäßige ATL\-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)