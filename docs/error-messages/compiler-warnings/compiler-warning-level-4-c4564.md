---
title: Compilerwarnung (Stufe 4) C4564
ms.date: 11/04/2016
f1_keywords:
- C4564
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
ms.openlocfilehash: 042eab1c125f2b98fd36257dfd8971262015ab92
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990675"
---
# <a name="compiler-warning-level-4-c4564"></a>Compilerwarnung (Stufe 4) C4564

die Methode "Method" der Klasse "Class" definiert den nicht unterstützten Standardparameter "Parameter".

Der Compiler hat eine Methode mit einem oder mehreren Parametern mit Standardwerten erkannt. Die Standardwerte für die Parameter werden ignoriert, wenn die-Methode aufgerufen wird. Geben Sie Werte für diese Parameter explizit an. Wenn Sie für diese Parameter nicht explizit Werte angeben, generiert der C++ Compiler einen Fehler.

Wenn die folgende dll mit Visual Basic erstellt wird, die Standardparameter für Methodenargumente zulässt:

```vb
' C4564.vb
' compile with: vbc /t:library C4564.vb
Public class TestClass
   Public Sub MyMethod (a as Integer, _
                        Optional c as Integer=1)
   End Sub
End class
```

Und im folgenden C++ Beispiel, in dem die mit Visual Basic erstellte DLL verwendet wird.

```cpp
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
