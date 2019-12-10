---
title: Linkertoolfehler LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: c56b2eb86c7605fb3330d7b1bb01e3235466ede6
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990964"
---
# <a name="linker-tools-error-lnk1237"></a>Linkertoolfehler LNK1237

während der Codegenerierung hat der Compiler einen Verweis auf Symbol ' Symbol ' eingeführt, das in Modul ' Module ' definiert ist, das mit/GL kompiliert

Während der Codegenerierung sollte der Compiler keine Symbole einführen, die später in Definitionen kompiliert werden, die **/GL**kompiliert wurden. `symbol` ist ein Symbol, das in eine mit **/GL**kompilierte Definition eingeführt und später aufgelöst wurde.

Weitere Informationen finden Sie unter [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).

Um Linkertoolfehler LNK1237 aufzulösen, kompilieren Sie das Symbol nicht mit **/GL** , oder verwenden Sie [/include (Symbol Verweise erzwingen)](../../build/reference/include-force-symbol-references.md) , um einen Verweis auf das Symbol zu erzwingen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird Linkertoolfehler LNK1237 generiert. Um diesen Fehler zu beheben, initialisieren Sie das Array nicht in LNK1237_a. cpp, und fügen Sie **/include: __chkstk** dem Link-Befehl hinzu.

```cpp
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```cpp
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```
