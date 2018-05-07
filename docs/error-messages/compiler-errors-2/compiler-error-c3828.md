---
title: Compilerfehler C3828 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3828
dev_langs:
- C++
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adb016c164923e1ac6008e6318e39f8ac8632113
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3828"></a>Compilerfehler C3828
'Objekttyp': Positionierungsargumente nicht zulässig, während des Erstellens von Instanzen von verwalteten oder WinRTclasses  
  
 Wenn Sie ein Objekt des verwalteten oder WinRT-Typs zu erstellen, können keine Format für die Platzierung des Operators [Ref neue Gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) oder [neue](../../cpp/new-operator-cpp.md).  
  
 Im folgenden Beispiel wird C3828 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```