---
title: Compiler-Fehler C2753 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2753
dev_langs:
- C++
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
caps.latest.revision: 7
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
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 7d77c7fa0c8035f8bb3a9ef732880bce4253c25b
ms.contentlocale: de-de
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-error-c2753"></a>Compiler-Fehler C2753 generiert
"*Vorlage*": teilweiser Spezialisierung darf nicht Argumentliste für den primären Vorlage übereinstimmen.  
  
 Wenn die Vorlagenargumentliste die Parameterliste übereinstimmt, behandelt der Compiler ihn als die gleiche Vorlage an. Definieren die gleiche Vorlage zweimal ist nicht zulässig.  
  
## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird C2753 generiert und zeigt eine Möglichkeit, sie diesen Fehler beheben:  
  
```cpp  
// C2753.cpp  
// compile with: cl /c C2753.cpp
template<class T>  
struct A {};  
  
template<class T>  
struct A<T> {};   // C2753  
// try the following line instead  
// struct A<int> {};  
  
template<class T, class U, class V, class W, class X>  
struct B {};  
```
