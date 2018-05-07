---
title: Geben Sie Einstellungen für Projektdateien, neues Projekt aus vorhandenen Code Assistent Erstellen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.appsettings
dev_langs:
- C++
helpviewer_keywords:
- Create New Project From Existing Code Files Wizard, project settings
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0f59b802b5a24c1b449f78cccee4744538a5a0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>Projekteinstellungen angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"
Geben Sie mithilfe dieser Seite des Assistenten für neue Projekt aus vorhandenen Codedateien erstellen:  
  
-   Der Buildumgebung für das neue Projekt  
  
-   Erstellen von Einstellungen entsprechend des neuen Projekts zum Generieren ein bestimmtes Typs  
  
## <a name="task-list"></a>Aufgabenliste  
 [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Verwenden Sie Visual Studio**  
 Gibt an, dass Build-Tools, die zum Erstellen des neuen Projekts in Visual Studio enthalten sind. Diese Option ist standardmäßig ausgewählt.  
  
 **Projekttyp**  
 Gibt den Typ des Projekts, das der Assistent generiert wird.  
  
 **Windows-Anwendungsprojekts**  
 Gibt an, dass der Assistent ein Projekt für eine ausführbare Windows-Anwendung generiert wird. Diese Option ist verfügbar, von der **Projekttyp** Dropdown Listenfeld aus.  
  
 **Konsolenanwendungsprojekt**  
 Gibt an, dass der Assistent ein Projekt für eine Konsolenanwendung generiert wird. Diese Option ist verfügbar, von der **Projekttyp** Dropdown Listenfeld aus.  
  
 **Dynamisch verknüpfte Klassenbibliotheksprojekt (DLL)**  
 Gibt an, dass der Assistent ein Projekt für eine leere dynamic Link Library-Anwendung generiert wird. Diese Option ist verfügbar, von der **Projekttyp** Dropdown Listenfeld aus.  
  
 **Statische Bibliothek (LIB)-Projekt**  
 Gibt an, dass der Assistent ein Projekt für eine statische bibliotheksanwendung generiert wird. Diese Option ist verfügbar, von der **Projekttyp** Dropdown Listenfeld aus.  
  
 **ATL-Unterstützung hinzufügen**  
 Das neue Projekt hinzugefügt ATL-Unterstützung.  
  
 **Hinzufügen von Unterstützung für MFC**  
 Das neue Projekt hinzugefügt MFC-Unterstützung.  
  
 **Hinzufügen von Unterstützung für die Common Language Runtime**  
 Fügt die CLR-Programmierung Support, um das neue Projekt.  
  
 **Common Language Runtime**  
 Gibt das neue Projekt ein, um mit der CLR-Funktionen kompatibel sein.  
  
 **Common Language Runtime (alte Syntax)**  
 Gibt das neue Projekt ein, um mit Managed Extensions for C++-Syntax kompatibel sein, die das CLR-Programmiersyntax vor Visual C++ 2005 ist.  
  
 **Verwenden von externen Buildsystems**  
 Gibt an, dass Buildtools, die nicht in Visual Studio enthalten sind, für das neue Projekt zu erstellen. Wenn diese Option ausgewählt ist, können Sie die Build-Befehlszeilen angeben, auf die **Debuggen Konfigurationseinstellungen geben** und **Einstellungen für Releasekonfiguration angeben** Seiten.  
  
> [!NOTE]
>  Wenn die **externen Buildsystems verwenden** Option aktiviert ist, werden die IDE erstellt das neue Projekt, nicht das/d, / I, / Fi, / AI verwenden oder/fu Optionen sind nicht für die Kompilierung erforderlich. Allerdings müssen diese Optionen damit IntelliSense ordnungsgemäß funktioniert ordnungsgemäß festgelegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Einstellungen für Debugkonfiguration angeben, neues Projekt aus vorhandenen Code Dateien-Assistenten erstellen](../ide/specify-debug-configuration-settings.md)   
 [Einstellungen für Releasekonfiguration angeben, Assistent „Neues Projekt aus vorhandenen Codedateien erstellen“](../ide/specify-release-configuration.md)