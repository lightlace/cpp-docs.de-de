---
title: Aktivieren und Deaktivieren von Diensten für einen Anbieter
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: d91f08accf1a8be69f63d6bbcaa4c620d68c1077
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033030"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Aktivieren und Deaktivieren von Diensten für einen Anbieter

Einzelne OLE DB-Dienste können aktiviert oder deaktiviert wird, wird standardmäßig für alle Anwendungen, die auf einen einzigen Anbieter zugreifen. Dies erfolgt durch das Hinzufügen eines OLEDB_SERVICES-Registrierungseintrag unter der CLSID des Anbieters, mit einem DWORD-Wert, der zu aktivieren oder deaktivieren, die Dienste angegeben, wie in der folgenden Tabelle gezeigt.

|Standarddienste, die aktiviert|Schlüsselwortwert|
|------------------------------|-------------------|
|Alle Dienste (Standard)|0xFFFFFFFF|
|Alle außer Pooling und AutoEnlistment|0xFFFFFFFE|
|Alle außer den Clientcursor|0xfffffffb|
|Alle außer Pooling AutoEnlistment und Clientcursor|0xfffffff0|
|Keine Dienste|0x00000000|
|Keine Aggregation, alle Dienste deaktiviert|\<Fehlender Schlüssel >|

## <a name="see-also"></a>Siehe auch

[Aktivieren und Deaktivieren von OLE DB-Diensten](../../data/oledb/enabling-and-disabling-ole-db-services.md)