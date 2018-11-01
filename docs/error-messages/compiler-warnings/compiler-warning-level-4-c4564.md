---
title: Compilerwarnung (Stufe 4) C4564
ms.date: 11/04/2016
f1_keywords:
- C4564
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
ms.openlocfilehash: 1948bdec5367fa7943f5a0de4338fd4ecd6c6581
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526229"
---
# <a name="compiler-warning-level-4-c4564"></a>Compilerwarnung (Stufe 4) C4564

Methode 'Methode' Klasse 'Klasse' definiert den nicht unterstützten Standardparameter "Parameter"

Der Compiler hat eine Methode mit der eine oder mehrere Parameter mit Standardwerten. Die Standardwerte für die Parameter wird ignoriert, wenn die Methode aufgerufen wird. Geben Sie explizit Werte für diese Parameter. Wenn Sie Werte für diese Parameter nicht explizit angeben, generiert der C++-Compiler einen Fehler.

Angegebene die folgenden DLL-Datei mit Visual Basic erstellt wurden können die Standardparameter für Methodenargumente:

```
' C4564.vb
' compile with: vbc /t:library C4564.vb
Public class TestClass
   Public Sub MyMethod (a as Integer, _
                        Optional c as Integer=1)
   End Sub
End class
```

Und im folgenden C++-Beispiel, das die DLL-Datei erstellt, die mit Visual Basic verwendet

```
// C4564.cpp
// compile with: /clr /W4 /WX
#using <C4564.dll>

int main() {
   TestClass ^ myx = gcnew TestClass();   // C4564
   myx->MyMethod(9);
   // try the following line instead, to avoid an error
   // myx->MyMethod(9, 1);
}
```