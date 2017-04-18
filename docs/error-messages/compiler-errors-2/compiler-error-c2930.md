---
title: Compilerfehler C2930 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2930
dev_langs:
- C++
helpviewer_keywords:
- C2930
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4cb9cdb0a171e9132eb4f3381d568c9ca0f03752
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2930"></a>Compilerfehler C2930
'Klasse': 'Typ-Klassen-ID' wird als Enumerator von 'Enumerationsbezeichner' neu definiert.  
  
 Eine generische oder Vorlagenklasse kann nicht als Member einer Enumeration verwendet werden.  
  
 Dieser Fehler kann dadurch verursacht werden, dass geschweifte Klammern nicht korrekt übereinstimmen.  
  
 Im folgenden Beispiel wird C2930 generiert:  
  
```  
// C2930.cpp  
// compile with: /c  
template<class T>   
class x{};  
enum SomeEnum { x };   // C2930  
  
class y{};  
enum SomeEnum { y };  
```  
  
 C2930 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2930c.cpp  
// compile with: /clr /c  
generic<class T>   
ref struct GC {};  
enum SomeEnum { GC };   // C2930  
  
ref struct GC2 {};  
enum SomeEnum2 { GC2 };  
```
