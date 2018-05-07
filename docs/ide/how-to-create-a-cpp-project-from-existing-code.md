---
title: 'Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1786e5704d7afd07576ab738d907eb841518f8be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>Gewusst wie: Erstellen eines C++-Projekts aus vorhandenem Code

In Visual Studio können Sie Ihre vorhandenen Codedateien in ein Visual C++-Projekt portieren, mithilfe der **neues Projekt aus vorhandenen Codedateien erstellen** Assistenten. Dieser Assistent ist nicht verfügbar in älteren Express-Editionen von Visual Studio. Dieser Assistent erstellt eine neue Projektmappe und Projekt, verwendet das MSBuild-System zum Verwalten von Quelldateien und Buildkonfiguration.  
  
Portieren Ihrer vorhandenen Codedateien in ein Visual C++-Projekt können Sie alle systemeigenen MSBuild Project Management-Funktionen in die IDE integriert. Falls gewünscht, verwenden Sie das vorhandene Buildsystem, z. B. Nmake Makefiles, CMake oder alternativen, können Sie stattdessen die Option Ordner öffnen. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](../ide/non-msbuild-projects.md). Beide Optionen können Sie die IDE-Funktionen verwenden, z. B. [IntelliSense](/visualstudio/ide/using-intellisense) und [Projekteigenschaften](../ide/working-with-project-properties.md).  
  
### <a name="to-create-a-c-project-from-existing-code"></a>So erstellen Sie ein C++-Projekt aus vorhandenem Code  
  
1.  Auf der **Datei** Sie im Menü **neu**, und klicken Sie dann auf **Projekt aus vorhandenem Code**.  
  
1.  Auf der ersten Seite des der **neues Projekt aus vorhandenen Codedateien erstellen** Assistenten **Visual C++** in der **welchen Typ von Projekt möchten Sie erstellen** Liste. Klicken Sie auf **Weiter** , um fortzufahren. 
  
1.  Geben Sie Speicherorts für Ihr Projekt und das Verzeichnis für Ihre Quelldateien. Informationen auf dieser Seite finden Sie unter [geben Projektspeicherort und Quelldateien, neues Projekt aus vorhandenen Code Dateien Assistenten zum Erstellen von](../ide/specify-project-location-and-source-files.md). Klicken Sie auf **Weiter** , um fortzufahren.  
  
1.  Geben Sie die Einstellungen für Projektdateien verwendet. Informationen auf dieser Seite finden Sie unter [Projekteinstellungen angeben, neues Projekt aus vorhandenen Code Dateien Assistenten zum Erstellen von](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md). Klicken Sie auf **Weiter** , um fortzufahren.  

1.  Geben Sie die Einstellungen für die Debugkonfiguration verwendet. Informationen auf dieser Seite finden Sie unter [Debuggen Konfigurationseinstellungen angeben, neues Projekt aus vorhandenen Code Dateien Assistenten zum Erstellen von](../ide/specify-debug-configuration-settings.md). Klicken Sie auf **Weiter** , um fortzufahren.  

1.  Geben Sie die Einstellungen für die Releasekonfiguration verwendet. Informationen auf dieser Seite finden Sie unter [Einstellungen für Releasekonfiguration angeben, neues Projekt aus vorhandenen Code Dateien Assistenten zum Erstellen von](../ide/specify-release-configuration.md). Wählen Sie **Fertig stellen** um das neue Projekt zu generieren.  
  
## <a name="see-also"></a>Siehe auch  

[Geben Sie Projekt Projektspeicherort und Quelldateien, neues Projekt aus vorhandenen Code Dateien-Assistenten erstellen.](../ide/specify-project-location-and-source-files.md)   
[Projekteinstellungen angeben, neues Projekt aus vorhandenen Code Dateien-Assistenten erstellen](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)   
[Einstellungen für Debugkonfiguration angeben, neues Projekt aus vorhandenen Code Dateien-Assistenten erstellen](../ide/specify-debug-configuration-settings.md)   
[Einstellungen für Releasekonfiguration angeben, Assistent „Neues Projekt aus vorhandenen Codedateien erstellen“](../ide/specify-release-configuration.md)