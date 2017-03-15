---
title: Pufferungseffekte | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d888b6d16e0a71168e0615d89bbd1d03c51afad8
ms.lasthandoff: 02/24/2017

---
# <a name="effects-of-buffering"></a>Pufferungseffekte
Im folgenden Beispiel werden die Effekte von Pufferung veranschaulicht. Sie erwarten wahrscheinlich, dass das Programm `please wait`ausgibt, 5 Sekunden wartet, und dann den nächsten Vorgang ausführt. Das Programm wird aber nicht unbedingt so funktionieren, weil die Ausgabe gepuffert wird.  
  
```  
// effects_buffering.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <time.h>  
using namespace std;  
  
int main( )  
{  
   time_t tm = time( NULL ) + 5;  
   cout << "Please wait...";  
   while ( time( NULL ) < tm )  
      ;  
   cout << "\nAll done" << endl;  
}  
```  
  
 Damit das Programm logisch funktioniert, muss sich das `cout` -Objekt selbst leeren, wenn die Meldung angezeigt werden soll. Um ein `ostream` -Objekt zu leeren, senden Sie ihm den `flush` -Manipulator:  
  
```  
cout <<"Please wait..." <<flush;  
```  
  
 In diesem Schritt wird der Puffer geleert, wodurch sichergestellt wird, dass die Meldung vor dem Wartevorgang ausgegeben wird. Sie können auch den `endl` -Manipulator verwenden, der den Puffer leert und einen Wagenrücklauf und Zeilenvorschub ausgibt, oder Sie können das `cin` Objekt verwenden. Dieses Objekt (mit dem `cerr` - oder dem `clog` -Objekt) ist in der Regel mit dem `cout` -Objekt verknüpft. Daher wird bei jeder Verwendung von `cin` (oder einem der Objekte `cerr` oder `clog` ) das `cout` -Objekt geleert.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)


