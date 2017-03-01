---
title: '&lt;future&gt;-Enumerationen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b1f8c56de97789bea4f0923cd87e8144382e1ed0
ms.lasthandoff: 02/24/2017

---
# <a name="ltfuturegt-enums"></a>&lt;future&gt;-Enumerationen
||||  
|-|-|-|  
|[future_errc-Enumeration](#future_errc_enumeration)|[future_status-Enumeration](#future_status_enumeration)|[launch-Enumeration](#launch_enumeration)|  
  
##  <a name="a-namefutureerrcenumerationa--futureerrc-enumeration"></a><a name="future_errc_enumeration"></a> future_errc-Enumeration  
 Liefert symbolische Namen für alle Fehler, die von der [future_error](../standard-library/future-error-class.md)-Klasse gemeldet werden.  
  
Klasse future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="a-namefuturestatusenumerationa--futurestatus-enumeration"></a><a name="future_status_enumeration"></a> future_status-Enumeration  
 Liefert symbolische Namen für die Gründe, aus denen eine zeitgesteuerte Wartefunktion eine Rückgabe ausführen kann.  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="a-namelaunchenumerationa--launch-enumeration"></a><a name="launch_enumeration"></a> launch-Enumeration  
 Stellt einen Bitmaskentyp dar, mit dem die möglichen Modi für die Vorlagenfunktion [async](../standard-library/future-functions.md#async_function) beschrieben werden.  
  
Klasse launch{ async, deferred };  
  
## <a name="see-also"></a>Siehe auch  
 [\<future>](../standard-library/future.md)




