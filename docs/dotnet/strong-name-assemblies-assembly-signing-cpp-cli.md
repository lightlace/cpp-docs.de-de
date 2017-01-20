---
title: "Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)"
ms.custom: na
ms.date: "12/14/2016"
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
  - ".NET Framework [C++], Signieren von Assemblys"
  - "Assemblys [C++]"
  - "Assemblys [C++], Signieren"
  - "Linker [C++], Signieren von Assemblys"
  - "Signieren von Assemblys"
  - "Assemblys mit starken Namen [C++]"
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema behandelt, wie Sie eine Assembly signieren können. Dies wird häufig auch als Vergeben eines starken Namens bezeichnet.  
  
## Hinweise  
 Wenn Sie mit Visual C\+\+ arbeiten, verwenden Sie die Linkeroptionen zum Signieren der Assembly, um Probleme im Zusammenhang mit den CLR\-Attributen zur Assemblysignierung zu vermeiden:  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 Einer der Gründe, nicht die Attribute zu verwenden, ist die Tatsache, dass der Schlüsselname in den Assemblymetadaten sichtbar ist. Dies kann ein Sicherheitsrisiko darstellen, falls der Dateiname vertrauliche Informationen enthält.  Außerdem macht der von der Visual C\+\+\-Entwicklungsumgebung verwendete Buildprozess den Schlüssel ungültig, mit dem die Assembly signiert wurde, wenn Sie CLR\-Attribute verwenden, um einer Assembly einen starken Namen zu geben, und anschließend ein Nachbearbeitungstool wie mt.exe auf die Assembly anwenden.  
  
 Wenn Sie über die Kommandozeile erstellen, Linkeroptionen verwenden, um die Assembly zu signieren, und dann ein Nachbearbeitungstool \(wie mt.exe\) ausführen, müssen Sie die Assembly mit sn.exe erneut signieren.  Alternativ können Sie nach dem Erstellen das Signieren hinauszögern und nach Ausführung des Nachbearbeitungstools die Signierung abschließen.  
  
 Wenn Sie beim Buildvorgang in der Entwicklungsumgebung die Signierungsattribute verwenden, können Sie die Assembly erfolgreich signieren, indem Sie in einem Postbuildereignis explizit sn.exe \([Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)\) aufrufen.  Weitere Informationen finden Sie unter [Angeben von Buildereignissen](../ide/specifying-build-events.md).  Durch die Verwendung von Attributen und einem Postbuildereignis können die Buildzeiten im Vergleich zu Vorgängen mit Linkeroptionen verkürzt werden.  
  
 Die folgenden Linkeroptionen unterstützen Assemblysignierung:  
  
-   [\/DELAYSIGN \(Assembly teilweise signieren\)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE \(Schlüsselcontainer oder Schlüsselpaar zum Signieren einer Assembly festlegen\)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER \(Schlüsselcontainer zum Signieren einer Assembly festlegen\)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Weitere Informationen zu starken Assemblys finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)