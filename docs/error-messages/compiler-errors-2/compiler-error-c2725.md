---
title: Compilerfehler Fehler C2725 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2725
dev_langs: C++
helpviewer_keywords: C2725
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dbf3a0e84f3cdf6b2ab9e42690cb8bc80f3d2201
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2725"></a>Compilerfehler Fehler C2725
'exception': Auslösen oder Erfassen eines verwalteten oder WinRT-Objekts nach Wert oder Verweis nicht möglich  
  
 Der Typ einer verwalteten oder WinRT-Ausnahme war falsch.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2725 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2725.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
};  
  
int main() {  
   R % r1 = *gcnew R;  
   throw r1;   // C2725  
  
   R ^ r2 = gcnew R;  
   throw r2;   // OK     
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2725 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2725b.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   try {}  
   catch( System::Exception%) {}   // C2725  
   // try the following line instead  
   // catch( System::Exception ^e) {}  
}  
```  
