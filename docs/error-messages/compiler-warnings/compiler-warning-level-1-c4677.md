---
title: Compilerwarnung (Stufe 1) C4677 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4677
dev_langs: C++
helpviewer_keywords: C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7af724ad56c3a84ffb8ef48e13d14bee97db14df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4677"></a>Compilerwarnung (Stufe 1) C4677
'Funktion': Signatur des nicht privaten Members enthält den privaten Assemblytyp 'Private_type'  
  
 Ein Typ, der öffentliche Zugriff außerhalb der Assembly verwendet einen Typ, der privaten Zugriff außerhalb der Assembly enthält. Eine Komponente, die auf den Typ der öffentliche Assemblyzugriff verweist ist nicht möglich, den Typ dieses Element oder Mitglieder, die auf den privaten Assemblytyp verweisen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4677 generiert.  
  
```  
// C4677.cpp  
// compile with: /clr /c /W1  
delegate void TestDel();  
public delegate void TestDel2();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;   // C4677  
   static event TestDel2^ MyClass_Event2;   // OK  
};  
```