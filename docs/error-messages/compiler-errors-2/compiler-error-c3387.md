---
title: Compilerfehler C3387 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3387
dev_langs:
- C++
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5469088b6707faa31e1d49157dcbc9991ffb7060
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3387"></a>Compilerfehler C3387
'Member': __declspec(dllexport) /\__declspec(dllimport) kann nicht auf einen Member eines verwalteten oder WinRT-Typ angewendet werden  
  
 Die `dllimport` und [Dllexport](../../cpp/dllexport-dllimport.md) `__declspec` Modifizierer sind nicht gültig für Member eines verwalteten oder WinRT-Typs.  
  
 Im folgenden Beispiel wird C3387 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3387a.cpp  
// compile with: /clr /c  
ref class X2 {  
   void __declspec(dllexport) mf() {   // C3387  
   // try the following line instead  
   // void mf() {  
   }  
};  
```