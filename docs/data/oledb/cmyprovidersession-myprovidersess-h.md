---
title: CMyProviderSession (MyProviderSess.H) | Microsoft Docs
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
ms.openlocfilehash: 5f5243edcbc6ad7781eb13caf6ec72021fd83506
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096534"
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
  
 Das Sitzungsobjekt erbt von **IGetDataSource**, `IOpenRowset`, **ISessionProperties**, und **IDBCreateCommand**. Die **IGetDataSource** Schnittstelle ermöglicht es, eine Sitzung mit die Datenquelle abzurufen, die es erstellt. Dies ist hilfreich, wenn Sie benötigen zum Abrufen von Eigenschaften aus der Datenquelle, die Sie erstellt oder andere Informationen, die die Datenquelle bereitstellen kann. Die **ISessionProperties** Schnittstelle behandelt alle Eigenschaften für die Sitzung. Die `IOpenRowset` und **IDBCreateCommand** Schnittstellen werden verwendet, um die Datenbank zu arbeiten. Wenn der Anbieter Befehle unterstützt, implementiert die **IDBCreateCommand** Schnittstelle. Es wird verwendet, um das Command-Objekt zu erstellen, das Befehle ausführen können. Immer vom Anbieter implementiert die `IOpenRowset` Objekt. Es wird zum Generieren eines einfachen Rowsets von einem Anbieter. Es ist ein Standardrowset (z. B. `"select * from mytable"`) von einem Anbieter.  
  
 Der Assistent generiert auch drei Sitzungsklassen: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema`, und `CMyProviderSessionTRSchema`. Diese Sitzungen werden für Schemarowsets verwendet. Schemarowsets können den Anbieter an Metadaten an den Consumer zurückgegeben, ohne dass der Consumer, die eine Abfrage ausführen oder Daten abrufen muss. Abrufen von Metadaten kann wesentlich schneller als das Ermitteln von einem Anbieter Funktionen sein.  
  
 OLE DB-Spezifikation erfordert, dass Anbieter implementieren die **IDBSchemaRowset** unterstützt drei Schemarowsets Schnittstellentypen: **DBSCHEMA_COLUMNS**, **DBSCHEMA_PROVIDER_TYPES** , und `DBSCHEMA_TABLES`. Der Assistent generiert für jedes Schemarowset Implementierungen. Jede vom Assistenten generierte Klasse enthält eine `Execute` Methode. In diesem `Execute` -Methode, können Sie die Daten zurückgeben, an den Anbieter zu Tabellen, Spalten und Datentypen, die Sie unterstützen. Diese Daten werden in der Regel zum Zeitpunkt der Kompilierung bezeichnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)