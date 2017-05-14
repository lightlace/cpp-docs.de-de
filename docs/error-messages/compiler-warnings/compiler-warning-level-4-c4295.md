---
title: Compilerwarnung (Stufe 4) C4295 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: b831b8e7b838ef25679d49a132c66d4b378fdcd7
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4295"></a>Compilerwarnung (Stufe 4) C4295
  
> "*Array*': Array ist zu klein, um ein abschließendes Nullzeichen enthalten.  
  
 Ein Array wurde initialisiert, aber das letzte Zeichen im Array ist nicht Null; Zugreifen auf das Array kann zu unerwarteten Ergebnissen führen.  
  
## <a name="example"></a>Beispiel  
  
 Im folgenden Beispiel wird C4295 generiert. Um dieses Problem zu beheben, konnten Sie deklarieren die Arraygröße größer, um eine terminierende aufzunehmen null aus dem Initialisierer.  
  
```C  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```
