---
title: 'Vorgehensweise: Erstellen von CLR-Konsolenanwendungen (C++ / CLI) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 60804b3863a4b44bc963f289b1d6a8c2f2d5cbf7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211156"
---
# <a name="how-to-create-clr-console-applications-ccli"></a>Gewusst wie: Erstellen von CLR-Konsolenanwendungen (C++/CLI)
Sie können die Vorlage für Konsolenanwendungen zum Erstellen eines Konsolen-App-Projekts verwenden, das bereits wesentliche Projektverweise und Dateien enthält.  
  
 Normalerweise wird eine Konsolen-App in eine eigenständige ausführbare Datei kompiliert, sie hat jedoch keine grafische Benutzeroberfläche. Ein Benutzer führt die Konsolen-App mit einer Eingabeaufforderung aus und verwendet die Eingabeaufforderung, um Anweisungen an die ausgeführte App auszugeben. Außerdem stellt die App an der Eingabeaufforderung Ausgabeinformationen bereit. Aufgrund ihrer Unmittelbarkeit eignet sich die Konsolen-App hervorragend, um Programmiertechniken zu erlernen, ohne sich über die Implementierung einer Benutzeroberfläche Gedanken zu machen.  
  
 Wenn Sie die Vorlage für Konsolenanwendungen zum Erstellen eines Projekts verwenden, werden automatisch diese Verweise und Dateien hinzugefügt:  
  
-   Verweise auf diese .NET Framework-Namespaces:  
  
    -   [System](https://msdn.microsoft.com/library/system.appdomainmanager.appdomainmanager.aspx)– enthält grundlegende Klassen und Basisklassen, definieren häufig, verwendete Werte und Verweisdatentypen, Ereignisse und Ereignishandler, Schnittstellen, Attribute und Verarbeitungsausnahmen.  
  
    -   mscorlib – Assembly-DLL, die die .NET Framework-Entwicklung unterstützt.  
  
-   Quelldateien:  
  
    -   Konsole (CPP-Datei) – Hauptquelldatei und Einstiegspunkt in die App, die Sie soeben erstellt haben. Diese Datei identifiziert die DLL-Datei und den Namespace des Projekts. Fügen Sie eigenen Code in diese Datei ein.  
  
    -   AssemblyInfo.cpp – Diese Datei enthält Attribute, Dateien, Ressourcen, Typen, Versionsinformationen, Signaturinformationen usw., die Sie zum Ändern der Assemblymetadaten des Projekts verwenden können. Weitere Informationen finden Sie unter [Assemblyinhalte](/dotnet/framework/app-domains/assembly-contents).  
  
    -   Stdafx.cpp – Diese Datei wird zum Erstellen der vorkompilierten Headerdatei "Win32.pc" und der vorkompilierten Typendatei "StdAfx.obj" verwendet.  
  
-   Headerdateien:  
  
    -   Stdafx.h – Diese Datei wird zum Erstellen der vorkompilierten Headerdatei "Win32.pc" und der vorkompilierten Typendatei "StdAfx.obj" verwendet.  
  
    -   resource.h – Eine generierte Includedatei für "app.rc".  
  
-   Ressourcendateien:  
  
    -   app.rc – Die Ressourcenskriptdatei eines Programms.  
  
    -   app.ico – Die Symboldatei eines Programms.  
  
-   ReadMe.txt – Diese Datei beschreibt die Dateien im Projekt.  
  
## <a name="to-create-a-common-language-runtime-clr-console-app-project"></a>Zum Erstellen eines Common Language Runtime (CLR)-Konsolen-App-Projekts  
  
1.  Wählen Sie in der Menüleiste **Datei** > **Neu** > **Projekt** aus.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** im Bereich **Installierte Vorlagen**den Knoten **Visual C++** aus. Wählen Sie den Knoten **CLR** und dann die Vorlage für Konsolenanwendungen aus.  
  
3.  Geben Sie im Feld **Name** einen eindeutigen Namen für die Anwendung ein.  
  
     Sie können andere Projekt- und Lösungseinstellungen angeben, sie sind jedoch nicht erforderlich.  
  
4.  Klicken Sie auf die Schaltfläche **OK** .  
  
## <a name="see-also"></a>Siehe auch  
 [CLR Projects (CLR-Projekte)](../ide/files-created-for-clr-projects.md)   


