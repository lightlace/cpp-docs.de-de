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
ms.openlocfilehash: 58986c7b80f2bb84b222047efc7aae359c0cd5b1
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083891"
---
# <a name="rowset-object-interfaces"></a>Rowsetobjekt-Schnittstellen

Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Rowset-Objekt definiert.  
  
|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](/previous-versions/windows/desktop/ms719672)|Erforderlich|Ja|  
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541)|Erforderlich|Ja|  
|[IConvertType](/previous-versions/windows/desktop/ms715926)|Erforderlich|Ja|  
|[IRowset](/previous-versions/windows/desktop/ms720986)|Erforderlich|Ja|  
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541)|Erforderlich|Ja|  
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180)|Optional|Nein|  
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953)|Optional|Nein|  
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657)|Optional|Nein|  
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|Ja (per ATL)|  
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832)|Optional|Nein|  
|[IGetRow](/previous-versions/windows/desktop/ms718047)|Optional|Nein|  
|[IRowsetChange](/previous-versions/windows/desktop/ms715790)|Optional|Ja|  
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430)|Optional|Nein|  
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700)|Optional|Nein|  
|[IRowsetFind](/previous-versions/windows/desktop/ms724221)|Optional|Nein|  
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913)|Optional (jedoch erforderlich, für den Anbieter der Ebene 0)|Ja|  
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604)|Optional|Nein|  
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190)|Optional|Ja|  
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892)|Optional|Nein|  
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984)|Optional|Nein|  
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401)|Optional|Ja|  
|[IRowsetView](/previous-versions/windows/desktop/ms709755)|Optional|Nein|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|Optional|Ja|  
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246)|Optional|Nein|  
  
Vom Assistenten generierte Rowset-Objekt implementiert `IAccessor`, `IRowset`, und `IRowsetInfo` durch Vererbung. Die `IAccessorImpl` bindet beide Ausgabespalten. Die `IRowset` Schnittstelle kümmert sich um Abrufvorgänge Zeilen und Daten. Die `IRowsetInfo` Schnittstelle behandelt die Rowseteigenschaften.  
  
## <a name="see-also"></a>Siehe auch  

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)