---
title: "Compilerwarnung (Stufe 1) C4677"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4677"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4677"
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4677
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Signatur des nicht privaten Members enthält eine Assembly mit dem privaten Typ 'private\_type'  
  
 Ein Typ, der außerhalb der Assembly öffentliche Zugriffe unterstützt, verwendet einen Typ, der außerhalb der Assembly über privaten Zugriff verfügt.  Eine Komponente, die auf den öffentlichen Assemblytyp verweist, ist nicht in der Lage, den bzw. die Typmember zu verwenden, die auf den privaten Typ der Assembly verweisen.  
  
## Beispiel  
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