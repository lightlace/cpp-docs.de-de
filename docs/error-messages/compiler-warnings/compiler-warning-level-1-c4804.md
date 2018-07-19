---
title: Compilerwarnung (Stufe 1) C4804 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4804
dev_langs:
- C++
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 677899230b2475c80f9bdd461a0c79740c4d3bec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286980"
---
# <a name="compiler-warning-level-1-c4804"></a>Compilerwarnung (Stufe 1) C4804
'Operation': unsichere Verwendung des Typs "Bool", Vorgang  
  
 Diese Warnung gilt für bei der Verwendung einer `bool` Variable oder ein Wert in der erwarteten Weise. C4804 wird beispielsweise generiert, wenn Sie Operatoren wie z. B. der negativen unäre Operator verwenden (**-**) oder dem Komplementoperator (`~`). Der Compiler wertet den Ausdruck.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4804 generiert:  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```