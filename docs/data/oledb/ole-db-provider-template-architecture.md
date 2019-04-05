---
title: Architektur von OLE DB-Anbietervorlagen
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
ms.openlocfilehash: 65a7e5b8f169d06ca11d8d27ec99ce3db4b63014
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028547"
---
# <a name="ole-db-provider-template-architecture"></a>Architektur von OLE DB-Anbietervorlagen

## <a name="data-sources-and-sessions"></a>Datenquellen und Sitzungen

Die OLE DB-Anbieterarchitektur enthält ein Datenquellenobjekt und eine oder mehrere Sitzungen. Das Objekt ist das erste Objekt, das jeder Anbieter instanziieren muss. Wenn eine Consumer-Anwendung Daten benötigt, wird gleichzeitig das Datenquellenobjekt, um den Anbieter zu starten. Das Datenquellenobjekt erstellt ein Sitzungsobjekt (mithilfe der `IDBCreateSession` Schnittstelle) über die der Consumer auf das Datenquellenobjekt stellt eine Verbindung her. ODBC-Programmierer können sich das Objekt als äquivalent zu vorstellen der `HENV` und das Sitzungsobjekt als Entsprechung zu den `HDBC`.

![Anbieterarchitektur](../../data/oledb/media/vc4twb1.gif "Anbieterarchitektur")

Zusammen mit den Quelldateien erstellt die **OLE DB-Anbieterassistent**, die OLE DB-Vorlagen implementiert ein Datenquellenobjekt. Eine Sitzung ist ein Objekt, der OLE DB entspricht `TSession`.

## <a name="mandatory-and-optional-interfaces"></a>Erforderliche und optionale Schnittstellen

Der OLE DB-Anbietervorlagen bieten vorgefertigte Implementierungen für alle erforderlichen Schnittstellen. Erforderliche und optionale Schnittstellen werden von OLE DB für verschiedene Typen von Objekten definiert:

- [Datenquelle](../../data/oledb/data-source-object-interfaces.md)

- [Sitzung](../../data/oledb/session-object-interfaces.md)

- [Rowset](../../data/oledb/rowset-object-interfaces.md)

- [Befehl](../../data/oledb/command-object-interfaces.md)

- [Transaktion](../../data/oledb/transaction-object-interfaces.md)

Der OLE DB-Anbietervorlagen implementiert nicht die Zeilen- und Storage-Objekte.

Die folgende Tabelle enthält die erforderliche und optionale Schnittstellen für die oben aufgeführten Objekte gemäß den [OLE DB 2.6 SDK-Dokumentation](/previous-versions/windows/desktop/ms722784(v=vs.85)).

