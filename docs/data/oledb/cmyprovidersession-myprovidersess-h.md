---
title: CCustomSession (CustomSess.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidersession
- myprovidersess.h
- ccustomsession
- customsess.h
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
- CCustomSession class in CustomSess.H
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
ms.openlocfilehash: 5cb462aba671e79450e9ee7b8447410252f8edc9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023463"
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

OLE DB-Spezifikation erfordert, dass Anbieter implementieren die `IDBSchemaRowset` Schnittstelle unterstützt drei Rowset Schematypen: DBSCHEMA_COLUMNS DBSCHEMA_PROVIDER_TYPES und DBSCHEMA_TABLES. Der Assistent generiert die Implementierungen für sämtliche-Schemarowsets. Jede vom Assistenten generierte Klasse enthält eine `Execute` Methode. In diesem `Execute` -Methode können Sie die Daten zurückgeben, an den Anbieter darüber, welche Tabellen, Spalten und Datentypen, die Sie unterstützen. Diese Daten werden zum Zeitpunkt der Kompilierung bezeichnet.

## <a name="see-also"></a>Siehe auch

[Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)<br/>
