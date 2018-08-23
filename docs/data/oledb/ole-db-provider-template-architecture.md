---
title: Architektur von OLE DB-Anbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e4170e2089cbfc584c5832e4a1a0542f360741c5
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571394"
---
# <a name="ole-db-provider-template-architecture"></a>Architektur von OLE DB-Anbietervorlagen
## <a name="data-sources-and-sessions"></a>Datenquellen und Sitzungen  
 Die OLE DB-Anbieterarchitektur enthält ein Datenquellenobjekt und eine oder mehrere Sitzungen. Das Objekt ist das erste Objekt, das jeder Anbieter instanziieren muss. Wenn eine Consumer-Anwendung Daten benötigt, wird gleichzeitig das Datenquellenobjekt, um den Anbieter zu starten. Das Datenquellenobjekt erstellt ein Sitzungsobjekt (mithilfe der `IDBCreateSession` Schnittstelle) über die der Consumer auf das Datenquellenobjekt stellt eine Verbindung her. ODBC-Programmierer können sich das Objekt als äquivalent zu vorstellen der `HENV` und das Sitzungsobjekt als Entsprechung zu den `HDBC`.  
  
 ![Anbieterarchitektur](../../data/oledb/media/vc4twb1.gif "vc4twb1")  
  
 Zusammen mit den Quelldateien, die vom OLE DB-Anbieter-Assistenten erstellt wird implementiert der OLE DB-Vorlagen ein Datenquellenobjekt. Eine Sitzung ist ein Objekt, der OLE DB entspricht `TSession`.  
  
## <a name="mandatory-and-optional-interfaces"></a>Erforderliche und optionale Schnittstellen  
 Der OLE DB-Anbietervorlagen bieten vorgefertigte Implementierungen für alle erforderlichen Schnittstellen. Erforderliche und optionale Schnittstellen werden von OLE DB für verschiedene Typen von Objekten definiert:  
  
-   [Datenquelle](../../data/oledb/data-source-object-interfaces.md)  
  
-   [Sitzung](../../data/oledb/session-object-interfaces.md)  
  
-   [Rowset](../../data/oledb/rowset-object-interfaces.md)  
  
-   [Befehl](../../data/oledb/command-object-interfaces.md)  
  
-   [Transaktion](../../data/oledb/transaction-object-interfaces.md)  
  
 Beachten Sie, dass der OLE DB-Anbietervorlagen nicht die Zeile und den Speicher implementiert werden.  
  
 Die folgende Tabelle enthält die erforderliche und optionale Schnittstellen für die oben aufgeführten Objekte gemäß den [OLE DB 2.6 SDK-Dokumentation](/previous-versions/windows/desktop/ms722784\(v=vs.85\)).  
  
