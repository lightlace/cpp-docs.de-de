---
title: "Projekteinstellungen angeben, Assistent &quot;Neues Projekt aus vorhandenen Codedateien erstellen&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.importwiz.appsettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "„Neues Projekt aus vorhandenen Codedateien erstellen“ (Assistent), Projekteinstellungen"
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Projekteinstellungen angeben, Assistent &quot;Neues Projekt aus vorhandenen Codedateien erstellen&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Seite des Assistenten Neues Projekt aus vorhandenen Codedateien erstellen, um Folgendes anzugeben:  
  
-   Die Buildumgebung für das neue Projekt  
  
-   Buildeinstellungen für einen bestimmten Typ, den das neue Projekt aufweisen soll  
  
## Aufgabenliste  
 [Gewusst wie: Erstellen eines C\+\+\-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## UIElement-Liste  
 **Visual Studio verwenden**  
 Gibt an, dass zum Erstellen des neuen Projekts Buildtools aus Visual Studio verwendet werden sollen.  Diese Option ist standardmäßig aktiviert.  
  
 **Projekttyp**  
 Gibt den vom Assistenten zu generierenden Projekttyp an.  
  
 **Windows\-Anwendungsprojekt**  
 Gibt an, dass der Assistent ein Projekt für eine ausführbare Windows\-Anwendung generiert.  Diese Option ist im Dropdown\-Listenfeld **Projekttyp** verfügbar.  
  
 **Konsolenanwendungsprojekt**  
 Gibt an, dass der Assistent ein Projekt für eine Konsolenanwendung generiert.  Diese Option ist im Dropdown\-Listenfeld **Projekttyp** verfügbar.  
  
 **DLL\-Projekt \(Dynamically Linked Library\)**  
 Gibt an, dass der Assistent ein Projekt für eine leere Dynamic Link Library\-Anwendung generiert.  Diese Option ist im Dropdown\-Listenfeld **Projekttyp** verfügbar.  
  
 **LIB\-Projekt \(Static Library, Statische Bibliothek\)**  
 Gibt an, dass der Assistent ein Projekt für eine statische Bibliotheksanwendung generiert.  Diese Option ist im Dropdown\-Listenfeld **Projekttyp** verfügbar.  
  
 **ATL\-Unterstützung hinzufügen**  
 Fügt dem neuen Projekt ATL\-Unterstützung hinzu.  
  
 **Unterstützung für MFC hinzufügen**  
 Fügt dem neuen Projekt MFC\-Unterstützung hinzu.  
  
 **Unterstützung für die Common Language Runtime hinzufügen**  
 Fügt dem neuen Projekt Unterstützung für die CLR\-Programmierung hinzu.  
  
 **Common Language Runtime**  
 Gibt an, dass das neue Projekt mit CLR\-Features kompatibel ist.  
  
 **Common Language Runtime \(alte Syntax\)**  
 Gibt an, dass das neue Projekt mit der Managed Extensions for C\+\+\-Syntax kompatibel ist, die vor Visual C\+\+ 2005 als Syntax für die CLR\-Programmierung verwendet wurde.  
  
 **Externes Buildsystem verwenden**  
 Gibt an, dass zum Erstellen des neuen Projekts Buildtools verwendet werden sollen, die nicht in Visual Studio enthalten sind.  Wenn diese Option aktiviert ist, können Sie auf den Seiten **Einstellungen für Debugkonfiguration angeben** und **Einstellungen für Releasekonfiguration angeben** Buildbefehlszeilen festlegen.  
  
> [!NOTE]
>  Wenn die Option **Externes Buildsystem verwenden** aktiviert ist, wird das neue Projekt von der IDE nicht erstellt. Die Optionen \/D, \/I, \/FI, \/AI oder \/FU sind folglich für die Kompilierung nicht erforderlich.  Diese Optionen müssen jedoch korrekt festgelegt werden, damit IntelliSense ordnungsgemäß funktioniert.  
  
## Siehe auch  
 [Einstellungen für Debugkonfiguration angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-debug-configuration-settings.md)   
 [Einstellungen für Releasekonfiguration angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-release-configuration.md)