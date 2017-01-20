---
title: "Architektur von OLE&#160;DB-Anbietervorlagen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Architektur [C++], OLE DB-Anbieter"
  - "OLE DB [C++], Objektmodell"
  - "OLE DB-Anbietervorlagen, Objektmodell"
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Architektur von OLE&#160;DB-Anbietervorlagen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Datenquellen und Sitzungen  
 Die OLE DB\-Anbieterarchitektur umfasst ein Datenquellenobjekt und eine oder mehrere Sitzungen.  Das Datenquellenobjekt ist das Ausgangsobjekt, das von jedem Anbieter instanziiert werden muss.  Wenn eine Consumeranwendung Daten benötigt, erstellt sie das Datenquellenobjekt parallel, um den Anbieter zu starten.  Das Datenquellenobjekt erstellt \(mithilfe der **IDBCreateSession**\-Schnittstelle\) ein Sitzungsobjekt. Über dieses Objekt stellt der Consumer eine Verbindung mit dem Datenquellenobjekt her.  ODBC\-Programmierer können das Datenquellenobjekt als Äquivalent zu **HENV** und das Sitzungsobjekt als Äquivalent zu **HDBC** betrachten.  
  
 ![Anbieterarchitektur](../../data/oledb/media/vc4twb1.png "vc4TWB1")  
  
 Durch die OLE DB\-Vorlagen wird in Kombination mit den vom OLE DB\-Anbieter\-Assistenten erstellten Quelldateien ein Datenquellenobjekt implementiert.  Eine Sitzung stellt ein Objekt dar und entspricht der **TSession** von OLE DB.  
  
## Erforderliche und optionale Schnittstellen  
 Die OLE DB\-Anbietervorlagen enthalten bereits vorgefertigte Implementierungen für alle erforderlichen Schnittstellen.  OLE DB bietet Definitionen erforderlicher und optionaler Schnittstellen für mehrere Objekttypen:  
  
-   [Datenquelle](../../data/oledb/data-source-object-interfaces.md)  
  
-   [Sitzung](../../data/oledb/session-object-interfaces.md)  
  
-   [Rowset](../../data/oledb/rowset-object-interfaces.md)  
  
-   [Befehl](../../data/oledb/command-object-interfaces.md)  
  