|Komponente|Interface|Kommentar|
|---------------|---------------|-------------|
|[Datenquelle](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|[erforderlich] `IDBCreateSession`<br /><br /> [erforderlich] `IDBInitialize`<br /><br /> [erforderlich] `IDBProperties`<br /><br /> [erforderlich] `IPersist`<br /><br /> [optional] `IConnectionPointContainer`<br /><br /> [optional] `IDBAsynchStatus`<br /><br /> [optional] `IDBDataSourceAdmin`<br /><br /> [optional] `IDBInfo`<br /><br /> [optional] `IPersistFile`<br /><br /> [optional] `ISupportErrorInfo`|Die Verbindung vom Consumer mit dem Anbieter. Das Objekt wird verwendet, um Eigenschaften für die Verbindung wie z. B. Benutzer-ID, Kennwort und Daten Quellname anzugeben. Das Objekt kann auch zur Verwaltung von einer Datenquelle verwendet werden (erstellen, aktualisieren, Löschen von Tabellen und so weiter).|
|[Sitzung](../../data/oledb/session-object-interfaces.md) ([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[erforderlich] `IGetDataSource`<br /><br /> [erforderlich] `IOpenRowset`<br /><br /> [erforderlich] `ISessionProperties`<br /><br /> [optional] `IAlterIndex`<br /><br /> [optional] `IAlterTable`<br /><br /> [optional] `IBindResource`<br /><br /> [optional] `ICreateRow`<br /><br /> [optional] `IDBCreateCommand`<br /><br /> [optional] `IDBSchemaRowset`<br /><br /> [optional] `IIndexDefinition`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `ITableCreation`<br /><br /> [optional] `ITableDefinition`<br /><br /> [optional] `ITableDefinitionWithConstraints`<br /><br /> [optional] `ITransaction`<br /><br /> [optional] `ITransactionJoin`<br /><br /> [optional] `ITransactionLocal`<br /><br /> [optional] `ITransactionObject`|Session-Objekt ist eine einfache Konversation zwischen einem Consumer und Anbieter. Es ähnelt der ODBC `HSTMT` , es können viele gleichzeitige Sitzungen aktiv sein.<br /><br /> Session-Objekt ist die primäre Verknüpfung, um den OLE DB-Funktionen zu erhalten. Um einen Befehl, der Transaktion oder der Rowset-Objekt zu erhalten, führen Sie das Session-Objekt.|
|[Rowset](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|[erforderlich] `IAccessor`<br /><br /> [erforderlich] `IColumnsInfo`<br /><br /> [erforderlich] `IConvertType`<br /><br /> [erforderlich] `IRowset`<br /><br /> [erforderlich] `IRowsetInfo`<br /><br /> [optional] `IChapteredRowset`<br /><br /> [optional] `IColumnsInfo2`<br /><br /> [optional] `IColumnsRowset`<br /><br /> [optional] `IConnectionPointContainer`<br /><br /> [optional] `IDBAsynchStatus`<br /><br /> [optional] `IGetRow`<br /><br /> [optional] `IRowsetChange`<br /><br /> [optional] `IRowsetChapterMember`<br /><br /> [optional] `IRowsetCurrentIndex`<br /><br /> [optional] `IRowsetFind`<br /><br /> [optional] `IRowsetIdentity`<br /><br /> [optional] `IRowsetIndex`<br /><br /> [optional] `IRowsetLocate`<br /><br /> [optional] `IRowsetRefresh`<br /><br /> [optional] `IRowsetScroll`<br /><br /> [optional] `IRowsetUpdate`<br /><br /> [optional] `IRowsetView`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `IRowsetBookmark`|Rowset-Objekt stellt die Daten aus der Datenquelle. Das Objekt ist für die Bindungen von Daten und grundlegende Vorgänge (Update, Fetch, datenverschiebung usw.) für die Daten verwendet. Sie haben immer eine Rowset-Objekt, und Bearbeiten von Daten.|
|[Command](../../data/oledb/command-object-interfaces.md) ([CCommand](ccommand-class.md))|[erforderlich] `IAccessor`<br /><br /> [erforderlich] `IColumnsInfo`<br /><br /> [erforderlich] `ICommand`<br /><br /> [erforderlich] `ICommandProperties`<br /><br /> [erforderlich] `ICommandText`<br /><br /> [erforderlich] `IConvertType`<br /><br /> [optional] `IColumnsRowset`<br /><br /> [optional] `ICommandPersist`<br /><br /> [optional] `ICommandPrepare`<br /><br /> [optional] `ICommandWithParameters`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `ICommandStream`|Das Command-Objekt verarbeitet die Vorgänge für Daten, z. B. Abfragen. Sie können die parametrisierte oder nicht parametrisierte Anweisungen behandeln.<br /><br /> Das Command-Objekt ist auch zuständig für die Behandlung von Bindungen für Parameter und Ausgabespalten. Eine Bindung ist eine Struktur, die enthält Informationen, wie eine Spalte, in einem Rowset abgerufen werden soll. Es enthält Informationen wie z. B. die Ordnungszahl, Datentyp, Länge und Status.|
|[Transaktion](../../data/oledb/transaction-object-interfaces.md) (optional)|[erforderlich] `IConnectionPointContainer`<br /><br /> [erforderlich] `ITransaction`<br /><br /> [optional] `ISupportErrorInfo`|Das Transaktionsobjekt, das eine unteilbare Arbeitseinheit in einer Datenquelle definiert, und bestimmt, wie diese Arbeitseinheiten miteinander in Beziehung stehen. Dieses Objekt wird nicht direkt von der OLE DB-Anbietervorlagen unterstützt (d. h., Sie erstellen ein eigenes Objekt).|

Weitere Informationen finden Sie unter den folgenden Themen:

- [Eigenschaftenzuordnungen](../../data/oledb/property-maps.md)

- [Benutzerdatensatz](../../data/oledb/user-record.md)

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB-Schnittstellen](/previous-versions/windows/desktop/ms709709(v=vs.85))<br/>
