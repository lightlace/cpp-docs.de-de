---
title: Architektur von OLE DB-Anbietervorlagen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 289d1d5f09f60b829c6dd7d1f1b00c0de3562518
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ole-db-provider-template-architecture"></a>Architektur von OLE DB-Anbietervorlagen
## <a name="data-sources-and-sessions"></a>Datenquellen und Sitzungen  
 Die OLE DB-Anbieterarchitektur enthält ein Datenquellenobjekt und eine oder mehrere Sitzungen. Das Datenquellenobjekt ist das erste Objekt, das jeder Anbieter instanziiert werden muss. Wenn eine Consumeranwendung Daten benötigt, erstellt er gemeinsam das Datenquellenobjekt, um den Anbieter zu starten. Das Datenquellenobjekt erstellt ein Sitzungsobjekt (mithilfe der **IDBCreateSession** Interface) über die der Consumer auf das Datenquellenobjekt stellt eine Verbindung her. ODBC-Programmierer können sich vorstellen, der das Datenquellenobjekt als äquivalent zu den **HENV** und das Sitzungsobjekt als gleichwertig mit der **HDBC**.  
  
 ![Architektur des Anbieters](../../data/oledb/media/vc4twb1.gif "vc4twb1")  
  
 Zusammen mit den Quelldateien, die vom OLE DB-Anbieter-Assistenten erstellt wird implementiert die OLE DB-Vorlagen ein Datenquellenobjekt. Eine Sitzung ist ein Objekt, das den OLE DB-entspricht **TSession**.  
  
## <a name="mandatory-and-optional-interfaces"></a>Obligatorische und optionale Schnittstellen  
 Der OLE DB-Anbietervorlagen bieten vorgefertigte Implementierungen für alle erforderlichen Schnittstellen. Obligatorische und optionale Schnittstellen werden von OLE DB für verschiedene Typen von Objekten definiert:  
  
-   [Datenquelle](../../data/oledb/data-source-object-interfaces.md)  
  
-   [Sitzung](../../data/oledb/session-object-interfaces.md)  
  
-   [Rowset](../../data/oledb/rowset-object-interfaces.md)  
  
-   [Befehl](../../data/oledb/command-object-interfaces.md)  
  
