---
title: Transaktionsobjekt-Schnittstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 33aa2c3ec99db2c2581bce827425c2dfc25bb653
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216304"
---
# <a name="transaction-object-interfaces"></a>Transaktionsobjekt-Schnittstellen

Das Transaktionsobjekt, das eine unteilbare Arbeitseinheit in einer Datenquelle definiert, und bestimmt, wie diese Arbeitseinheiten miteinander in Beziehung stehen. Dieses Objekt wird nicht direkt von der OLE DB-Anbietervorlagen unterstützt (d. h. Sie müssen ein eigenes Objekt erstellen).

Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Transaktionsobjekt definiert.

|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Erforderlich|Nein|
|[ITransaction](/previous-versions/windows/desktop/ms723053)|Erforderlich|Nein|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|Optional|Nein|

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
