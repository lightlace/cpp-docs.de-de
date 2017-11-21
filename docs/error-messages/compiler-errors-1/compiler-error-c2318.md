---
title: Compilerfehler C2318 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2318
dev_langs: C++
helpviewer_keywords: C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e73934351caf640b650335b7c4766407d5c485d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2318"></a>Compilerfehler C2318
Kein try-Block mit diesem catch-Handler verbunden  
  
 Es ist ein `catch` -Handler definiert, vor diesem ist aber kein `try` -Block angegeben.  
  
 Im folgenden Beispiel wird C2318 generiert:  
  
```  
// C2318.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   // no try block  
   catch( int ) {}   // C2318  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2318b.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try{}  
   catch( int ) {}  
}  
```