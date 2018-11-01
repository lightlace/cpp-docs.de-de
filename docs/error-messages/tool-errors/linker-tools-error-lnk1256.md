---
title: Linkertoolfehler LNK1256
ms.date: 11/04/2016
f1_keywords:
- xml
- LNK1256
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
ms.openlocfilehash: 9d969d1e5bbae92ed49747f761c1b89d1910d4e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492863"
---
# <a name="linker-tools-error-lnk1256"></a>Linkertoolfehler LNK1256

Fehler bei ALINK-Operation: Ursache

Ein häufiger Grund für LNK1256 ist eine falsche Versionsnummer für eine Assembly. Der Wert 65535 ist für keinen Teil der Assemblyversionsnummer zulässig. Der gültige Bereich für Assemblyversionen ist 0 – 65534.

LNK1256 kann auch entstehen, wenn ALINK den benannten Schlüsselcontainer nicht finden konnte. Den Schlüsselcontainer löschen und erneut hinzufügen, CSP für starke Namen mit [Sn.exe (Strong Name Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool).

Ein weiterer Grund für LNK1256 ist ein Versionskonflikt zwischen dem Linker und Alink.dll. Dies kann durch eine fehlerhafte Installation von Visual Studio verursacht werden. Verwendung **Programme und Funktionen** in der Windows-Systemsteuerung zu reparieren oder installieren Sie Visual Studio.

Im folgende Beispiel wird LNK1256 generiert:

```
// LNK1256.cpp
// compile with: /clr /LD
// LNK1256 expected
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];
public class CMyClass {
public:
   int value;
};
```