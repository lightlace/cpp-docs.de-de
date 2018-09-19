---
title: Aktivieren und Deaktivieren von Diensten für einen Anbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5db612c836e4b902e7cad83017661246f4b649e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079387"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Aktivieren und Deaktivieren von Diensten für einen Anbieter

Einzelne OLE DB-Dienste können aktiviert oder deaktiviert wird, wird standardmäßig für alle Anwendungen, die auf einen einzigen Anbieter zugreifen. Dies erfolgt durch hinzufügen einen OLEDB_SERVICES-Registrierungseintrag unter der CLSID des Anbieters, mit einem `DWORD` -Wert, der Dienste zum Aktivieren oder Deaktivieren der angibt, wie in der folgenden Tabelle gezeigt.  
  
|Standarddienste, die aktiviert|Schlüsselwortwert|  
|------------------------------|-------------------|  
|Alle Dienste (Standard)|0xFFFFFFFF|  
|Alle außer Pooling und AutoEnlistment|0xFFFFFFFE|  
|Alle außer den Clientcursor|0xfffffffb|  
|Alle außer Pooling AutoEnlistment und Clientcursor|0xfffffff0|  
|Keine Dienste|0x00000000|  
|Keine Aggregation, alle Dienste deaktiviert|\<Fehlender Schlüssel >|  
  
## <a name="see-also"></a>Siehe auch  

[Aktivieren und Deaktivieren von OLE DB-Diensten](../../data/oledb/enabling-and-disabling-ole-db-services.md)