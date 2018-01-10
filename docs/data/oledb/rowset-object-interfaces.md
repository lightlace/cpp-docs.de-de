---
title: Rowsetobjekt-Schnittstellen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 41ed76120029ac8ae82f6be6c6634f08b3912bc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rowset-object-interfaces"></a>Rowsetobjekt-Schnittstellen
Die folgende Tabelle zeigt die obligatorischen und optionalen Schnittstellen, die für ein Rowsetobjekt durch OLE DB definiert.  
  
|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)|Erforderlich|Ja|  
|[IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|Erforderlich|Ja|  
|[IConvertType wird](https://msdn.microsoft.com/en-us/library/ms715926.aspx)|Erforderlich|Ja|  
|[IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)|Erforderlich|Ja|  
|[IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|Erforderlich|Ja|  
|[IChapteredRowset](https://msdn.microsoft.com/en-us/library/ms718180.aspx)|Optional|Nein|  
|[IColumnsInfo2](https://msdn.microsoft.com/en-us/library/ms712953.aspx)|Optional|Nein|  
|[IColumnsRowset](https://msdn.microsoft.com/en-us/library/ms722657.aspx)|Optional|Nein|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|Ja (über ATL)|  
|[IDBAsynchStatus](https://msdn.microsoft.com/en-us/library/ms709832.aspx)|Optional|Nein|  
|[IGetRow](https://msdn.microsoft.com/en-us/library/ms718047.aspx)|Optional|Nein|  
|[IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)|Optional|Ja|  
|[IRowsetChapterMember](https://msdn.microsoft.com/en-us/library/ms725430.aspx)|Optional|Nein|  
|[IRowsetCurrentIndex](https://msdn.microsoft.com/en-us/library/ms709700.aspx)|Optional|Nein|  
|[' Irowsetfind '](https://msdn.microsoft.com/en-us/library/ms724221.aspx)|Optional|Nein|  
|[IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx)|Optional (erforderlich für Ebene-0-Anbieter)|Ja|  
|[IRowsetIndex](https://msdn.microsoft.com/en-us/library/ms719604.aspx)|Optional|Nein|  
|[IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)|Optional|Ja|  
|[IRowsetRefresh abgelöst](https://msdn.microsoft.com/en-us/library/ms714892.aspx)|Optional|Nein|  
|[IRowsetScroll](https://msdn.microsoft.com/en-us/library/ms712984.aspx)|Optional|Nein|  
|[IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)|Optional|Ja|  
|[IRowsetView](https://msdn.microsoft.com/en-us/library/ms709755.aspx)|Optional|Nein|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|Ja|  
|[IRowsetBookmark](https://msdn.microsoft.com/en-us/library/ms714246.aspx)|Optional|Nein|  
  
 Die vom Assistenten generierten Rowset-Objekte implementiert `IAccessor`, `IRowset`, und `IRowsetInfo` durch Vererbung. Die `IAccessorImpl` bindet beide Ausgabespalten. Die `IRowset` Schnittstelle behandelt Abrufvorgänge Zeilen und Daten. Die `IRowsetInfo` Schnittstelle behandelt die Rowseteigenschaften.  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)