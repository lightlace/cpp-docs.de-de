---
title: "Compilerfehler C3831"
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
  - "C3831"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3831"
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3831
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': 'Klasse' kann keinen festen Datenmember oder eine Memberfunktion aufweisen, die einen festen Zeiger zurückgibt  
  
 [pin\_ptr \(C\+\+\/CLI\)](../../windows/pin-ptr-cpp-cli.md) oder [\_\_pin](../../misc/pin.md) wurde falsch verwendet.  
  
 Im folgenden Beispiel wird C3831 generiert:  
  
```  
// C3831a.cpp  
// compile with: /clr  
ref class Y  
{  
public:  
   int i;  
};  
  
ref class X  
{  
   pin_ptr<int> mbr_Y;   // C3831  
   int^ mbr_Y2;   // OK  
};  
  
int main() {  
   Y y;  
   pin_ptr<int> p = &y.i;  
}  
```  
  
 Im folgenden Beispiel wird C3831 generiert:  
  
```  
// C3831b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class Y  
{  
};  
  
__gc class X  
{  
   Y __pin * mbr_Y;   // C3831  
   Y * mbr_Y2;   // OK  
  
   Y __pin * mf_Y()  // C3831  
   {  
      Y __pin * pY = new Y();  
      return pY;  
   }  
  
   Y * mf_Y2()   // OK  
   {  
      Y * pY = new Y();  
      return pY;  
   }  
};  
```