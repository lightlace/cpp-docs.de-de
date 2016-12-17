---
title: "Compilerwarnung (Stufe 3) C4265"
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
  - "C4265"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4265"
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4265
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Die Klasse verfügt über virtuelle Funktionen, der Destruktor ist jedoch nicht virtuell  
  
 Wenn eine Klasse über virtuelle Funktionen, aber einen nicht virtuellen Destruktor verfügt, werden Objekte des Typs möglicherweise nicht ordnungsgemäß gelöscht, wenn eine Klasse durch einen Basisklassenzeiger gelöscht wird.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Beispiel wird C4265 generiert:  
  
```  
// C4265.cpp  
// compile with: /W3 /c  
#pragma warning(default : 4265)  
class B  
{  
public:  
   virtual void vmf();  
  
   ~B();  
   // try the following line instead  
   // virtual ~B();  
};   // C4265  
  
int main()  
{  
   B b;  
}  
```