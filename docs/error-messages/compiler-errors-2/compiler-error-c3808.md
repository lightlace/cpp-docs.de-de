---
title: Compiler-Fehler C3808 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3808
dev_langs:
- C++
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 989f17e8f59afc6a04ed4101204053fc971c6a62
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3808"></a>Compilerfehler C3808
'Typ': eine Klasse mit dem ComImport-Attribut kann nicht Member "Member", nur abstrakte definieren oder Dllimport-Funktionen sind zulässig.  
  
 Ein Typ, der von abgeleiteten <xref:System.Runtime.InteropServices.ComImportAttribute>kann nicht definiert `member`.</xref:System.Runtime.InteropServices.ComImportAttribute>  
  
 Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 veraltet sind.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3808 generiert.  
  
```  
// C3808.cpp  
// compile with: /c /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 {  
   int f() {}   // C3808  
   virtual int g() abstract;   // OK  
  
   [DllImport("msvcrt.dll")]  
   int printf(System::String ^, int i);   // OK  
};  
```
