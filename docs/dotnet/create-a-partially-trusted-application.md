---
title: "Gewusst wie: Erstellen einer teilweise vertrauensw&#252;rdigen Anwendung durch Entfernen der Abh&#228;ngigkeit der CRT-Bibliotheks-DLL"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Teilweise vertrauenswürdige Anwendungen"
  - "Interop [C++], Teilweise vertrauenswürdige Anwendungen"
  - "Interoperabilität [C++], Teilweise vertrauenswürdige Anwendungen"
  - "Gemischte Assemblys [C++], Teilweise vertrauenswürdige Anwendungen"
  - "msvcm90[d].dll"
  - "Teilweise vertrauenswürdige Anwendungen [C++]"
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Erstellen einer teilweise vertrauensw&#252;rdigen Anwendung durch Entfernen der Abh&#228;ngigkeit der CRT-Bibliotheks-DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie eine teilweise vertrauenswürdige Common Language Runtime\-Anwendung mit [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] erstellt wird, indem die Abhängigkeit von msvcm90.dll aufgehoben wird.  
  
 Eine mit **\/clr** erstellte Visual C\+\+\-Anwendung ist von msvcm90.dll abhängig, die Teil der C\-Laufzeitbibliothek ist.  Wenn die Anwendung in einer teilweise vertrauenswürdigen Umgebung verwendet werden soll, erzwingt die CLR bestimmte Regeln für die Codezugriffssicherheit bezüglich der DLL.  Deshalb muss diese Abhängigkeit entfernt werden, da msvcm90.dll systemeigenen Code enthält und die Sicherheitsrichtlinien für den Codezugriff nicht entsprechend erzwungen werden können.  
  
 Wenn Ihre Anwendung keine Funktionen der C\-Laufzeitbibliothek verwendet und Sie die Abhängigkeit von dieser Bibliothek aus dem Code entfernen möchten, müssen Sie die Linkeroption **\/NODEFAULTLIB:msvcmrt.lib** verwenden und eine Verknüpfung mit ptrustm.lib oder ptrustmd.lib herstellen.  Diese Bibliotheken enthalten Objektdateien zur Initialisierung einer Anwendung sowie zur Aufhebung der Initialisierung, vom Initialisierungscode verwendete Ausnahmeklassen sowie Code zur verwalteten Ausnahmebehandlung.  Durch das Verknüpfen mit einer dieser Bibliotheken wird jede Abhängigkeit von msvcm90.dll. aufgehoben.  
  
> [!NOTE]
>  Die Reihenfolge der Aufhebung der Initialisierung der Assemblys unterscheidet sich möglicherweise bei Anwendungen, die die ptrust\-Bibliotheken verwenden.  Bei normalen Anwendungen werden die Assemblys i. d R., jedoch nicht garantiert, in der umgekehrten Reihenfolge entladen, in der sie geladen wurden.  Bei teilweise vertrauenswürdigen Anwendungen werden Assemblys in derselben Reihenfolge entladen, in der sie geladen werden.  Auch dies ist jedoch nicht garantiert der Fall.  
  
### So erstellen Sie eine teilweise vertrauenswürdige gemischte \(\/clr\) Anwendung  
  
1.  Um die Abhängigkeit von msvcm90.dll aufzuheben, müssen Sie für den Linker angeben, dass diese Bibliothek nicht einbezogen werden soll. Verwenden Sie dazu die Linkeroption **\/NODEFAULTLIB:msvcmrt.lib**.  Informationen dazu, wie dies mit der Visual Studio\-Entwicklungsumgebung oder programmgesteuert durchgeführt wird, finden Sie unter [\/NODEFAULTLIB \(Bibliotheken ignorieren\)](../build/reference/nodefaultlib-ignore-libraries.md).  
  
2.  Fügen Sie den Linkereingabeabhängigkeiten eine der ptrustm\-Bibliotheken hinzu.  Verwenden Sie ptrustm.lib, wenn Sie die Anwendung im Releasemodus erstellen.  Im Debugmodus verwenden Sie ptrustmd.lib.  Informationen dazu, wie dies mit der Visual Studio\-Entwicklungsumgebung oder programmgesteuert durchgeführt wird, finden Sie unter [.LIB\-Dateien als Linkereingabe](../build/reference/dot-lib-files-as-linker-input.md).  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Initialisierung gemischter Assemblys](../dotnet/initialization-of-mixed-assemblies.md)   
 [Bibliotheksunterstützung für verschiedene Assemblys](../dotnet/library-support-for-mixed-assemblies.md)   
 [\/link \(Optionen an Linker übergeben\)](../build/reference/link-pass-options-to-linker.md)   
 [Sicherheit in systemeigenem Code und .NET Framework\-Code](assetId:///bd61be84-c143-409a-a75a-44253724f784)