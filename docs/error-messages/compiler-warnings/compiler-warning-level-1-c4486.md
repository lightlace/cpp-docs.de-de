---
title: "Compilerwarnung (Stufe 1) C4486 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4486"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4486"
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Compilerwarnung (Stufe 1) C4486
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Eine private virtuelle Methode einer Verweisklasse oder einer Werteklasse sollte als 'sealed' markiert sein.  
  
 Da auf eine private virtuelle Memberfunktion einer verwalteten Klasse oder Struktur nicht zugegriffen werden kann und diese nicht überschrieben werden kann, sollte sie mit [sealed](../../windows/sealed-cpp-component-extensions.md) gekennzeichnet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C4486 generiert.  
  
```  
// C4486.cpp  
// compile with: /clr /c /W1  
ref class B {  
private:  
   virtual void f() {}   // C4486  
   virtual void f1() sealed {}   // OK  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird eine mögliche Verwendung einer privaten versiegelten virtuellen Funktion gezeigt.  
  
```  
// C4486_b.cpp  
// compile with: /clr /c  
ref class B {};  
  
ref class D : B {};  
  
interface class I {  
   B^ mf();  
};  
  
ref class E : I {  
private:  
   virtual B^ g() sealed = I::mf {  
      return gcnew B;  
   }  
  
public:  
   virtual D^ mf() {  
      return gcnew D;  
   }  
};  
```