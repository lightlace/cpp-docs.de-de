---
title: CCustomSession (CustomSess.H) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidersession
- myprovidersess.h
- ccustomsession
- customsess.h
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
- CCustomSession class in CustomSess.H
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50576d93d8b86a070b928d62662a212d957e5c79
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216317"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*Benutzerdefinierte*Sess.H enthält die Deklaration und Implementierung für das OLE DB-Sitzungsobjekt. Das Datenquellenobjekt erstellt das Sitzungsobjekt und stellt eine Konversation zwischen einem Consumer und Anbieter dar. Mehrere gleichzeitige Sitzungen können für eine Datenquelle geöffnet sein. Die Vererbungsliste für `CCustomSession` folgt:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSession
class ATL_NO_VTABLE CCustomSession : 
   public CComObjectRootEx<CComSingleThreadModel>,
   public IGetDataSourceImpl<CCustomSession>,
   public IOpenRowsetImpl<CCustomSession>,
   public ISessionPropertiesImpl<CCustomSession>,
   public IObjectWithSiteSessionImpl<CCustomSession>,
   public IDBSchemaRowsetImpl<CCustomSession>,
   public IDBCreateCommandImpl<CCustomSession, CCustomCommand>
```

Das Sitzungsobjekt erbt `IGetDataSource`, `IOpenRowset`, `ISessionProperties`, und `IDBCreateCommand`. Die `IGetDataSource` Schnittstelle ermöglicht es, eine Sitzung mit die Datenquelle abgerufen werden, die sie erstellt haben. Dies ist nützlich, wenn Sie zum Abrufen von Eigenschaften aus der Datenquelle, die Sie erstellt oder andere Informationen, die die Datenquelle bereitstellen müssen. Die `ISessionProperties` Schnittstelle verarbeitet alle Eigenschaften für die Sitzung. Die `IOpenRowset` und `IDBCreateCommand` Schnittstellen werden verwendet, um Datenbankaufgaben. Wenn der Anbieter Befehle unterstützt, es implementiert die `IDBCreateCommand` Schnittstelle. Es wird verwendet, um das Command-Objekt zu erstellen, das Befehle ausführen können. Immer vom Anbieter implementiert die `IOpenRowset` Objekt. Es wird verwendet, um ein Rowset von einem Anbieter zu generieren. Es ist ein Standardrowset (z. B. `"select * from mytable"`) von einem Anbieter.

Der Assistent generiert auch drei Sitzungsklassen: `CCustomSessionColSchema`, `CCustomSessionPTSchema`, und `CCustomSessionTRSchema`. Diese Sitzungen werden für Schemarowsets verwendet. Schemarowsets können den Anbieter an Metadaten an den Consumer zurückgegeben, ohne dass die Consumer, die eine Abfrage ausführen oder Daten abrufen muss. Beim Abrufen von Metadaten kann viel schneller als das Suchen eines Anbieters Funktionen sein.

OLE DB-Spezifikation erfordert, dass Anbieter implementieren die `IDBSchemaRowset` unterstützt drei Schema Rowsets Schnittstellentypen: DBSCHEMA_COLUMNS DBSCHEMA_PROVIDER_TYPES und DBSCHEMA_TABLES. Der Assistent generiert die Implementierungen für sämtliche-Schemarowsets. Jede vom Assistenten generierte Klasse enthält eine `Execute` Methode. In diesem `Execute` -Methode können Sie die Daten zurückgeben, an den Anbieter darüber, welche Tabellen, Spalten und Datentypen, die Sie unterstützen. Diese Daten werden zum Zeitpunkt der Kompilierung bezeichnet.

## <a name="see-also"></a>Siehe auch

[Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)<br/>
