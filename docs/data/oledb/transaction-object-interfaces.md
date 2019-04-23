---
title: Transaktionsobjekt-Schnittstellen
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
ms.openlocfilehash: 0caecc797a3175d5769f98e181e1d99ef6b1ad16
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034033"
---
# <a name="transaction-object-interfaces"></a>Transaktionsobjekt-Schnittstellen

Das Transaktionsobjekt, das eine unteilbare Arbeitseinheit in einer Datenquelle definiert, und bestimmt, wie diese Arbeitseinheiten miteinander in Beziehung stehen. Dieses Objekt wird nicht direkt von der OLE DB-Anbietervorlagen unterstützt (d. h. Sie müssen ein eigenes Objekt erstellen).

Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Transaktionsobjekt definiert.

|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Erforderlich|Nein|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Erforderlich|Nein|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|Nein|

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
