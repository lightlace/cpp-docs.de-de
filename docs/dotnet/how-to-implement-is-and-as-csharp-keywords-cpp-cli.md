---
title: "Gewusst wie: Implementieren der C#-Schl&#252;sselw&#246;rter &quot;is&quot; und &quot;as&quot; (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "as (C#-Schlüsselwort) [C++]"
  - "is (C#-Schlüsselwort) [C++]"
ms.assetid: bc66c0d1-696b-480d-977c-5d9d1ad1ece6
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Implementieren der C#-Schl&#252;sselw&#246;rter &quot;is&quot; und &quot;as&quot; (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird dargestellt, wie die Funktionalität der C\#\-Schlüsselwörter `is` und `as` in Visual C\+\+ implementiert wird.  
  
 Weitere Informationen finden Sie unter [is](../Topic/is%20\(C%23%20Reference\).md) und [as](../Topic/as%20\(C%23%20Reference\).md).  
  
## Beispiel  
  
```  
// CS_is_as.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I {  
public:  
   void F();  
};  
  
ref struct C : public I {  
   virtual void F( void ) { }  
};  
  
template < class T, class U >   
Boolean isinst(U u) {  
   return dynamic_cast< T >(u) != nullptr;  
}  
  
int main() {  
   C ^ c = gcnew C();  
   I ^ i = safe_cast< I ^ >(c);   // is (maps to castclass in IL)  
   I ^ ii = dynamic_cast< I ^ >(c);   // as (maps to isinst in IL)  
  
   // simulate 'as':  
   Object ^ o = "f";  
   if ( isinst< String ^ >(o) )  
      Console::WriteLine("o is a string");  
}  
```  
  
  **o ist eine Zeichenfolge.**   
## Siehe auch  
 [Interoperabilität mit anderen .NET\-Sprachen](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)