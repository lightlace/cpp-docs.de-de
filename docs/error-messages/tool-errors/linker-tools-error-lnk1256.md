---
title: Linkertoolfehler LNK1256
ms.date: 11/04/2016
f1_keywords:
- LNK1256
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
ms.openlocfilehash: bedf96262944d59737a39a942021cdec9445f3b8
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990942"
---
# <a name="linker-tools-error-lnk1256"></a>Linkertoolfehler LNK1256

Fehler bei ALINK-Operation: Ursache

Ein häufiger Grund für LNK1256 ist eine falsche Versionsnummer für eine Assembly. Der Wert 65535 ist für keinen Teil der Assemblyversionsnummer zulässig. Der gültige Bereich für die Assemblyversionen ist 0-65534.

LNK1256 kann auch entstehen, wenn ALINK den benannten Schlüsselcontainer nicht finden konnte. Löschen Sie den Schlüssel Container, und fügen Sie ihn mithilfe von [Sn. exe (Strong Name-Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool)erneut dem CSP-Namen (Strong Name) hinzu.

Ein weiterer Grund für LNK1256 ist ein Versionskonflikt zwischen dem Linker und Alink.dll. Dies kann durch eine fehlerhafte Installation von Visual Studio verursacht werden. Verwenden Sie **Programme und Funktionen** in der Windows-Systemsteuerung, um Visual Studio zu reparieren oder neu zu installieren.

Im folgende Beispiel wird LNK1256 generiert:

```cpp
// LNK1256.cpp
// compile with: /clr /LD
// LNK1256 expected
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];
public class CMyClass {
public:
   int value;
};
```
