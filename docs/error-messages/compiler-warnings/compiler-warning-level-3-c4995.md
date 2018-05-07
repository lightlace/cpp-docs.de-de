---
title: Compilerwarnung (Stufe 3) C4995 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4995
dev_langs:
- C++
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c6bf1bbab4ee9a5a08a1376c91c6a7bba160625
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4995"></a>Compilerwarnung (Stufe 3) C4995
'Funktion': Name wurde als veraltet #pragma markiert  
  
 Der Compiler hat festgestellt, eine Funktion, die mit dem Pragma gekennzeichnet war [veraltet](../../preprocessor/deprecated-c-cpp.md). Die Funktion wird in zukünftigen Releases u. U. nicht mehr unterstützt. Sie können diese Warnung deaktivieren, mit der [Warnung](../../preprocessor/warning.md) Pragma (nachfolgendes Beispiel).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4995 generiert:  
  
```  
// C4995.cpp  
// compile with: /W3  
#include <stdio.h>  
  
// #pragma warning(disable : 4995)  
void func1(void)  
{  
    printf("\nIn func1");  
}  
  
int main()   
{  
    func1();  
    #pragma deprecated(func1)  
    func1();   // C4995  
}  
```