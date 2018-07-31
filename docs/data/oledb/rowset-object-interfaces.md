---
title: Rowsetobjekt-Schnittstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e8a1a5f5256087a8869426489fe01250b16fc598
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340510"
---
# <a name="rowset-object-interfaces"></a>Rowsetobjekt-Schnittstellen
Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Rowset-Objekt definiert.  
  
|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](https://msdn.microsoft.com/library/ms719672.aspx)|Erforderlich|Ja|  
|[IColumnsInfo](https://msdn.microsoft.com/library/ms724541.aspx)|Erforderlich|Ja|  
|[IConvertType](https://msdn.microsoft.com/library/ms715926.aspx)|Erforderlich|Ja|  
|[IRowset](https://msdn.microsoft.com/library/ms720986.aspx)|Erforderlich|Ja|  
|[IRowsetInfo](https://msdn.microsoft.com/library/ms724541.aspx)|Erforderlich|Ja|  
|[IChapteredRowset](https://msdn.microsoft.com/library/ms718180.aspx)|Optional|Nein|  
|[IColumnsInfo2](https://msdn.microsoft.com/library/ms712953.aspx)|Optional|Nein|  
|[IColumnsRowset](https://msdn.microsoft.com/library/ms722657.aspx)|Optional|Nein|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|Ja (per ATL)|  
|[IDBAsynchStatus](https://msdn.microsoft.com/library/ms709832.aspx)|Optional|Nein|  
|[IGetRow](https://msdn.microsoft.com/library/ms718047.aspx)|Optional|Nein|  
|[IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx)|Optional|Ja|  
|[IRowsetChapterMember](https://msdn.microsoft.com/library/ms725430.aspx)|Optional|Nein|  
|[IRowsetCurrentIndex](https://msdn.microsoft.com/library/ms709700.aspx)|Optional|Nein|  
|[IRowsetFind](https://msdn.microsoft.com/library/ms724221.aspx)|Optional|Nein|  
|[IRowsetIdentity](https://msdn.microsoft.com/library/ms715913.aspx)|Optional (jedoch erforderlich, für den Anbieter der Ebene 0)|Ja|  
|[IRowsetIndex](https://msdn.microsoft.com/library/ms719604.aspx)|Optional|Nein|  
|[IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx)|Optional|Ja|  
|[IRowsetRefresh](https://msdn.microsoft.com/library/ms714892.aspx)|Optional|Nein|  
|[IRowsetScroll](https://msdn.microsoft.com/library/ms712984.aspx)|Optional|Nein|  
|[IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx)|Optional|Ja|  
|[IRowsetView](https://msdn.microsoft.com/library/ms709755.aspx)|Optional|Nein|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|Optional|Ja|  
|[IRowsetBookmark](https://msdn.microsoft.com/library/ms714246.aspx)|Optional|Nein|  
  
 Vom Assistenten generierte Rowset-Objekt implementiert `IAccessor`, `IRowset`, und `IRowsetInfo` durch Vererbung. Die `IAccessorImpl` bindet beide Ausgabespalten. Die `IRowset` Schnittstelle kümmert sich um Abrufvorgänge Zeilen und Daten. Die `IRowsetInfo` Schnittstelle behandelt die Rowseteigenschaften.  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)