---
title: Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
ms.openlocfilehash: 762c95c3ecc60995e8d0e6f9e4f7bc95d179c26f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747500"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)

In diesem Thema wird erläutert, wie Sie die Assembly, die genannte vergeben Ihrer Assembly einen starken Namen signieren können.

## <a name="remarks"></a>Hinweise

Bei der Verwendung von Visual C++ verwenden Sie Optionen des Linkers, um die Assembly zur Vermeidung von Problemen im Zusammenhang mit der CLR-Attribute für das Signieren der Assembly zu signieren:

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

Gründe für die Verwendung nicht die Attribute enthalten, die Tatsache, dass der Schlüsselname in der Metadaten einer Assembly sichtbar, die ein Sicherheitsrisiko darstellen können ist, wenn der Dateiname, vertrauliche Informationen enthält. Darüber hinaus wird der Buildprozess, der von der Visual C++-Entwicklungsumgebung verwendet den Schlüssel ungültig, mit dem die Assembly signiert wird, wenn Sie die CLR-Attribute verwenden, um einer Assembly einen starken Namen zuzuweisen, und Sie dann auf die Assembly ein nachträglich verarbeitetes Tool wie mt.exe führen.

Wenn Sie in der Befehlszeile erstellen, verwenden Sie die Optionen des Linkers zum Signieren der Assembly, und Sie dann ein nachträglich verarbeitetes Tool (z. B. mt.exe führen), müssen Sie die Assembly mit sn.exe erneut signieren. Sie können alternativ erstellen und verzögerte Signierung der Assembly und nach der Ausführung Nachbearbeitung Tools durchführen, das Signieren.

Wenn Sie die Signierung Attribute beim Entwickeln in der Entwicklungsumgebung verwenden, können Sie die Assembly erfolgreich signieren, durch explizites Aufrufen von sn.exe ([Sn.exe (Strong Name Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool)) in ein Postbuildereignis. Weitere Informationen finden Sie unter [Specifying Build Events (Angeben von Buildereignissen)](../ide/specifying-build-events.md). Buildzeiten können kleiner sein, wenn Sie Attribute und ein Postbuildereignis, im Vergleich zur Verwendung der Optionen des Linkers verwenden.

Die folgenden Optionen des Linkers Signieren von Assemblys zu unterstützen:

- [/DELAYSIGN (Assembly teilweise signieren)](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE (Schlüssel oder Schlüsselpaar zum Signieren einer Assembly festlegen)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER (Schlüsselcontainer zum Signieren einer Assembly festlegen)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Weitere Informationen zu starken Assemblys finden Sie unter [erstellen und Assemblys mit starkem Namen](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
