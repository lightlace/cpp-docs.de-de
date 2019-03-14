---
title: ClickOnce-Bereitstellung für Visual C++-Anwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
ms.openlocfilehash: e1460f13226291e76d297b628d3542a1e147900f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742155"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>ClickOnce-Bereitstellung für Visual C++-Anwendungen

Visual Studio bietet zwei verschiedene Technologien für die Bereitstellung von Windows-Anwendungen: Die Bereitstellung mit ClickOnce oder dem [Windows Installer](/windows/desktop/Msi/windows-installer-portal).

## <a name="clickonce-deployment-in-c"></a>ClickOnce-Bereitstellung in C++

Die Visual C++-Entwicklungsumgebung bietet keine direkte Unterstützung für das Bereitstellen von Visual C++-Projekten mit ClickOnce, dafür zu verwendende Tools sind jedoch verfügbar.

> [!NOTE]
>  Visual Studio unterstützt ClickOnce in den Visual C#- und Visual Basic-Entwicklungsumgebungen. Wenn das Visual C++-Projekt von einem Visual C#-Projekt abhängig ist, können Sie die Anwendung (einschließlich ihrer Projektabhängigkeiten) mit der ClickOnce-Bereitstellung der Visual C#-Entwicklungsumgebung veröffentlichen.

Sie müssen zunächst ein [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest) und ein [ClickOnce-Bereitstellungsmanifest](/visualstudio/deployment/clickonce-deployment-manifest) mithilfe von [Mage.exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) oder der GUI-Version des Tools erstellen, um eine Visual C++-Anwendung mit ClickOnce bereitzustellen (Informationen finden Sie unter [MageUI.exe (Manifest Generation and Editing Tool, grafischer Client)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).

Sie verwenden zunächst Mage.exe, um das Anwendungsmanifest zu erstellen; die so erstellte Datei hat die Erweiterung .manifest. Anschließend verwenden Sie Mage.exe, um das Bereitstellungsmanifest zu erstellen; die erstellte Datei hat die Erweiterung .application. Danach signieren Sie die Manifeste.

Im Anwendungsmanifest muss der Zielprozessor (**x86**, **x64** oder **ARM**) angegeben werden. Informationen zu diesen Optionen finden Sie unter [Deploying Prerequisites for 64-bit Applications (Bereitstellen der erforderlichen Komponenten für 64-Bit-Anwendungen)](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications).

Die Namen des Anwendungs- und des Bereitstellungsmanifests müssen sich vom Namen der C++-Anwendung unterscheiden. Dadurch wird ein Konflikt vermieden zwischen dem durch Mage.exe erstellten Anwendungsmanifest und dem externen Manifest, welches Teil der C++-Anwendung ist.

Im Rahmen der Bereitstellung müssen alle Visual C++-Bibliotheken installiert werden, von denen die Anwendung abhängt. Zum Bestimmen der Abhängigkeiten einer einzelnen Anwendung können Sie depends.exe oder das Dienstprogramm DUMPBIN mit der Option /DEPENDENTS verwenden. Weitere Informationen zu Abhängigkeiten finden Sie unter [Understanding the Dependencies of a Visual C++ Application (Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung)](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Möglicherweise müssen Sie „VCRedist.exe“ ausführen. Dieses Hilfsprogramm installiert Visual C++-Bibliotheken auf dem Zielcomputer.

Möglicherweise müssen Sie für die Anwendung einen Bootstrapper (Programm zum Installieren erforderlicher Komponenten) erstellen, um die erforderlichen Komponenten bereitzustellen. Informationen zum Bootstrapper finden Sie unter [Creating Bootstrapper Packages (Erstellen von Bootstrapperpaketen)](/visualstudio/deployment/creating-bootstrapper-packages).

Eine ausführlichere Beschreibung der Technologie finden Sie unter [ClickOnce Security and Deployment (ClickOnce-Sicherheit und Bereitstellung)](/visualstudio/deployment/clickonce-security-and-deployment). Ein ausführliches Beispiel der ClickOnce-Bereitstellung finden Sie unter [Walkthrough: Manually Deploying a ClickOnce Application (Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung)](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).

## <a name="see-also"></a>Siehe auch

[Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[Makecert.exe (Tool für die Zertifikaterstellung)](https://msdn.microsoft.com/library/windows/desktop/aa386968)<br>
[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)<br>
[Bereitstellen von Anwendungen, Diensten und Komponenten](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Erstellen von Bootstrapperpaketen](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)
