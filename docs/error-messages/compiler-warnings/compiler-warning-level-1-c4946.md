---
title: "Compilerwarnung (Stufe 1) C4946 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4946"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4946"
ms.assetid: b85cbef0-e053-4de6-9b14-7b0f82d40495
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerwarnung (Stufe 1) C4946
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

reinterpret\_cast wird zwischen verknüpften Klassen verwendet: 'Klasse1' und 'Klasse2'  
  
 Verwenden Sie nicht [reinterpret\_cast](../../cpp/reinterpret-cast-operator.md), die sich aufeinander Typen umzuwandeln.  Verwenden Sie stattdessen [static\_cast](../../cpp/static-cast-operator.md) oder für polymorphe Typen, dem [Der Operator dynamic\_cast](../../cpp/dynamic-cast-operator.md).  
  
 Standardmäßig ist diese Warnung aus.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Codebeispiel C4946 generiert:  
  
```  
// C4946.cpp  
// compile with: /W1  
#pragma warning (default : 4946)  
class a {  
public:  
   a() : m(0) {}  
   int m;  
};  
  
class b : public virtual a {  
};  
  
class b2 : public virtual a {  
};  
  
class c : public b, public b2 {  
};  
  
int main() {  
   c* pC = new c;  
   a* pA = reinterpret_cast<a*>(pC);   // C4946  
   // try the following line instead  
   // a* pA = static_cast<a*>(pC);  
}  
```