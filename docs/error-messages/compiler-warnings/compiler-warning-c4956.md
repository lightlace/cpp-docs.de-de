---
title: Compilerwarnung C4956 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: 9
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
ms.openlocfilehash: 782735be55c043482679740afa9571ba7b29dfc4
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4956"></a>Compilerwarnung C4956
'typ': Dieser Typ ist nicht überprüfbar  
  
 Diese Warnung wird generiert, wenn [/CLR: safe](../../build/reference/clr-common-language-runtime-compilation.md) angegeben ist und der Code enthält einen Typ, der nicht überprüfbar ist.  
  
 Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Diese Warnung wird als Fehler ausgegeben und kann deaktiviert werden, mit der [Warnung](../../preprocessor/warning.md) Pragmas oder der [/WD](../../build/reference/compiler-option-warning-level.md) -Compileroption.  
  
 Im folgenden Beispiel wird C4956 generiert:  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```