|Komponente|Interface|Kommentar|  
|---------------|---------------|-------------|  
|[Datenquelle](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|[erforderlich] `IDBCreateSession`<br /><br /> [erforderlich] `IDBInitialize`<br /><br /> [erforderlich] `IDBProperties`<br /><br /> [erforderlich] `IPersist`<br /><br /> [optional] `IConnectionPointContainer`<br /><br /> [optional] `IDBAsynchStatus`<br /><br /> [optional] `IDBDataSourceAdmin`<br /><br /> [optional] `IDBInfo`<br /><br /> [optional] `IPersistFile`<br /><br /> [optional] `ISupportErrorInfo`|Die Verbindung vom Consumer mit dem Anbieter. Das Objekt wird verwendet, um Eigenschaften für die Verbindung wie z. B. Benutzer-ID, Kennwort und Daten Quellname anzugeben. Das Objekt kann auch zur Verwaltung von einer Datenquelle verwendet werden (erstellen, aktualisieren, Löschen von Tabellen und so weiter).|  
|[Sitzung](../../data/oledb/session-object-interfaces.md) ([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[erforderlich] `IGetDataSource`<br /><br /> [erforderlich] `IOpenRowset`<br /><br /> [erforderlich] `ISessionProperties`<br /><br /> [optional] `IAlterIndex`<br /><br /> [optional] `IAlterTable`<br /><br /> [optional] `IBindResource`<br /><br /> [optional] `ICreateRow`<br /><br /> [optional] `IDBCreateCommand`<br /><br /> [optional] `IDBSchemaRowset`<br /><br /> [optional] `IIndexDefinition`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `ITableCreation`<br /><br /> [optional] `ITableDefinition`<br /><br /> [optional] `ITableDefinitionWithConstraints`<br /><br /> [optional] `ITransaction`<br /><br /> [optional] `ITransactionJoin`<br /><br /> [optional] `ITransactionLocal`<br /><br /> [optional] `ITransactionObject`|Das Sitzungsobjekt stellt eine einfache Konversation zwischen einem Consumer und Anbieter dar. Es ähnelt der ODBC `HSTMT` , es können viele gleichzeitige Sitzungen aktiv sein.<br /><br /> Session-Objekt ist die primäre Verknüpfung, um den OLE DB-Funktionen zu erhalten. Um einen Befehl, der Transaktion oder der Rowset-Objekt zu erhalten, führen Sie das Session-Objekt.|  
|[Rowset](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|[erforderlich] `IAccessor`<br /><br /> [erforderlich] `IColumnsInfo`<br /><br /> [erforderlich] `IConvertType`<br /><br /> [erforderlich] `IRowset`<br /><br /> [erforderlich] `IRowsetInfo`<br /><br /> [optional] `IChapteredRowset`<br /><br /> [optional] `IColumnsInfo2`<br /><br /> [optional] `IColumnsRowset`<br /><br /> [optional] `IConnectionPointContainer`<br /><br /> [optional] `IDBAsynchStatus`<br /><br /> [optional] `IGetRow`<br /><br /> [optional] `IRowsetChange`<br /><br /> [optional] `IRowsetChapterMember`<br /><br /> [optional] `IRowsetCurrentIndex`<br /><br /> [optional] `IRowsetFind`<br /><br /> [optional] `IRowsetIdentity`<br /><br /> [optional] `IRowsetIndex`<br /><br /> [optional] `IRowsetLocate`<br /><br /> [optional] `IRowsetRefresh`<br /><br /> [optional] `IRowsetScroll`<br /><br /> [optional] `IRowsetUpdate`<br /><br /> [optional] `IRowsetView`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `IRowsetBookmark`|Rowset-Objekt stellt die Daten aus der Datenquelle. Das Objekt ist verantwortlich für die Bindungen von Daten und grundlegende Vorgänge (Update, Fetch, datenverschiebung usw.) für die Daten. Sie haben immer eine Rowset-Objekt enthalten und Bearbeiten von Daten.|  
|[Befehl](../../data/oledb/command-object-interfaces.md) ([CCommand](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409))|[erforderlich] `IAccessor`<br /><br /> [erforderlich] `IColumnsInfo`<br /><br /> [erforderlich] `ICommand`<br /><br /> [erforderlich] `ICommandProperties`<br /><br /> [erforderlich] `ICommandText`<br /><br /> [erforderlich] `IConvertType`<br /><br /> [optional] `IColumnsRowset`<br /><br /> [optional] `ICommandPersist`<br /><br /> [optional] `ICommandPrepare`<br /><br /> [optional] `ICommandWithParameters`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `ICommandStream`|Das Command-Objekt verarbeitet die Vorgänge für Daten, z. B. Abfragen. Sie können die parametrisierte oder nicht parametrisierte Anweisungen behandeln.<br /><br /> Das Command-Objekt ist auch zuständig für die Behandlung von Bindungen für Parameter und Ausgabespalten. Eine Bindung ist eine Struktur, die enthält Informationen, wie eine Spalte, in einem Rowset abgerufen werden soll. Es enthält Informationen wie z. B. die Ordnungszahl, Datentyp, Länge und Status.|  
|[Transaktion](../../data/oledb/transaction-object-interfaces.md) (optional)|[erforderlich] `IConnectionPointContainer`<br /><br /> [erforderlich] `ITransaction`<br /><br /> [optional] `ISupportErrorInfo`|Das Transaktionsobjekt, das eine unteilbare Arbeitseinheit in einer Datenquelle definiert, und bestimmt, wie diese Arbeitseinheiten miteinander in Beziehung stehen. Dieses Objekt wird nicht direkt von der OLE DB-Anbietervorlagen unterstützt (d. h., Sie erstellen ein eigenes Objekt).|  
  
 Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Eigenschaftenzuordnungen](../../data/oledb/property-maps.md)  
  
-   [Benutzerdatensatz](../../data/oledb/user-record.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB-Schnittstellen](/previous-versions/windows/desktop/ms709709\(v=vs.85\))