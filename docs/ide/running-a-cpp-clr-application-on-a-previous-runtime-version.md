---
title: "Ausf&#252;hren einer C++&#160;/clr-Anwendung unter einer fr&#252;heren Laufzeitversion"
ms.custom: na
ms.date: "12/03/2016"
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
  - "app.config-Dateien, Angegebene Version der Common Language Runtime"
  - "Anwendungsbereitstellung [C++], Angegebene Version der Common Language Runtime"
  - "Anwendungen [C++], Angegebene Version der Common Language Runtime"
  - "Abwärtskompatibilität [C++], Angegebene Version der Common Language Runtime"
  - "Common Language Runtime [C++], Angegebene Version"
  - "Kompatibilität [C++], Angegebene Version der Common Language Runtime"
  - "Bereitstellen von Anwendungen [C++], Angegebene Version der Common Language Runtime"
  - "Versionen [C++]"
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# Ausf&#252;hren einer C++&#160;/clr-Anwendung unter einer fr&#252;heren Laufzeitversion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn nicht anders angegeben wird eine Visual C\+\+ .NET\-Framework\-Anwendung, auf die Version der CLR \(Common Language Runtime\) ausgeführt wird, erstellt der Compiler verwendet, um die Anwendung zu erstellen.  Es ist jedoch für eine EXE\-Anwendung möglich, die für eine Version der Laufzeit erstellt wird, um auf jede andere Version ausgeführt, die die erforderliche Funktionalität bereitstellt.  
  
 Um dies zu erreichen, erstellen Sie eine app.config\-Datei bereit die Laufzeitversionsinformationen im `supportedRuntime`\-Tag enthält.  
  
 Zur Laufzeit muss die Datei app.config den Namen des Formulars *filename.ext*.config haben, an *filename.ext* der Name der ausführbaren Datei ist, die die Anwendung startet, und sie muss sich im gleichen Verzeichnis wie die ausführbare Datei befinden.  Wenn die Anwendung TestApp.exe lautet, würde die muss die app.config\-Datei.  
  
 Wenn Sie mehr als eine Laufzeitversion angeben, und die Anwendung auf einem Computer ausgeführt wird, der mehr als eine installierte Laufzeitversion hat, verwendet die Anwendung die erste Version, die in der Konfigurationsdatei angegeben und installiert ist.  
  
 Weitere Informationen finden Sie unter [How to: Configure an App to Target a .NET Framework Version](assetId:///5247b307-89ca-417b-8dd0-e8f9bd2f4717).  
  
 Um auf Version 1.0 oder Version 1.1 der CLR ausgeführt werden können, muss eine Anwendung die vom Visual C\+\+\-Compiler erstellt wird kompiliert werden mit [\/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md) verwendet.  
  
## Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)