---
title: Compilerwarnung (Stufe 4) C4564 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4564
dev_langs:
- C++
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f0cf68eb75d420a0d23c04687d4f9492910b53f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293672"
---
# <a name="compiler-warning-level-4-c4564"></a>Compilerwarnung (Stufe 4) C4564
Methode 'Methode' Klasse 'Klasse' definiert den nicht unterstützten Standardparameter 'Parameter'  
  
 Der Compiler hat eine Methode mit einem oder mehreren Parametern mit Standardwerten. Die Standardwerte für die Parameter wird ignoriert, wenn die Methode aufgerufen wird. Geben Sie explizit Werte für diese Parameter. Wenn Sie Werte für diese Parameter nicht explizit angeben, generiert der C++-Compiler einen Fehler.  
  
 Der angegebene die folgenden DLL-Datei erstellt, die mit Visual Basic ermöglicht die Standardparameter für Methodenargumente:  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 Und die folgenden C++-Beispiel, das die DLL-Datei erstellt, die mit Visual Basic verwendet,  
  
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