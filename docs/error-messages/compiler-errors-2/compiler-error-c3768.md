---
title: Compiler-Fehler C3768 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
caps.latest.revision: 8
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
ms.openlocfilehash: cb9c1c3a41deb35e6aa82d3d77e61dfd4b15a7cb
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3768"></a>Compilerfehler C3768
Die Adresse einer virtuellen vararg-Funktion in reinem verwaltetem Code kann nicht übernommen werden.  
  
 Die **/CLR: pure** -Compileroption in Visual Studio 2015 veraltet ist.  
  
 Beim Kompilieren mit `/clr:pure`, Sie können nicht die Adresse einer virtuellen nutzen `vararg` Funktion.  
  
## <a name="example"></a>Beispiel  

 Im folgende Beispiel wird C3768 generiert:  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```
