---
title: Compilerwarnung C4958 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4958
dev_langs:
- C++
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 7deb92709adbb5a10148c092985e9a7c9f463c0c
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4958"></a>Compilerwarnung C4958
'Operation': Die Zeigerarithmetik kann nicht überprüft werden.  
  
 Bei Verwendung der Zeigerarithmetik wird ein nicht überprüfbares Image erstellt.  
  
 Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Diese Warnung wird als Fehler ausgegeben und kann deaktiviert werden, mit der [Warnung](../../preprocessor/warning.md) Pragmas oder der [/WD](../../build/reference/compiler-option-warning-level.md) -Compileroption.  
  
 Im folgenden Beispiel wird C4958 generiert:  
  
```  
// C4958.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
using namespace System;  
  
int main( ) {  
   Int32 arr[] = new Int32[10];  
   Int32* p = &arr[0];  
   p++;   // C4958  
}  
```  
  
 Der Compiler implementiert Arrayoperationen mit Zeigerarithmetik. Daher sind systemeigene Arrays nicht überprüfbar. Verwenden Sie stattdessen ein CLR-Array. Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C4958 generiert:  
  
```  
// C4958b.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
  
int main() {  
   int array[5];  
   array[4] = 0;   // C4958  
}  
```
