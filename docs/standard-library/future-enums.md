---
title: '&lt;future&gt;-Enumerationen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: eebca67270d208f1e8aa233ece80818bdc40f7f1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltfuturegt-enums"></a>&lt;future&gt;-Enumerationen
||||  
|-|-|-|  
|[future_errc](#future_errc)|[future_status](#future_status)|[launch](#launch)|  
  
##  <a name="future_errc"></a> future_errc-Enumeration  
 Liefert symbolische Namen für alle Fehler, die von der [future_error](../standard-library/future-error-class.md)-Klasse gemeldet werden.  
  
Klasse future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="future_status"></a> future_status-Enumeration  
 Liefert symbolische Namen für die Gründe, aus denen eine zeitgesteuerte Wartefunktion eine Rückgabe ausführen kann.  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="launch"></a> launch-Enumeration  
 Stellt einen Bitmaskentyp dar, mit dem die möglichen Modi für die Vorlagenfunktion [async](../standard-library/future-functions.md#async) beschrieben werden.  
  
Klasse launch{ async, deferred };  
  
## <a name="see-also"></a>Siehe auch  
 [\<future>](../standard-library/future.md)



