---
title: Aktivieren und Deaktivieren von Diensten für einen Anbieter | Microsoft Docs
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
ms.openlocfilehash: ef36e35234aa4878e30e70748a5b2ba2975c38dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Aktivieren und Deaktivieren von Diensten für einen Anbieter
Einzelne OLE DB-Dienste können aktiviert oder deaktiviert wird, wird standardmäßig für alle Anwendungen, die einen einzelnen Anbieter zugreifen. Dies erfolgt durch Hinzufügen von einer **OLEDB_SERVICES** Registrierungseintrag unter der Anbieter die CLSID, mit einer `DWORD` Wert, der die Dienste zum Aktivieren oder deaktivieren, angibt, wie in der folgenden Tabelle gezeigt.  
  
|Standarddienste aktiviert|Schlüsselwortwert|  
|------------------------------|-------------------|  
|Alle Dienste (Standard)|0xFFFFFFFF|  
|Alle außer Pooling und AutoEnlistment|0xFFFFFFFE|  
|Alle außer den Clientcursor|0xfffffffb|  
|Alle Dienste außer Pooling, AutoEnlistment und Clientcursor|0xfffffff0|  
|Keine Dienste|0x00000000|  
|Keine Aggregation alle Dienste deaktiviert|\<Fehlender Schlüssel >|  
  
## <a name="see-also"></a>Siehe auch  
 [Aktivieren und Deaktivieren von OLE DB-Diensten](../../data/oledb/enabling-and-disabling-ole-db-services.md)