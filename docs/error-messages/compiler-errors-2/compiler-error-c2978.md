---
title: Compilerfehler C2978 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2978
dev_langs:
- C++
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
caps.latest.revision: 6
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
ms.openlocfilehash: e34fc28dd4b4bae71f2244e8539d69f1b775303c
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2978"></a>Compilerfehler C2978
Syntaxfehler: 'Schlüsselwort1' oder 'Schlüsselwort2' wurde erwartet, der Typ 'Schlüsselwort3' wurde gefunden. Nichttypparameter werden für Generika nicht unterstützt.  
  
 Eine generische Klasse wurde falsch deklariert. Finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md)für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2978 generiert:  
  
```  
// C2978.cpp  
// compile with: /clr /c  
generic <ref class T>   // C2978  
// try the following line instead  
// generic <typename T>   // OK  
ref class Utils {  
   static void sort(T elems, size_t size);  
};  
  
generic <int>  
// try the following line instead  
// generic <class T>  
ref class Utils2 {  
   static void sort(T elems, size_t size);  
};  
```
