---
title: "ClickOnce-Bereitstellung für Visual C++-Anwendungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e1a036a1520a747448c5541f367f0b43711e30b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>ClickOnce-Bereitstellung für Visual C++-Anwendungen
Visual Studio bietet zwei verschiedene Technologien zum Bereitstellen von Windows-Anwendungen: ClickOnce-Bereitstellung oder [Windows Installer](http://msdn.microsoft.com/library/cc185688) Bereitstellung.  
  
## <a name="clickonce-deployment-in-c"></a>ClickOnce-Bereitstellung in C++  
 Der Entwicklungsumgebung von Visual C++ unterstützt Visual C++-Projekte mit ClickOnce-Bereitstellung nicht direkt, aber die Tools zur Verfügung, ihn zu verwenden.  
  
> [!NOTE]
>  Visual Studio unterstützt ClickOnce in Visual c# und Visual Basic-entwicklungsumgebungen. Wenn es sich bei Visual C++-Projekt eine Abhängigkeit von einem Visual C#-Projekt ist, können Sie die Anwendung (einschließlich ihrer projektabhängigkeiten) veröffentlichen über ClickOnce-Bereitstellung in der Visual C#-Entwicklungsumgebung.  
  
 Um ein Visual C++-Anwendung mithilfe von ClickOnce bereitstellen, müssen Sie zum Erstellen einer [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest) und ein [ClickOnce-Bereitstellungsmanifest](/visualstudio/deployment/clickonce-deployment-manifest) mithilfe der [Mage.exe (Manifest Tool zum Generieren und bearbeiten)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) oder Version der grafischen Benutzeroberfläche (Informationen finden Sie unter [MageUI.exe (Manifest generieren und Bearbeiten von Manifesten, Grafischer Client)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).  

  
 Sie verwenden zunächst Mage.exe, um das Anwendungsmanifest zu erstellen; die so erstellte Datei hat die Erweiterung .manifest. Anschließend verwenden Sie Mage.exe, um das Bereitstellungsmanifest zu erstellen; die erstellte Datei hat die Erweiterung .application. Danach signieren Sie die Manifeste.  
  
 Das Anwendungsmanifest muss der Zielprozessor angeben (**X86**, **X64**, oder **ARM**). Finden Sie unter [Bereitstellung erforderlichen Komponenten für 64-Bit-Anwendungen](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) Informationen zu diesen Optionen.  
  
 Die Namen des Anwendungs- und des Bereitstellungsmanifests müssen sich vom Namen der C++-Anwendung unterscheiden. Dadurch wird ein Konflikt vermieden zwischen dem durch Mage.exe erstellten Anwendungsmanifest und dem externen Manifest, welches Teil der C++-Anwendung ist.  
  
 Die Bereitstellung müssen alle Visual C++-Bibliotheken installieren, von denen die Anwendung abhängig ist. Zum Bestimmen der Abhängigkeiten einer einzelnen Anwendung können Sie depends.exe oder das Dienstprogramm DUMPBIN mit der Option /DEPENDENTS verwenden. Weitere Informationen zu Abhängigkeiten, finden Sie unter [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Möglicherweise müssen Sie VCRedist.exe ausführen; Dieses Dienstprogramm installiert Visual C++-Bibliotheken auf dem Zielcomputer installiert.  
  
 Möglicherweise müssen Sie auch einen Bootstrapper (Voraussetzungen Installer) für die Anwendung zum Bereitstellen der erforderlicher Komponenten zu erstellen; Informationen zum Bootstrapper finden Sie unter [Bootstrapperpakete erstellen](/visualstudio/deployment/creating-bootstrapper-packages).  
  
 Eine ausführlichere Beschreibung der Technologie finden Sie unter [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment). Ein ausführliches Beispiel der ClickOnce-Bereitstellung finden Sie unter [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  
  
## <a name="see-also"></a>Siehe auch  
 [„Mage.exe“ (Tool zum Generieren und Bearbeiten von Manifesten)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Makecert.exe (Certificate Creation-Tool)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Bereitstellen von Anwendungen, Diensten und Komponenten](/visualstudio/deployment/deploying-applications-services-and-components)   
 [Windows Installer-Bereitstellung](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [ClickOnce-Sicherheit und -Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Erstellen von Bootstrapperpaketen](/visualstudio/deployment/creating-bootstrapper-packages)   
 [.NET Programmieren mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)