---
title: "ClickOnce-Bereitstellung f&#252;r Visual&#160;C++-Anwendungen"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bereitstellen von Anwendungen [C++], ClickOnce"
  - "Anwendungsbereitstellung [C++], ClickOnce"
  - "ClickOnce-Bereitstellung [C++], C++-Anwendungen"
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# ClickOnce-Bereitstellung f&#252;r Visual&#160;C++-Anwendungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] verfügt über zwei verschiedene Technologien zum Bereitstellen von Windows\-Anwendungen: ClickOnce\-Bereitstellung oder [Windows Installer](http://msdn.microsoft.com/library/cc185688)\-Bereitstellung.  
  
## ClickOnce\-Bereitstellung in C\+\+  
 Die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Entwicklungsumgebung bietet keine direkte Unterstützung für das Bereitstellen von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Projekten mit [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)], dafür zu verwendende Tools sind jedoch verfügbar.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] unterstützt [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] in der [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)]\-Entwicklungsumgebung und der [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\-Entwicklungsumgebung.  Wenn das [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Projekt von einem [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)]\-Projekt abhängig ist, können Sie die Anwendung \(einschließlich ihrer Projektabhängigkeiten\) mit der [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)]\-Bereitstellung der [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)]\-Entwicklungsumgebung veröffentlichen.  
  
 Zum Veröffentlichen einer [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Anwendung mit [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] müssen Sie zunächst ein [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md) und ein [ClickOnce Deployment Manifest](../Topic/ClickOnce%20Deployment%20Manifest.md) mit dem [Mage.exe \(Tool zum Generieren und Bearbeiten von Manifesten\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md) oder seiner GUI \(Graphical User Interface\)\-Version erstellen \(Informationen hierzu finden Sie unter [MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)\).  
  
 Sie verwenden zunächst Mage.exe, um das Anwendungsmanifest zu erstellen; die so erstellte Datei hat die Erweiterung .manifest.  Anschließend verwenden Sie Mage.exe, um das Bereitstellungsmanifest zu erstellen; die erstellte Datei hat die Erweiterung .application.  Danach signieren Sie die Manifeste.  
  
 Im Anwendungsmanifest muss der Zielprozessor \(**x86**, **x64** oder **ARM**\) angegeben werden.  Informationen zu diesen Optionen finden Sie unter [Bereitstellen der erforderlichen Komponenten für 64\-Bit\-Anwendungen](../Topic/Deploying%20Prerequisites%20for%2064-bit%20Applications.md).  
  
 Die Namen des Anwendungs\- und des Bereitstellungsmanifests müssen sich vom Namen der C\+\+\-Anwendung unterscheiden.  Dadurch wird ein Konflikt vermieden zwischen dem durch Mage.exe erstellten Anwendungsmanifest und dem externen Manifest, welches Teil der C\+\+\-Anwendung ist.  
  
 Im Rahmen der Bereitstellung müssen alle [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken installiert werden, von denen die Anwendung abhängt.  Zum Bestimmen der Abhängigkeiten einer einzelnen Anwendung können Sie depends.exe oder das Dienstprogramm DUMPBIN mit der Option \/DEPENDENTS verwenden.  Weitere Informationen über Abhängigkeiten finden Sie unter [Grundlegendes zu den Abhängigkeiten einer Visual C\+\+\-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  Möglicherweise müssen Sie VCRedist.exe ausführen; dieses Dienstprogramm installiert [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken auf dem Zielcomputer.  
  
 Möglicherweise müssen Sie für die Anwendung einen Bootstrapper \(Programm zum Installieren erforderlicher Komponenten\) erstellen, um die erforderlichen Komponenten bereitzustellen; Informationen zum Bootstrapper finden Sie unter [Erstellen von Bootstrapperpaketen](../Topic/Creating%20Bootstrapper%20Packages.md).  
  
 Eine ausführlichere Beschreibung der Technologie finden Sie unter [ClickOnce Security and Deployment](../Topic/ClickOnce%20Security%20and%20Deployment.md).  Ein ausführliches Beispiel zur [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)]\-Bereitstellung finden Sie unter [Walkthrough: Manually Deploying a ClickOnce Application](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md).  
  
## Siehe auch  
 [Mage.exe \(Tool zum Generieren und Bearbeiten von Manifesten\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)   
 [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Bereitstellen von Anwendungen, Diensten und Komponenten](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md)   
 [Windows Installer Deployment](assetId:///121be21b-b916-43e2-8f10-8b080516d2a0)   
 [ClickOnce Security and Deployment](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Erstellen von Bootstrapperpaketen](../Topic/Creating%20Bootstrapper%20Packages.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)