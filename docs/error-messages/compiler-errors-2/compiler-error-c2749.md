---
title: Compiler-Fehler C2749 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2749
dev_langs:
- C++
helpviewer_keywords:
- C2749
ms.assetid: a81aef36-cdca-4d78-89d5-b72eff2500b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1738bdcc66e05512932fcd9029484dc55e3fc4a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236893"
---
# <a name="compiler-error-c2749"></a>Compiler-Fehler C2749 generiert
'Typ': kann nur ausgelöst oder abgefangen Handle für eine verwaltete Klasse mit/clr: safe  
  
 Bei Verwendung **/CLR: safe**, kann nur ausgelöst oder abgefangen einen Referenztyp darstellt.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2749 generiert:  
  
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