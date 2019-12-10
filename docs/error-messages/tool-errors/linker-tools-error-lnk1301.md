---
title: Linkertoolfehler LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: fe64eecfbc9fed57c3748afd5804b76d6e4284a4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990941"
---
# <a name="linker-tools-error-lnk1301"></a>Linkertoolfehler LNK1301

LTCG CLR-Module gefunden, nicht kompatibel mit/LTCG: Parameter

Ein Modul, das mit/CLR und/GL kompiliert wurde, wurde zusammen mit einem der Parameter für die Profil gesteuerte Optimierung (PGO) von/LTCG. an den Linker übergeben.

Profil gesteuerte Optimierungen werden für/CLR-Module nicht unterstützt.

Weitere Informationen finden Sie unter: .

- [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (Link-Zeitcodegenerierung)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Profilgesteuerte Optimierungen](../../build/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Nicht mit/clr kompilieren oder nicht mit einem der PGO-Parameter für/LTCG. verknüpfen

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird Linkertoolfehler LNK1301 generiert:

```cpp
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```
