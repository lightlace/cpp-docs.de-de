---
title: Linkertoolfehler Lnk1301 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8646de5bb81120f6445e16b819b27da62ed9d5ec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039945"
---
# <a name="linker-tools-error-lnk1301"></a>Linkertoolfehler LNK1301

Clr-Module für LTCG gefunden, nicht kompatibel mit /LTCG:parameter

Ein mit "/ CLR" und "/ GL" kompilierten Modul wurde an den Linker zusammen mit einem der profilgesteuerten Optimierungen (PGO)-Parameter von "/ LTCG" übergeben.

Profilgesteuerte Optimierungen werden zu/CLR-Modulen nicht unterstützt.

Weitere Informationen finden Sie unter:

- [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (Link-Zeitcodegenerierung)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Kompilieren Sie nicht mit/CLR oder nicht mit einem der PGO-Parameter zu "/ LTCG" verknüpfen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK1301 generiert:

```
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```