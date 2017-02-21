---
title: "Compilerwarnung (Stufe 4) C4623 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4623"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4623"
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 4) C4623
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'`derived class`': Der Standardkonstruktor wurde implizit als gelöscht definiert, da ein Basisklassen\-Standardkonstruktor nicht zugreifbar ist oder gelöscht wurde.  
  
 Auf einen Konstruktor konnte nicht in einer Basisklasse zugegriffen werden und ein Konstruktor wurde nicht für die abgeleitete Klasse generiert.  Jeder Versuch, ein Objekt dieses Typs auf dem Stapel zu erstellen, verursacht einen Compilerfehler.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4623 generiert.  
  
```  
// C4623.cpp  
// compile with: /W4  
#pragma warning(default : 4623)  
class B {  
   B();  
};  
  
class C {  
public:  
   C();  
};  
  
class D : public B {};   // C4623 - to fix, make B's constructor public  
class E : public C {};   // OK - class C constructor is public  
  
int main() {  
   // D d;  will cause an error  
}  
```