---
title: Datenquelle Objektschnittstelle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 1c8aaed0a9f50e20dba5938b9b37425f4caa2bb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="data-source-object-interfaces"></a>Datenquellenobjekt-Schnittstellen
Die folgende Tabelle zeigt die obligatorischen und optionalen Schnittstellen, die durch OLE DB für ein Datenquellenobjekt definiert.  
  
|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|Erforderlich|Ja|  
|`IDBInitialize`|Erforderlich|Ja|  
|`IDBProperties`|Erforderlich|Ja|  
|[IPersist](http://msdn.microsoft.com/library/windows/desktop/ms688695)|Erforderlich|Ja|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|Nein|  
|`IDBDataSourceAdmin`|Optional|Nein|  
|`IDBInfo`|Optional|Nein|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Optional|Nein|  
|`ISupportErrorInfo`|Optional|Nein|  
  
 Das Datenquellenobjekt implementiert die `IDBProperties`, `IDBInitialize`, und `IDBCreateSession` Schnittstellen durch Vererbung. Sie können auswählen, um zusätzliche Funktionalität durch Vererben oder erben nicht von einer dieser Implementierungsklassen zu unterstützen. Wenn Sie unterstützen möchten die `IDBDataSourceAdmin` Schnittstelle erbt von der `IDBDataSourceAdminImpl` Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)