-   [Transaktion](../../data/oledb/transaction-object-interfaces.md)  
  
 Beachten Sie, dass Row\- und Speicherobjekte nicht von den OLE DB\-Anbietervorlagen implementiert werden.  
  
 In der folgenden Tabelle sind die erforderlichen und optionalen Schnittstellen für die oben genannten Objekte gemäß der [Dokumentation zum OLE DB 2.6 SDK](https://msdn.microsoft.com/en-us/library/ms722784.aspx) aufgeführt.  
  
|Komponente|Schnittstelle|Kommentar|  
|----------------|-------------------|---------------|  
|[Datenquelle](../../data/oledb/data-source-object-interfaces.md) \([CDataSource](../../data/oledb/cdatasource-class.md)\)|\[erforderlich\] **IDBCreateSession**<br /><br /> \[erforderlich\] **IDBInitialize**<br /><br /> \[erforderlich\] `IDBProperties`<br /><br /> \[erforderlich\] `IPersist`<br /><br /> \[optional\] **IConnectionPointContainer**<br /><br /> \[optional\] **IDBAsynchStatus**<br /><br /> \[optional\] **IDBDataSourceAdmin**<br /><br /> \[optional\] **IDBInfo**<br /><br /> \[optional\] `IPersistFile`<br /><br /> \[optional\] **ISupportErrorInfo**|Verbindung vom Consumer zum Anbieter.  Das Objekt wird zum Festlegen von Verbindungseigenschaften, z. B. Benutzer\-ID, Kennwort und Datenquellenname, verwendet.  Das Objekt kann auch zum Verwalten einer Datenquelle verwendet werden \(Erstellungs\-, Aktualisierungs\-, Löschvorgänge, Tabellen usw.\).|  
|[Sitzung](../../data/oledb/session-object-interfaces.md) \([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md)\)|\[erforderlich\] **IGetDataSource**<br /><br /> \[erforderlich\] `IOpenRowset`<br /><br /> \[erforderlich\] **ISessionProperties**<br /><br /> \[optional\] **IAlterIndex**<br /><br /> \[optional\] **IAlterTable**<br /><br /> \[optional\] **IBindResource**<br /><br /> \[optional\] **ICreateRow**<br /><br /> \[optional\] **IDBCreateCommand**<br /><br /> \[optional\] **IDBSchemaRowset**<br /><br /> \[optional\] **IIndexDefinition**<br /><br /> \[optional\] **ISupportErrorInfo**<br /><br /> \[optional\] **ITableCreation**<br /><br /> \[optional\] **ITableDefinition**<br /><br /> \[optional\] **ITableDefinitionWithConstraints**<br /><br /> \[optional\] **ITransaction**<br /><br /> \[optional\] **ITransactionJoin**<br /><br /> \[optional\] **ITransactionLocal**<br /><br /> \[optional\] **ITransactionObject**|Das Sitzungsobjekt stellt eine einfache Konversation zwischen einem Consumer und einem Anbieter dar.  Sie ist insofern mit **HSTMT** in ODBC vergleichbar, als dass mehrere Sitzungen gleichzeitig aktiv sein können.<br /><br /> Das Sitzungsobjekt ist der primäre Link für den Zugriff auf OLE DB\-Funktionen.  Der Abruf eines Befehls\-, Transaktions\- oder Rowsetobjekts erfolgt über das Sitzungsobjekt.|  
|[Rowset](../../data/oledb/rowset-object-interfaces.md) \([CRowset](../../data/oledb/crowset-class.md)\)|\[erforderlich\] `IAccessor`<br /><br /> \[erforderlich\] `IColumnsInfo`<br /><br /> \[erforderlich\] **IConvertType**<br /><br /> \[erforderlich\] `IRowset`<br /><br /> \[erforderlich\] `IRowsetInfo`<br /><br /> \[optional\] **IChapteredRowset**<br /><br /> \[optional\] **IColumnsInfo2**<br /><br /> \[optional\] **IColumnsRowset**<br /><br /> \[optional\] **IConnectionPointContainer**<br /><br /> \[optional\] **IDBAsynchStatus**<br /><br /> \[optional\] **IGetRow**<br /><br /> \[optional\] `IRowsetChange`<br /><br /> \[optional\] **IRowsetChapterMember**<br /><br /> \[optional\] **IRowsetCurrentIndex**<br /><br /> \[optional\] **IRowsetFind**<br /><br /> \[optional\] **IRowsetIdentity**<br /><br /> \[optional\] **IRowsetIndex**<br /><br /> \[optional\] `IRowsetLocate`<br /><br /> \[optional\] **IRowsetRefresh**<br /><br /> \[optional\] `IRowsetScroll`<br /><br /> \[optional\] `IRowsetUpdate`<br /><br /> \[optional\] **IRowsetView**<br /><br /> \[optional\] **ISupportErrorInfo**<br /><br /> \[optional\] **IRowsetBookmark**|Das Rowsetobjekt steht für die Daten aus der Datenquelle.  Das Objekt ist für die Bindungen dieser Daten sowie für alle grundlegenden Datenoperationen \(Aktualisieren, Abrufen, Verschieben usw.\) zuständig.  Es ist stets ein Rowsetobjekt vorhanden, in dem Daten aufgenommen und bearbeitet werden.|  
|[Befehl](../../data/oledb/command-object-interfaces.md) \([CCommand](assetId:///52bef5da-c1a0-4223-b4e6-9e464b6db409)\)|\[erforderlich\] `IAccessor`<br /><br /> \[erforderlich\] `IColumnsInfo`<br /><br /> \[erforderlich\] `ICommand`<br /><br /> \[erforderlich\] **ICommandProperties**<br /><br /> \[erforderlich\] `ICommandText`<br /><br /> \[erforderlich\] **IConvertType**<br /><br /> \[optional\] **IColumnsRowset**<br /><br /> \[optional\] **ICommandPersist**<br /><br /> \[optional\] **ICommandPrepare**<br /><br /> \[optional\] `ICommandWithParameters`<br /><br /> \[optional\] **ISupportErrorInfo**<br /><br /> \[optional\] **ICommandStream**|Das Befehlsobjekt verwaltet Datenoperationen, z. B. Abfragen.  Es unterstützt sowohl parametrisierte als auch nicht parametrisierte Anweisungen.<br /><br /> Das Befehlsobjekt ist außerdem für die Verwaltung der Parameter\- und Ausgabespaltenbindungen zuständig.  Eine Bindung ist eine Struktur, die Informationen dazu enthält, wie eine Spalte in einem Rowset abgerufen werden sollte.  Sie enthält Informationen wie Ordnungszahl, Datentyp, Länge und Status.|  
|[Transaktion](../../data/oledb/transaction-object-interfaces.md) \(optional\)|\[erforderlich\] **IConnectionPointContainer**<br /><br /> \[erforderlich\] **ITransaction**<br /><br /> \[optional\] **ISupportErrorInfo**|Das Transaktionsobjekt definiert eine atomare Arbeitseinheit für eine Datenquelle und bestimmt, in welcher Beziehung diese Arbeitseinheiten zueinander stehen.  Dieses Objekt wird von den OLE DB\-Anbietervorlagen nicht direkt unterstützt \(d. h., Sie erstellen ein eigenes Objekt\).|  
  
 Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Eigenschaftenzuordnungen](../../data/oledb/property-maps.md)  
  
-   [Benutzerdatensatz](../../data/oledb/user-record.md)  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Interfaces](https://msdn.microsoft.com/en-us/library/ms709709.aspx)