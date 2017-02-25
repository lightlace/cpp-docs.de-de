---
title: "Compilerwarnung (Stufe 4) C4516 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4516"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4516"
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4516
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::symbol': Zugriffsdeklarationen sind veraltet; using\-Deklarationen von Membern stellen eine bessere Alternative dar  
  
 Die ANSI C\+\+\-Kommission hat Zugriffsdeklarationen \(d. h., das Ändern der Zugriffsebene für einen in einer abgeleiteten Klasse enthaltenen Member, ohne das Schlüsselwort [using](../../cpp/using-declaration.md) zu verwenden\) zur überholten Praktik erklärt.  Zugriffsdeklarationen werden von zukünftigen C\+\+\-Versionen möglicherweise nicht mehr unterstützt.  
  
 Im folgenden Beispiel wird C4516 generiert:  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```