---
title: Visual C++-Projekttypen | Microsoft Docs
ms.custom: ''
ms.date: 10/30/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], projects
- project templates [Visual Studio], C++
- TODO comments [C++]
- projects [C++], types
- templates [C++], projects
- applications [C++], projects
- Visual C++ projects, types
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80ac3479338dcb7f6be9e7e5f3f150cc8e15a9a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="visual-c-project-types"></a>Visual C++-Projekttypen

Sie können eine Projektvorlage verwenden, um eine grundlegende Programmstruktur, Menüs, Symbolleisten, Symbole, Verweise und `#include` -Anweisungen zu erstellen, die für das gewünschte Projekt angemessen sind. Visual Studio umfasst verschiedene Arten von Visual C++-Projektvorlagen und bietet für viele von ihnen Assistenten, sodass Sie Ihre Projekte beim Erstellen anpassen können. Sofort, nachdem Sie ein Projekt erstellt haben, können Sie sie erstellen und Ausführen der Anwendung; Es wird empfohlen, zwischendurch während der Entwicklung der Anwendung.

Sie müssen keine Vorlage verwenden, um ein Projekt zu erstellen, doch in den meisten Fällen ist es effizienter dies zu tun, da es einfacher ist, die bereitgestellten Projektdateien und die Struktur zu ändern, anstatt sie von Grund auf neu zu erstellen.  
  
> [!NOTE]
> Mit C++-Projektvorlagen können Sie ein C-Sprachprojekt erstellen. Suchen Sie im generierten Projekt die Dateien mit der Dateinamenerweiterung .cpp, und ändern Sie sie in .c. Erweitern Sie dann auf der Seite **Projekteigenschaften** für das Projekt (nicht für die Projektmappe) die Option **Konfigurationseigenschaften**, **C/C++** , und wählen Sie dann **Erweitert**. Ändern Sie die Einstellung **Kompilierungsart** in **Als C-Code kompilieren (/TC)**.

## <a name="project-templates"></a>Projektvorlagen

Die in Visual Studio enthalten Projektvorlagen hängen davon ab, die Produktversion und die arbeitsauslastungen, die Sie installiert haben. Wenn Sie die Desktopentwicklung Arbeitslast C++ installiert haben, hat Visual Studio diese Visual C++-Projektvorlagen.

### <a name="windows-desktop"></a>Windows-Desktop

