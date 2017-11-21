---
title: Compilerfehler C3539 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3539
dev_langs: C++
helpviewer_keywords: C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 03283217be6aabbf216e2e60ad47abfc01a961d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3539"></a>Compilerfehler C3539
'Typ': ein Vorlagenargument nicht mit einem Typ, der "auto" enthält  
  
 Die angegebene Vorlage Argument darf nicht enthalten eine Verwendung von der `auto` Schlüsselwort.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie keine Vorlagenarguments mit dem `auto` Schlüsselwort.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ergibt C3539.  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)