-   [Transaktion](../../data/oledb/transaction-object-interfaces.md)  
  
 Beachten Sie, dass der OLE DB-Anbietervorlagen keine Zeilen- und Speicher-Objekte implementieren.  
  
 Die folgende Tabelle enthält die erforderliche und optionale Schnittstellen für die oben aufgeführten Objekte gemäß der [OLE DB 2.6 SDK-Dokumentation](https://msdn.microsoft.com/en-us/library/ms722784.aspx).  
  
|Komponente|Schnittstelle|Kommentar|  
|---------------|---------------|-------------|  
|[Datenquelle](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|[erforderlich] **IDBCreateSession**<br /><br /> [erforderlich] **IDBInitialize**<br /><br /> [erforderlich]`IDBProperties`<br /><br /> [erforderlich]`IPersist`<br /><br /> [optional] **IConnectionPointContainer**<br /><br /> [optional] **IDBAsynchStatus**<br /><br /> [optional] **IDBDataSourceAdmin**<br /><br /> [optional] **IDBInfo**<br /><br /> [optional]`IPersistFile`<br /><br /> [optional] **ISupportErrorInfo**|Die Verbindung vom Consumer an den Anbieter. Das Objekt wird verwendet, um Eigenschaften auf der Verbindung z. B. Benutzer-ID, Kennwort und Daten Quellname anzugeben. Das Objekt kann auch zum Verwalten von einer Datenquelle verwendet werden (erstellen, aktualisieren, Löschen von Tabellen und so weiter).|  
|[Sitzung](../../data/oledb/session-object-interfaces.md) ([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[erforderlich] **IGetDataSource**<br /><br /> [erforderlich]`IOpenRowset`<br /><br /> [erforderlich] **ISessionProperties**<br /><br /> [optional] **IAlterIndex**<br /><br /> [optional] **IAlterTable**<br /><br /> [optional] **IBindResource**<br /><br /> [optional] **ICreateRow**<br /><br /> [optional] **IDBCreateCommand**<br /><br /> [optional] **IDBSchemaRowset**<br /><br /> [optional] **IIndexDefinition**<br /><br /> [optional] **ISupportErrorInfo**<br /><br /> [optional] **ITableCreation**<br /><br /> [optional] **ITableDefinition**<br /><br /> [optional] **ITableDefinitionWithConstraints**<br /><br /> [optional] **ITransaction**<br /><br /> [optional] **ITransactionJoin**<br /><br /> [optional] **ITransactionLocal**<br /><br /> [optional] **ITransactionObject**|Das Sitzungsobjekt stellt eine einfache Konversation zwischen einem Consumer und Anbieter dar. Es ähnelt der ODBC **Befehls beschäftigt** , es können viele gleichzeitige Sitzungen aktiv sein.<br /><br /> Das Sitzungsobjekt ist der primäre Link, um OLE DB-Funktionalität zu erhalten. Um einen Befehl, Transaktion oder Rowsetobjekt abzurufen, durchlaufen Sie das Sitzungsobjekt.|  
|[Rowset](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|[erforderlich]`IAccessor`<br /><br /> [erforderlich]`IColumnsInfo`<br /><br /> [erforderlich] **IConvertType**<br /><br /> [erforderlich]`IRowset`<br /><br /> [erforderlich]`IRowsetInfo`<br /><br /> [optional] **IChapteredRowset**<br /><br /> [optional] **IColumnsInfo2**<br /><br /> [optional] **IColumnsRowset**<br /><br /> [optional] **IConnectionPointContainer**<br /><br /> [optional] **IDBAsynchStatus**<br /><br /> [optional] **IGetRow**<br /><br /> [optional]`IRowsetChange`<br /><br /> [optional] **IRowsetChapterMember**<br /><br /> [optional] **IRowsetCurrentIndex**<br /><br /> [optional] **' Irowsetfind '**<br /><br /> [optional] **IRowsetIdentity**<br /><br /> [optional] **IRowsetIndex**<br /><br /> [optional]`IRowsetLocate`<br /><br /> [optional] **IRowsetRefresh abgelöst**<br /><br /> [optional]`IRowsetScroll`<br /><br /> [optional]`IRowsetUpdate`<br /><br /> [optional] **IRowsetView**<br /><br /> [optional] **ISupportErrorInfo**<br /><br /> [optional] **IRowsetBookmark**|Das Rowsetobjekt stellt die Daten aus der Datenquelle an. Das Objekt ist verantwortlich für die Bindungen von Daten und alle grundlegende Vorgänge für die Daten (Update, Fetch, Verschiebung und andere). Sie können jederzeit ein Rowsetobjekt Daten zu enthalten.|  
|[Befehl](../../data/oledb/command-object-interfaces.md) ([CCommand](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409))|[erforderlich]`IAccessor`<br /><br /> [erforderlich]`IColumnsInfo`<br /><br /> [erforderlich]`ICommand`<br /><br /> [erforderlich] **ICommandProperties**<br /><br /> [erforderlich]`ICommandText`<br /><br /> [erforderlich] **IConvertType**<br /><br /> [optional] **IColumnsRowset**<br /><br /> [optional] **ICommandPersist**<br /><br /> [optional] **ICommandPrepare**<br /><br /> [optional]`ICommandWithParameters`<br /><br /> [optional] **ISupportErrorInfo**<br /><br /> [optional] **' ICommandStream '**|Das Command-Objekt verarbeitet die Operationen mit Daten, z. B. Abfragen. Sie können parametrisierte oder nicht parametrisierten Anweisungen behandeln.<br /><br /> Das Command-Objekt ist auch für die Behandlung von Bindungen für Parameter und die Ausgabespalten verantwortlich. Eine Bindung ist eine Struktur, die enthält Informationen, wie eine Spalte in einem Rowset abgerufen werden soll. Es enthält Informationen wie Ordnungszahl, Datentyp, Länge und Status.|  
|[Transaktion](../../data/oledb/transaction-object-interfaces.md) (optional)|[erforderlich] **IConnectionPointContainer**<br /><br /> [erforderlich] **ITransaction**<br /><br /> [optional] **ISupportErrorInfo**|Das Transaktionsobjekt, das eine unteilbare Arbeitseinheit für eine Datenquelle definiert und bestimmt, wie diese Arbeitseinheiten miteinander in Beziehung stehen. Dieses Objekt wird von der OLE DB-Anbietervorlagen nicht direkt unterstützt (d. h., Sie erstellen ein eigenes Objekt).|  
  
 Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Eigenschaftenzuordnungen](../../data/oledb/property-maps.md)  
  
-   [Benutzerdatensatz](../../data/oledb/user-record.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB-Schnittstellen](https://msdn.microsoft.com/en-us/library/ms709709.aspx)