|Projektvorlage|Beschreibung|  
|----------------------|-----------------------------| 
|[Windows-Konsolenanwendung](../windows/creating-a-console-application.md)|Ein Projekt zum Erstellen einer Windows-Konsolenanwendung.|
|[Windows-Desktopanwendung](../windows/walkthrough-creating-windows-desktop-applications-cpp.md)|Ein Projekt zum Erstellen einer Windows-Desktopanwendung (Win32).|
|[Dynamic Link Library](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)|Ein Projekt zum Erstellen einer Dynamic Link Library (DLL).|
|[Statische Bibliothek](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Ein Projekt zum Erstellen einer statischen Bibliothek (LIB).|
|Assistent für Windows-Desktop|Ein Assistent zum Erstellen von Windows-desktopanwendungen und Bibliotheken mit zusätzlichen Optionen.|

### <a name="general"></a>Allgemein

|Projektvorlage|Beschreibung|
|----------------------|-----------------------------|
|Leeres Projekt|Ein leeres Projekt zum Erstellen einer Anwendung, eine Bibliothek oder eine DLL. Sie müssen Code und keine erforderlichen Ressourcen hinzufügen.|
|[Makefile-Projekt](../ide/creating-a-makefile-project.md)|Ein Projekt für die Verwendung eines externen Buildsystems.|
|Freigegebene Projekt|Ein Projekt für die Freigabe von Dateien zwischen mehreren Projekten verwendet wird.|

### <a name="atl"></a>ATL

|Projektvorlage|Beschreibung|
|----------------------|-----------------------------|
|[ATL-Projekt](../atl/reference/creating-an-atl-project.md)|Ein Projekt, der Active Template Library verwendet.|

### <a name="test"></a>Test

|Projektvorlage|Beschreibung|
|----------------------|-----------------------------|
|[Systemeigenes Komponententestprojekt](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)|Ein Projekt, systemeigenen C++-Komponententests enthält.|

### <a name="mfc"></a>MFC

Wenn Sie, dass die MFC und ATL-Komponente der Visual Studio-Installation unterstützt hinzufügen, werden diese Projektvorlagen in Visual Studio hinzugefügt.

|Projektvorlage|Beschreibung|
|----------------------|-----------------------------|
|[MFC-Anwendung](../mfc/reference/creating-an-mfc-application.md)|Ein Projekt zum Erstellen einer Anwendung, die die Microsoft Foundation Class (MFC)-Bibliothek verwendet.|
|[MFC-ActiveX-Steuerelement](../mfc/reference/creating-an-mfc-activex-control.md)|Ein Projekt zum Erstellen eines ActiveX-Steuerelements, das die MFC-Bibliothek verwendet.|
|[MFC-DLL](../mfc/reference/creating-an-mfc-dll-project.md)|Ein Projekt zum Erstellen einer Dynamic Link Library, die die MFC-Bibliothek verwendet.|

### <a name="windows-universal-apps"></a>Universelle Windows-Apps

Wenn Sie Visual Studio-Installation die Toolkomponenten C++ Windows Universal-Plattform hinzugefügt haben, werden diese Projektvorlagen in Visual Studio hinzugefügt.

Einen Überblick über die Windows Universal-apps in C++ finden Sie unter [universelle Windows-Apps (C++)](../windows/universal-windows-apps-cpp.md).

|Projektvorlage|Beschreibung|
|----------------------|-----------------------------|
|Leere App|Ein Projekt für eine Einzelseiten universelle Windows-Plattform (UWP)-app, die nicht über vordefinierte Steuerelemente oder Layout verfügt.|
|DirectX 11-App|Ein Projekt für eine universelle Windows-Plattform-app, die DirectX 11 verwendet.|
|DirectX 12-App|Ein Projekt für eine universelle Windows-Plattform-app, die DirectX 12 verwendet.|
|DirectX 11 und XAML-App|Ein Projekt für eine universelle Windows-Plattform-app, die DirectX 11 und XAML verwendet.|
|Komponententest, Test-App|Ein Projekt zum Erstellen einer Einheit Test-app für apps der universellen Windows-Plattform (UWP).|
|DLL|Ein Projekt für eine systemeigene Dynamic Link Library (DLL), die von einer universellen Windows-Plattform-app oder Common Language Runtime-Komponente verwendet werden kann.|
|Statische Bibliothek|Ein Projekt für eine systemeigene statische Verknüpfung-Bibliothek (LIB), die von einer universellen Windows-Plattform-app oder Common Language Runtime-Komponente verwendet werden kann.|
|Komponente für Windows-Runtime|Ein Projekt für eine Windows-Runtime-Komponente, die von einer universellen Windows-Plattform-app, unabhängig von der Programmiersprache verwendet werden kann, in denen die Anwendung geschrieben wird.|
|Verpacken von Windows-Anwendungsprojekt|Ein Projekt, das ein Paket für universelle Windows-Plattform erstellt ermöglicht eine Desktopanwendung auf die Seite geladen oder über den Microsoft Store verteilt werden.|

## <a name="todo-comments"></a>TODO-Kommentare

Viele der mit einer Projektvorlage generierten Dateien enthalten TODO-Kommentare, um Ihnen beim Identifizieren von Orten zu helfen, an denen Sie Ihren eigenen Quellcode bereitstellen können. Weitere Informationen zum Hinzufügen von Code finden Sie unter [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md) und [arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md).

## <a name="see-also"></a>Siehe auch

[Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
