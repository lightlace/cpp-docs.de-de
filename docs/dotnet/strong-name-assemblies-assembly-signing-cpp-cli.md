---
title: Assemblys mit starken Namen (Assemblysignierung) (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d7ae911d2572a35ee8dbb21d5484b4679b64c4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169191"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)
In diesem Thema wird erläutert, wie Sie die Assembly, die genannte erteilen der Assembly einen starken Namen signieren können.  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung von Visual C++ verwenden Sie Linkeroptionen zum Signieren der Assembly, um Probleme im Zusammenhang mit der CLR-Attribute für das Signieren von Assemblys zu vermeiden:  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 Gründe für die nicht mit den Attributen für die Tatsache, dass der Schlüsselname in Metadaten der Assembly sichtbar, der ein Sicherheitsrisiko sein kann ist, wenn der Dateiname vertrauliche Informationen enthält. Darüber hinaus wird des Build-Prozesses, die von der Visual C++-Entwicklungsumgebung verwendet den Schlüssel ungültig, mit dem die Assembly signiert wird, wenn Sie die CLR-Attribute verwenden, um einer Assembly einen starken Namen zuzuweisen, und Sie dann auf die Assembly ein Nachbearbeitung Tools wie mt.exe führen.  
  
 Wenn Sie in der Befehlszeile erstellen, Linkeroptionen zum Signieren der Assembly verwendet, und Sie dann ein entsprechendes nachträglich Tool (z. B. mt.exe führen), müssen Sie die Assembly mit sn.exe erneut signieren. Alternativ können Sie Sie erstellen und verzögerte Signierung der Assembly und nach dem Ausführen der Nachbearbeitung Verwaltungstools, führen Sie die Signatur.  
  
 Wenn Sie die Signatur Attribute beim Buildvorgang in der Entwicklungsumgebung verwenden, können Sie die Assembly erfolgreich signieren, durch explizites Aufrufen von sn.exe ([Sn.exe (Strong Name-Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool)) in ein Postbuildereignis. Weitere Informationen finden Sie unter [Festlegen von Buildereignissen](../ide/specifying-build-events.md). Buildzeiten können kleiner sein, wenn Sie Attribute und ein Postbuildereignis, im Vergleich zur Verwendung der Optionen des Linkers verwenden.  
  
 Die folgenden Optionen des Linkers unterstützen Assemblysignierung:  
  
-   [/DELAYSIGN (Assembly teilweise signieren)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYFILE (Schlüssel oder Schlüsselpaar zum Signieren einer Assembly festlegen)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/KEYCONTAINER (Schlüsselcontainer zum Signieren einer Assembly festlegen)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Weitere Informationen zu starken Assemblys finden Sie unter [erstellen und Verwenden von Assemblys](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).  
  
## <a name="see-also"></a>Siehe auch  
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)