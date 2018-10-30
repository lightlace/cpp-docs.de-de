---
title: Datenquellen-Schnittstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d6b76dd8423abd18359081a8fc30050c23e0b161
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216278"
---
# <a name="data-source-object-interfaces"></a>Datenquellenobjekt-Schnittstellen

Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Datenquellenobjekt definiert.

|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|Erforderlich|Ja|
|`IDBInitialize`|Erforderlich|Ja|
|`IDBProperties`|Erforderlich|Ja|
|[IPersist](/windows/desktop/api/objidl/nn-objidl-ipersist)|Erforderlich|Ja|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|Nein|
|`IDBDataSourceAdmin`|Optional|Nein|
|`IDBInfo`|Optional|Nein|
|[IPersistFile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|Optional|Nein|
|`ISupportErrorInfo`|Optional|Nein|

Das Datenquellenobjekt implementiert die `IDBProperties`, `IDBInitialize`, und `IDBCreateSession` Schnittstellen durch Vererbung. Sie können auch zusätzliche Funktionen unterstützt werden, erbt oder keine von einem dieser Implementierung Klassen erben. Wenn Sie unterstützen möchten die `IDBDataSourceAdmin` -Schnittstelle, die Sie erben müssen, von der `IDBDataSourceAdminImpl` Klasse.

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
