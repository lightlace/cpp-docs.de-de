---
title: Transaktionsobjekt-Schnittstellen | Microsoft Docs
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
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d295bd73fbc8bb5fba7ae443b8a99705768753bf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="transaction-object-interfaces"></a>Transaktionsobjekt-Schnittstellen
Das Transaktionsobjekt, das eine unteilbare Arbeitseinheit für eine Datenquelle definiert und bestimmt, wie diese Arbeitseinheiten miteinander in Beziehung stehen. Dieses Objekt wird von der OLE DB-Anbietervorlagen nicht direkt unterstützt (d. h. Sie müssen ein eigenes Objekt erstellen).  
  
 Die folgende Tabelle zeigt die obligatorischen und optionalen Schnittstellen, die durch OLE DB für ein Transaktionsobjekt definiert.  
  
|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Erforderlich|Nein|  
|[ITransaction](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Erforderlich|Nein|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|Nein|  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)