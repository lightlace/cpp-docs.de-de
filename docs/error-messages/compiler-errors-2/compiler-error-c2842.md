---
title: Compilerfehler C2842 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe0a95edfa484eb8606b914424e52483c4c1c52d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2842"></a>Compilerfehler C2842
„Klasse“: Ein verwalteter oder WinRT-Typ kann keinen eigenen „operator new“- oder „operator delete“-Operator definieren.  
  
 Können eigene definieren ** new-Operator oder **Delete-Operator** speicherbelegung auf dem systemeigenen Heap zu verwalten. Verweisklassen können diese Operatoren jedoch nicht definieren, da sie nur dem verwalteten Heap zugewiesen sind.  

  
 Weitere Informationen finden Sie unter [benutzerdefinierte Operatoren (C + c++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2842 generiert.  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
