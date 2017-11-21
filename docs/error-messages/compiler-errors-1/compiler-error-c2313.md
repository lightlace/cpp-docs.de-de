---
title: Compilerfehler C2313 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2313
dev_langs: C++
helpviewer_keywords: C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fe00bfe9ec265da9aa2cb3db76f32107dfe0c03a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2313"></a>Compilerfehler C2313
'Typ1': wurde aufgefangen durch Verweis ('Typ2') in Zeile  
  
 Der Ausnahmetyp verfügt über zwei Handler. Der Verweis für den zweiten Catch ist ein Verweis auf den Typ des ersten Catch.  
  
 Im folgenden Beispiel wird C2313 generiert:  
  
```  
// C2313.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
    try {  
        throw "ooops!";  
    }  
    catch( C& ) {}  
    catch( C ) {}   // C2313  
}  
```