---
title: "Aktivieren und Deaktivieren von Diensten für einen Anbieter | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dc6b3d7cc8e80eaa24c2e2dd9b4e23e79dfb09f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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