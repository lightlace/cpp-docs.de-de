---
title: "How to: Declare Value Types with the interior_ptr Keyword (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ptr keyword"
  - "value types, declaring"
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Declare Value Types with the interior_ptr Keyword (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`interior_ptr` kann mit einem Werttyp verwendet werden.  
  
> [!IMPORTANT]
>  Diese Sprachfunktion wird durch die **\/clr**\-Compileroption, jedoch nicht durch die **\/ZW**\-Compileroption unterstützt.  
  
## Beispiel  
  
### **Beschreibung**  
 Im Folgenden [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] \- Beispiel zeigt, wie `interior_ptr` mit einem Werttyp verwendet.  
  
### Code  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### Ausgabe  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## Beispiel  
  
### **Beschreibung**  
 In einen Werttyp ergibt der `this` Zeiger zu einem interior\_ptr aus.  
  
 Im Text einer nicht statischen Memberfunktion eines Werttyps `V` wird, `this` ein Ausdruck vom Typ `interior_ptr<V>`, dessen Wert die Adresse des Objekts ist, für das die Funktion aufgerufen wird.  
  
### Code  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## Beispiel  
  
### **Beschreibung**  
 Das folgende Beispiel zeigt, wie dem Adressoperator mit statischen Member verwendet.  
  
 Die Adresse eines statischen Visual C\+\+\-Typmembers ergibt einen systemeigenen Zeiger.  Die Adresse eines statischen Werttypmembers ist ein verwalteter Zeiger, da Werttypmember auf dem Laufzeitheap belegten Speicherplatz wird und vom Garbage Collector verschoben werden kann.  
  
### Code  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### Ausgabe  
  
```  
22  
23  
hello  
```  
  
## Siehe auch  
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)