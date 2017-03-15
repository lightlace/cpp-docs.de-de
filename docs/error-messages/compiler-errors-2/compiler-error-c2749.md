---
title: "Compilerfehler C2749 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2749"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2749"
ms.assetid: a81aef36-cdca-4d78-89d5-b72eff2500b2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2749
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Ein Handle einer verwalteten Klasse kann nur mit \/clr:safe ausgelöst oder abgefangen werden  
  
 Wenn **\/clr:safe** verwendet wird, kann ein Referenztyp nur ausgelöst oder abgefangen werden.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2749 generiert:  
  
```  
// C2749.cpp  
// compile with: /clr:safe  
ref struct MyStruct {  
public:  
   int i;  
};  
  
int main() {  
   MyStruct ^x = gcnew MyStruct;  
  
   // Delete the following 4 lines to resolve.  
   try {   
      throw (1);   // C2749  
   }  
   catch(int){}  
  
   // OK  
   try {  
      throw (x);  
   }  
   catch(MyStruct ^){}   
}  
```