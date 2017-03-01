---
title: Compiler-Fehler C3846 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3846
dev_langs:
- C++
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 04807182611beed23bf388d1f42a4fba0a3acea7
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3846"></a>Compilerfehler C3846
'Symbol': Symbol aus "assembly2" kann nicht importiert werden: 'Symbol' wurde bereits von einer anderen Assembly 'assembly1' importiert  
  
 Ein Symbol konnte nicht aus einer referenzierten Assembly importiert werden, da sie zuvor aus einer referenzierten Assembly importiert wurde.  
  
## <a name="example"></a>Beispiel
Im folgende Beispiel wird C3846 generiert:  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 Und kompilieren Sie diese:  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  

