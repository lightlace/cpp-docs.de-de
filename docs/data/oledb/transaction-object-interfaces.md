---
title: Transaktionsobjekt-Schnittstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: b8f03516aedcaf231f14943079eb9be40adf5be4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073122"
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

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)