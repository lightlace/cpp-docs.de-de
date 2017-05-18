---
title: Compilerwarnung C4957 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4957
dev_langs:
- C++
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8eb7283942a8a89fc3322983c41c68082b6c5cee
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4957"></a>Compilerwarnung C4957
'CAST' : Die explizite Umwandlung von 'cast_from' in 'cast_to' kann nicht überprüft werden  
  
 Eine Umwandlung ergibt ein nicht überprüfbares Image.  
  
 Einige Umwandlungen sind sicher (z. B. eine `static_cast` die benutzerdefinierte Umwandlungen auslöst, und eine `const_cast`). Ein ["safe_cast"](../../windows/safe-cast-cpp-component-extensions.md) wird sichergestellt, dass zum Erzeugen von überprüfbarem Code.  
  
 Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Diese Warnung wird als Fehler ausgegeben und kann deaktiviert werden, mit der [Warnung](../../preprocessor/warning.md) Pragmas oder der [/WD](../../build/reference/compiler-option-warning-level.md) -Compileroption.  
  
 Im folgenden Beispiel wird C4957 generiert:  
  
```  
// C4957.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4957 )  
using namespace System;  
int main() {  
   Object ^ o = "Hello, World!";  
   String ^ s = static_cast<String^>(o);   // C4957  
   String ^ s2 = safe_cast<String^>(o);   // OK  
}  
```
