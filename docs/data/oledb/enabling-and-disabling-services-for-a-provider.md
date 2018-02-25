---
title: "Aktivieren und Deaktivieren von Diensten für einen Anbieter | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 60e54d9d02cc819c9eaf7674257d846c537da615
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Aktivieren und Deaktivieren von Diensten für einen Anbieter
Einzelne OLE DB-Dienste können aktiviert oder deaktiviert wird, wird standardmäßig für alle Anwendungen, die einen einzelnen Anbieter zugreifen. Dies erfolgt durch Hinzufügen von einer **OLEDB_SERVICES** Registrierungseintrag unter der Anbieter die CLSID, mit einer `DWORD` Wert, der die Dienste zum Aktivieren oder deaktivieren, angibt, wie in der folgenden Tabelle gezeigt.  
  
|Standarddienste aktiviert|Schlüsselwortwert|  
|------------------------------|-------------------|  
|Alle Dienste (Standard)|0xffffffff|  
|Alle außer Pooling und AutoEnlistment|0xfffffffe|  
|Alle außer den Clientcursor|0xfffffffb|  
|Alle Dienste außer Pooling, AutoEnlistment und Clientcursor|0xfffffff0|  
|Keine Dienste|0x00000000|  
|Keine Aggregation alle Dienste deaktiviert|\<Fehlender Schlüssel >|  
  
## <a name="see-also"></a>Siehe auch  
 [Aktivieren und Deaktivieren von OLE DB-Diensten](../../data/oledb/enabling-and-disabling-ole-db-services.md)