---
title: 'Vorgehensweise: Erstellen einer teilweise vertrauenswürdigen Anwendung (C + c++ / CLI) | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a4a0a4b8b1045a9107158c6e67ecdfa7939b6a08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Gewusst wie: Erstellen einer teilweise vertrauenswürdigen Anwendung durch Entfernen der Abhängigkeit der CRT-Bibliotheks-DLL
In diesem Thema wird erläutert, wie zum Erstellen einer teilweise vertrauenswürdigen Common Language Runtime-Anwendung, indem Sie in Visual C++ Abhängigkeit von msvcm90.dll aufgehoben wird.  
  
 Eine Visual C++-Anwendung mit erstellten **"/ CLR"** weist eine Abhängigkeit von msvcm90.dll abhängig, die Teil der C-Laufzeitbibliothek ist. Wenn Sie Ihre Anwendung in einer teilweise vertrauenswürdigen Umgebung verwendet werden soll, wird die CLR bestimmte Regeln für die Codezugriffssicherheit auf die DLL erzwungen. Aus diesem Grund ist es erforderlich sein, diese Abhängigkeit entfernt werden, da msvcm90.dll systemeigenen Code enthält und darauf nicht Codezugriff-Sicherheitsrichtlinie erzwungen werden.  
  
 Wenn Ihre Anwendung keine Funktionen der C-Laufzeitbibliothek verwendet und die Abhängigkeit von dieser Bibliothek aus dem Code entfernen möchten, müssen Sie verwenden die **/NODEFAULTLIB:msvcmrt.lib** (Linkeroption) und Verknüpfen mit ptrustm.lib oder ptrustmd.lib. Diese Bibliotheken enthalten Objektdateien für Initialisierung und zur Aufhebung der Anwendungsfehler, Ausnahmeklassen von Initialisierungscode verwendet, und verwalteten Code für die Ausnahmebehandlung. In einer dieser Bibliotheken verknüpfen, wird eine Abhängigkeit von msvcm90.dll entfernt.  
  
> [!NOTE]
>  Die Reihenfolge der Assembly zur Aufhebung unterscheiden sich für Anwendungen, die die Ptrust-Bibliotheken verwenden. Für normale Anwendungen werden Assemblys in der Regel entladen in umgekehrter Reihenfolge, die sie geladen werden, dies wird jedoch nicht garantiert. Für teilweise vertrauenswürdige Anwendungen werden die Assemblys in der Regel in der gleichen Reihenfolge entladen geladen sind. Dies ist zudem nicht gewährleistet.  
  
### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Erstellung einer teilweise vertrauenswürdigen gemischt (/ Clr) Anwendung  
  
1.  Um die Abhängigkeit von msvcm90.dll zu entfernen, geben Sie an den Linker nicht auf diese Bibliothek enthalten die **/NODEFAULTLIB:msvcmrt.lib** (Linkeroption). Informationen zum dazu verwenden Sie die Entwicklungsumgebung von Visual Studio oder programmgesteuert, finden Sie unter [/NODEFAULTLIB (Bibliotheken ignorieren)](../build/reference/nodefaultlib-ignore-libraries.md).  
  
2.  Fügen Sie eine der Bibliotheken Ptrustm den Linker-Eingabe-Abhängigkeiten hinzu. Verwenden Sie ptrustm.lib, wenn Sie Ihre Anwendung im Releasemodus erstellen. Verwenden Sie für den Debugmodus ptrustmd.lib. Informationen zum dazu verwenden Sie die Entwicklungsumgebung von Visual Studio oder programmgesteuert, finden Sie unter [. LIB-Dateien als Linkereingabe](../build/reference/dot-lib-files-as-linker-input.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (systemeigene und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Initialisierung gemischter Assemblys](../dotnet/initialization-of-mixed-assemblies.md)   
 [Bibliotheksunterstützung für gemischte Assemblys](../dotnet/library-support-for-mixed-assemblies.md)   
 [/link (Optionen an Linker übergeben)](../build/reference/link-pass-options-to-linker.md)   
