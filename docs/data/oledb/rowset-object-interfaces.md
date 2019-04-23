---
title: Rowsetobjekt-Schnittstellen
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
ms.openlocfilehash: 1f3e6066af4b6870c5fa90f7bde373bb7be476ce
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032952"
---
# <a name="rowset-object-interfaces"></a>Rowsetobjekt-Schnittstellen

Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Rowset-Objekt definiert.

|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|
|---------------|---------------|--------------------------------------|
|[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))|Erforderlich|Ja|
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Erforderlich|Ja|
|[IConvertType](/previous-versions/windows/desktop/ms715926(v=vs.85))|Erforderlich|Ja|
|[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85))|Erforderlich|Ja|
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Erforderlich|Ja|
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180(v=vs.85))|Optional|Nein|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953(v=vs.85))|Optional|Nein|
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657(v=vs.85))|Optional|Nein|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|Ja (per ATL)|
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832(v=vs.85))|Optional|Nein|
|[IGetRow](/previous-versions/windows/desktop/ms718047(v=vs.85))|Optional|Nein|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))|Optional|Ja|
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430(v=vs.85))|Optional|Nein|
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700(v=vs.85))|Optional|Nein|
|[IRowsetFind](/previous-versions/windows/desktop/ms724221(v=vs.85))|Optional|Nein|
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85))|Optional (jedoch erforderlich, für den Anbieter der Ebene 0)|Ja|
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604(v=vs.85))|Optional|Nein|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))|Optional|Ja|
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892(v=vs.85))|Optional|Nein|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984(v=vs.85))|Optional|Nein|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))|Optional|Ja|
|[IRowsetView](/previous-versions/windows/desktop/ms709755(v=vs.85))|Optional|Nein|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|Ja|
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246(v=vs.85))|Optional|Nein|

Vom Assistenten generierte Rowset-Objekt implementiert `IAccessor`, `IRowset`, und `IRowsetInfo` durch Vererbung. Die `IAccessorImpl` bindet beide Ausgabespalten. Die `IRowset` Schnittstelle kümmert sich um Abrufvorgänge Zeilen und Daten. Die `IRowsetInfo` Schnittstelle behandelt die Rowseteigenschaften.

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
