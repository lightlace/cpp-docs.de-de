---
title: "Reiner und überprüfbarer Code (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ba218772bdedf772e995bb9289b18452d599e6c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="pure-and-verifiable-code-ccli"></a>Reiner und überprüfbarer Code (C++/CLI)
Bei der .NET-Programmierung unterstützt Visual C++ in Visual Studio 2017 die Erstellung von gemischten Assemblys mithilfe der [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption. Die **/CLR: pure** und **CLR: safe** Optionen sind ab Visual Studio 2015 als veraltet markiert und wird in einer zukünftigen Version des Compilers entfernt. Wenn der Code überprüfbar sein muss, empfehlen wir, ihn zu c# portieren.
  
## <a name="mixed-clr"></a>Gemischt (/clr)  
 Gemischte Assemblys (kompiliert mit **"/ CLR"**) enthalten sowohl unverwaltete als auch verwaltete Teile, sodass es möglich, dass sie .NET-Funktionen verwenden aber dennoch systemeigenen Code. Dadurch können Anwendungen und Komponenten für die Verwendung von .NET-Funktionen aktualisiert werden, ohne dass das gesamte Projekt neu geschrieben werden muss. Mithilfe von Visual C++ zum Mischen von verwaltetem und systemeigenem Code auf diese Weise wird die C++-Interop aufgerufen. Weitere Informationen finden Sie unter [gemischte (systemeigene und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md) und [einheitlichen als auch .NET Interoperabilität](../dotnet/native-and-dotnet-interoperability.md).  
  
  
Aufrufe aus verwalteten Assemblys systemeigener DLLs über P/Invoke werden kompiliert, aber möglicherweise ein Fehler zur Laufzeit abhängig von Sicherheitseinstellungen.  
  
Es gibt eine Codekonstellation, die kompiliert wird, obwohl dies eine unüberprüfbare Assembly zu Folge hat: Aufruf einer virtuellen Funktion durch eine Objektinstanz mit dem Bereichsauflösungsoperator.  Beispiel: `MyObj -> A::VirtualFunction();`.  
  
## <a name="see-also"></a>Siehe auch  
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
