---
title: Compilerwarnung (Stufe 1) C4526 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4526
dev_langs: C++
helpviewer_keywords: C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 00ffa9e20781d8d5d1405d6bf5546b47a6530b88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4526"></a>Compilerwarnung (Stufe 1) C4526
'Funktion': statische Memberfunktion kann nicht virtuelle Funktion, die außer Kraft setzen "virtuelle function'override ignoriert, virtuelle Funktion wird ausgeblendet  
  
 Die statische Memberfunktion erfüllt die Kriterien für die virtuelle Funktion überschreiben, wodurch die Memberfunktion sowohl statische als auch virtuelle.  
  
 Der folgende Code generiert C4526:  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 Im folgenden sind mögliche Korrekturen aufgeführt:  
  
-   Wenn die Funktion wurde der virtuellen Funktion der Basisklasse überschreiben, entfernen Sie den statischen Spezifizierer.  
  
-   Wenn die Funktion eine statische Memberfunktion sein sollte, benennen Sie sie, sodass kein Konflikt mit der virtuellen Basisklasse-Funktion entsteht.