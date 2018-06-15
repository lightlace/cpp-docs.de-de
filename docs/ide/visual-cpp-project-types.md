---
title: Visual C++-Projekttypen | Microsoft-Dokumentation
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33339981"
---
# <a name="visual-c-project-types"></a>Visual C++-Projekttypen

Sie können eine Projektvorlage verwenden, um eine grundlegende Programmstruktur, Menüs, Symbolleisten, Symbole, Verweise und `#include` -Anweisungen zu erstellen, die für das gewünschte Projekt angemessen sind. Visual Studio umfasst verschiedene Arten von Visual C++-Projektvorlagen und bietet für viele von ihnen Assistenten, sodass Sie Ihre Projekte beim Erstellen anpassen können. Sie können die Anwendung unmittelbar nach dem Erstellen eines Projekts erstellen und ausführen. Es ist empfehlenswert, den Buildprozess in Abständen durchzuführen, während Sie Ihre Anwendung entwickeln.

Sie müssen keine Vorlage verwenden, um ein Projekt zu erstellen, doch in den meisten Fällen ist es effizienter dies zu tun, da es einfacher ist, die bereitgestellten Projektdateien und die Struktur zu ändern, anstatt sie von Grund auf neu zu erstellen.  
  
> [!NOTE]
> Mit C++-Projektvorlagen können Sie ein C-Sprachprojekt erstellen. Suchen Sie im generierten Projekt die Dateien mit der Dateinamenerweiterung .cpp, und ändern Sie sie in .c. Erweitern Sie dann auf der Seite **Projekteigenschaften** für das Projekt (nicht für die Projektmappe) die Option **Konfigurationseigenschaften**, **C/C++** , und wählen Sie dann **Erweitert**. Ändern Sie die Einstellung **Kompilierungsart** in **Als C-Code kompilieren (/TC)**.

## <a name="project-templates"></a>Projektvorlagen

Die in Visual Studio enthaltenen Projektvorlagen hängen von der Produktversion und den Workloads ab, die Sie installiert haben. Wenn Sie die Workload „Desktopentwicklung mit C++“ installiert haben, verfügt Visual Studio über die folgenden Visual C++-Projektvorlagen.

### <a name="windows-desktop"></a>Windows-Desktop

|Projektvorlage|description|  
|----------------------|-----------------------------| 
|[Windows-Konsolenanwendung](../windows/creating-a-console-application.md)|Ein Projekt zum Erstellen einer Windows-Konsolenanwendung|
|[Windows-Desktopanwendung](../windows/walkthrough-creating-windows-desktop-applications-cpp.md)|Ein Projekt zum Erstellen einer Windows-Desktopanwendung (Win32)|
|[Dynamic Link Library](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)|Ein Projekt zum Erstellen einer Dynamic Link Library (DLL)|
|[Statische Bibliothek](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Ein Projekt zum Erstellen einer statischen Bibliothek (LIB)|
|Windows-Desktop-Assistenten|Ein Assistent zum Erstellen von Windows-Desktopanwendungen und -Bibliotheken mit zusätzlichen Optionen|

### <a name="general"></a>Allgemein

|Projektvorlage|description|
|----------------------|-----------------------------|
|Leeres Projekt|Ein leeres Projekt zum Erstellen einer Anwendung, Bibliothek oder DLL. Sie müssen erforderlichen Code oder Ressourcen hinzufügen.|
|[Makefile-Projekt](../ide/creating-a-makefile-project.md)|Ein Projekt zum Verwenden eines externen Buildsystems|
|Projekt mit freigegebenen Elementen|Ein Projekt zum Freigeben von Dateien zwischen mehreren Projekten|

### <a name="atl"></a>ATL

|Projektvorlage|description|
|----------------------|-----------------------------|
|[ATL-Projekt](../atl/reference/creating-an-atl-project.md)|Ein Projekt, das die Active Template Library (ATL) verwendet|

### <a name="test"></a>Test

|Projektvorlage|description|
|----------------------|-----------------------------|
|[Natives Komponententestprojekt](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)|Ein Projekt, das native C++-Komponententests enthält|

### <a name="mfc"></a>MFC

Wenn Sie Ihrer Visual Studio-Installation die Komponente für die MFC- und ATL-Unterstützung hinzufügen, werden die folgenden Projektvorlagen in Visual Studio hinzugefügt.

|Projektvorlage|description|
|----------------------|-----------------------------|
|[MFC-Anwendung](../mfc/reference/creating-an-mfc-application.md)|Ein Projekt zum Erstellen einer Anwendung, die die MFC-Bibliothek verwendet.|
|[MFC-ActiveX-Steuerelement](../mfc/reference/creating-an-mfc-activex-control.md)|Ein Projekt zum Erstellen eines ActiveX-Steuerelements, das die MFC-Bibliothek verwendet.|
|[MFC-DLL](../mfc/reference/creating-an-mfc-dll-project.md)|Ein Projekt zum Erstellen einer DLL, die die MFC-Bibliothek verwendet.|

### <a name="windows-universal-apps"></a>Universelle Windows-Apps

Wenn Sie Ihrer Visual Studio-Installation die Komponente für C++-Tools für die Universelle Windows Plattform hinzufügen, werden die folgenden Projektvorlagen in Visual Studio hinzugefügt.

Einen Überblick über Universelle Windows-Apps in C++ finden Sie unter [Universal Windows Apps (C++) (Universelle Windows-Apps (C++))](../windows/universal-windows-apps-cpp.md).

|Projektvorlage|description|
|----------------------|-----------------------------|
|Leere App|Ein Projekt für eine einseitige UWP-App ohne vordefinierte Steuerelemente oder Layouts.|
|DirectX 11-App|Ein Projekt für eine UWP-App, die DirectX 11 verwendet.|
|DirectX 12-App|Ein Projekt für eine UWP-App, die DirectX 12 verwendet.|
|DirectX 11- und XAML-App|Ein Projekt für eine UWP-App, die DirectX 11 und XAML verwendet.|
|Komponententest-App|Ein Projekt zum Erstellen einer Komponententest-App für UWP-Apps.|
|DLL|Ein Projekt für eine native DLL (Dynamic Link Library), die von einer UWP-App oder Komponente für Windows-Runtime verwendet werden kann.|
|Statische Bibliothek|Ein Projekt für eine native LIB (Static Link Library), die von einer UWP-App oder Komponente für Windows-Runtime verwendet werden kann.|
|Komponente für Windows-Runtime|Ein Projekt für eine Komponente für Windows-Runtime, die von einer UWP-App verwendet werden kann, unabhängig von der Programmiersprache, in der die App geschrieben ist.|
|Paketerstellungsprojekt für Windows-Anwendungen|Ein Projekt, das ein UWP-Paket erstellt, mit dem eine Desktopanwendung über Microsoft Store quer geladen oder verteilt werden kann.|

## <a name="todo-comments"></a>TODO-Kommentare

Viele der mit einer Projektvorlage generierten Dateien enthalten TODO-Kommentare, um Ihnen beim Identifizieren von Orten zu helfen, an denen Sie Ihren eigenen Quellcode bereitstellen können. Weitere Informationen zum Hinzufügen von Code finden Sie unter [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md) und [Working with Resource Files (Arbeiten mit Ressourcendateien)](../windows/working-with-resource-files.md).

## <a name="see-also"></a>Siehe auch

[Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
