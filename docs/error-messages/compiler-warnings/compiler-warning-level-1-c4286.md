---
title: Compilerwarnung (Stufe 1) C4286 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4286
dev_langs:
- C++
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2dab6c5c28809108e178ec7792a68a570ece14ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277113"
---
# <a name="compiler-warning-level-1-c4286"></a>Compilerwarnung (Stufe 1) C4286
"Typ1": wurde aufgefangen durch Basisklasse ("Typ2") in Zeilennummer  
  
 Der angegebene Ausnahmetyp wird von einem vorherigen Handler behandelt. Der Typ für den zweiten Catch ist der Typ des ersten abgeleitet. Ausnahmen für eine Basisklasse fangen Sie Ausnahmen für eine abgeleitete Klasse.  
  
## <a name="example"></a>Beispiel  
  
```  
//C4286.cpp  
// compile with: /W1  
#include <eh.h>  
class C {};  
class D : public  C {};  
int main()  
{  
    try  
    {  
        throw "ooops!";  
    }  
    catch( C ) {}  
    catch( D ) {}  // warning C4286, D is derived from C  
}  
```