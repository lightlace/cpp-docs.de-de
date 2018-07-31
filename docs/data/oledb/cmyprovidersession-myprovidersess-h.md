---
title: CMyProviderSession (MyProviderSess.H) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidersession
- myprovidersess.h
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6bc3a9d377592b16c7e90cf0e75a6fba0eb00a64
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340126"
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession (MyProviderSess.H)
MyProviderSess.H enthält die Deklaration und Implementierung für das OLE DB-Sitzungsobjekt. Das Datenquellenobjekt erstellt das Sitzungsobjekt und stellt eine Konversation zwischen einem Consumer und Anbieter dar. Mehrere gleichzeitige Sitzungen können für eine Datenquelle geöffnet sein. Die Vererbungsliste für `CMyProviderSession` folgt:  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 Das Sitzungsobjekt erbt `IGetDataSource`, `IOpenRowset`, `ISessionProperties`, und `IDBCreateCommand`. Die `IGetDataSource` Schnittstelle ermöglicht es, eine Sitzung mit die Datenquelle abgerufen werden, die sie erstellt haben. Dies ist nützlich, wenn Sie zum Abrufen von Eigenschaften aus der Datenquelle, die Sie erstellt oder andere Informationen, die die Datenquelle bereitstellen müssen. Die `ISessionProperties` Schnittstelle verarbeitet alle Eigenschaften für die Sitzung. Die `IOpenRowset` und `IDBCreateCommand` Schnittstellen werden verwendet, um Datenbankaufgaben. Wenn der Anbieter Befehle unterstützt, es implementiert die `IDBCreateCommand` Schnittstelle. Es wird verwendet, um das Command-Objekt zu erstellen, das Befehle ausführen können. Immer vom Anbieter implementiert die `IOpenRowset` Objekt. Es wird zum Generieren eines einfachen Rowsets von einem Anbieter. Es ist ein Standardrowset (z. B. `"select * from mytable"`) von einem Anbieter.  
  
 Der Assistent generiert auch drei Sitzungsklassen: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema`, und `CMyProviderSessionTRSchema`. Diese Sitzungen werden für Schemarowsets verwendet. Schemarowsets können den Anbieter an Metadaten an den Consumer zurückgegeben, ohne dass die Consumer, die eine Abfrage ausführen oder Daten abrufen muss. Beim Abrufen von Metadaten kann weitaus schneller als beim Ermitteln von einem Anbieter Funktionen sein.  
  
 OLE DB-Spezifikation erfordert, dass Anbieter implementieren die `IDBSchemaRowset` unterstützt drei Schema Rowsets Schnittstellentypen: DBSCHEMA_COLUMNS DBSCHEMA_PROVIDER_TYPES und DBSCHEMA_TABLES. Der Assistent generiert die Implementierungen für sämtliche-Schemarowsets. Jede vom Assistenten generierte Klasse enthält eine `Execute` Methode. In diesem `Execute` -Methode können Sie die Daten zurückgeben, an den Anbieter darüber, welche Tabellen, Spalten und Datentypen, die Sie unterstützen. Diese Daten werden in der Regel zum Zeitpunkt der Kompilierung bezeichnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)