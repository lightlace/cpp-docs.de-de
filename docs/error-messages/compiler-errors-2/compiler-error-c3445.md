---
title: Compilerfehler Fehler C3445 | Microsoft Docs
ms.custom: 
ms.date: 04/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3445
dev_langs:
- C++
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
caps.latest.revision: 3
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
ms.openlocfilehash: c89d7f1f13829422a330960ac319531fc551fb97
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3445"></a>Compilerfehler Fehler C3445
Copy-Liste-Initialisierung von "*Typ*' können keine expliziten Konstruktor  
  
Gemäß dem ISO C ++ 17-standard der Compiler ist erforderlich, um einen expliziten Konstruktor für die Auflösung von funktionsüberladungen im kopierinitialisierung-Liste sollten allerdings muss einen Fehler wird ausgelöst, wenn Sie diese Überladung tatsächlich ausgewählt wird.  
  
Ab Visual Studio 2017, sucht der Compiler Fehler im Zusammenhang mit objekterstellung mithilfe einer Initialisiererliste, die von Visual Studio 2015 nicht gefunden wurden. Dieser Fehler können zu abstürzt oder nicht definiertes Verhalten zur Laufzeit führen.

## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3445 generiert.  
  
```cpp  
// C3445.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of 
                      //     'A' cannot use an explicit constructor
}
```  
  
Um den Fehler zu beheben, verwenden Sie stattdessen direkte Initialisierung:  
  
```cpp  
// C3445b.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1{ 1 };
}  
```  
  
