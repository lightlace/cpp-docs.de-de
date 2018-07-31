---
title: Referenz der OLE DB Consumervorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a4a96ca189c8363d4aaf8df17e00b2419715086
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337952"
---
# <a name="ole-db-consumer-templates-reference"></a>Referenz der OLE DB-Consumervorlagen
Die OLE DB-Consumervorlagen enthalten die folgenden Klassen. Das Referenzmaterial enthält außerdem Themen, in der [Makros für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## <a name="session-classes"></a>Sitzungsklassen  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 Verwaltet die Verbindung mit der Datenquelle an. Dies ist eine nützliche für Clients erstellen, da er kapselt erforderlichen Objekte (Datenquelle und Sitzung) und einige der Aufgaben, die Sie tun, wenn eine Verbindung mit einer Datenquelle herstellen möchten.  
  
 [CDataSource](../../data/oledb/cdatasource-class.md)  
 Entspricht ein OLE DB-Datenquellenobjekt, das eine Verbindung über einen Anbieter mit einer Datenquelle darstellt. Eine oder mehrere datenbanksitzungen, von jeder dargestellt eine `CSession` Objekt, kann über eine einzelne Verbindung stattfinden.  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 Entspricht ein OLE DB-Enumerator-Objekt, das Rowsetinformationen zu verfügbaren Datenquellen abruft.  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 Ein, die `CEnumerator` Zugriff auf die Daten aus dem Enumerator-Rowset. Dieses Rowset besteht aus den Datenquellen und Enumeratoren, die der aktuelle Enumerator sichtbar.  
  
 [CSession](../../data/oledb/csession-class.md)  
 Stellt eine einzelne Datenbank-Access-Sitzung dar. Eine oder mehrere Sitzungen können zugeordnet werden, mit jedem `CDataSource` Objekt.  
  
## <a name="accessor-classes"></a>Accessorklassen  
 [CAccessor](../../data/oledb/caccessor-class.md)  
 Verwendet für Datensätze, die statisch mit einer Datenquelle gebunden sind. Verwenden Sie diese Accessorklasse, wenn Sie wissen, dass die Struktur der Datenquelle.  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 Die Basisklasse für alle Accessorklassen.  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 Ein Accessor, der zur Laufzeit erstellt werden kann, anhand der Spalteninformationen des Rowsets. Verwenden Sie diese Klasse zum Abrufen von Daten, wenn Sie nicht, dass die Struktur der Datenquelle wissen.  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 Ein Accessor, der verwendet werden kann, wenn Befehlstypen unbekannt sind. Ruft die Parameterinformationen durch Aufrufen der `ICommandWithParameters` Schnittstelle, wenn der Anbieter die Schnittstelle unterstützt.  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnis der zugrunde liegende Struktur verfügen.  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse aus dem Datenspeicher als ANSI-Zeichenfolgendaten verwendete Daten anfordert.  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse aus dem Datenspeicher als UNICODE-Zeichenfolgendaten verwendete Daten anfordert.  
  
 [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
 Ein Accessor mit Methoden, sowohl die Spalten als auch die Parameter des Befehls zu behandeln. Mit dieser Klasse können Sie alle Datentypen verwenden, solange der Anbieter den Typ konvertieren kann.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Kann als Vorlagenargument verwendet werden, wenn Sie nicht die Klasse zum unterstützen Parameter oder Spalten ausgeben möchten.  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse alle Daten aus dem Datenspeicher als XML-Format (tagged) Daten konvertiert.  
  
## <a name="rowset-classes"></a>Schemarowset-Klassen  
 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)  
 Kapselt ein Rowset und die zugehörigen Accessoren.  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 Zugriff auf Elemente eines Rowsets mit Arraysyntax verwendet.  
  
 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)  
 Zum Abrufen und Bearbeiten von Zeilen in einer Massenoperation durch mehrere Zeilenhandles mit einem einzigen Aufruf abrufen verwendet.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Kann als Vorlagenargument verwendet werden, wenn der Befehl kein Rowset zurückgibt.  
  
 [cRestrictions](../../data/oledb/crestrictions-class.md)  
 Dient zum Angeben von Einschränkungen für Schemarowsets.  
  
 [CRowset](../../data/oledb/crowset-class.md)  
 Zum Bearbeiten, festlegen und Abrufen von Rowsetdaten verwendet.  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 Gibt eine `ISequentialStream` -Objekt statt eines Rowsets, die Sie verwenden, klicken Sie dann die `Read` Methode zum Abrufen von Daten im XML-Format. (SQL Server 2000 ist die Formatierung, beachten Sie, dass dieses Feature nur mit SQL Server 2000 funktioniert.)  
  
 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)  
 Bietet eine dummy-Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify` Methoden `OnFieldChange`, `OnRowChange`, und `OnRowsetChange`.  
  
 [Schemarowset-Klassen und Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)  
  
 OLE DB-Vorlagen bieten Ihnen eine Reihe von Klassen, die die OLE DB-Schemarowsets entsprechen.  
  
## <a name="command-classes"></a>Command-Klassen  
 [CCommand](../../data/oledb/ccommand-class.md)  
 Zum Festlegen und einen Parameter-basierte OLE DB-Befehl ausführen. Verwenden Sie zum Öffnen von lediglich eines einfachen Rowsets `CTable` stattdessen.  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 Als Vorlagenargument für die `CCommand` Vorlage, wenn der Befehl mehrere Resultsets verarbeiten soll.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Verwendet als Vorlagenargument für Vorlagenklassen, z. B. `CCommand` und `CTable`, diese nehmen ein Argument der Accessor-Klasse. Verwendung `CNoAccessor` , wenn Sie nicht die Klasse zum unterstützen Parameter oder Spalten ausgeben möchten.  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 Als Vorlagenargument für die `CCommand` Vorlage, wenn der Befehl, um ein einzelnes Rowset verarbeiten soll. `CNoMultipleResults` ist der Standardwert für die Template-Argument.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Als Vorlagenargument für `CCommand` oder `CTable` , wenn der Befehl oder eine Tabelle kein Rowset zurückgibt.  
  
 [CTable](../../data/oledb/ctable-class.md)  
 Auf der eines einfachen Rowsets ohne Parameter verwendet.  
  
## <a name="property-classes"></a>Eigenschaftenklassen  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 Wird verwendet, um ein Array von Eigenschaften-IDs übergeben, für die der Consumer Informationen wünscht. Die Eigenschaften gehören zu einer Eigenschaft festgelegt.  
  
 [CDBPropSet](../../data/oledb/cdbpropset-class.md)  
 Zum Festlegen von Eigenschaften für einen Anbieter.  
  
## <a name="bookmark-class"></a>Lesezeichen-Klasse  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 Verwendet als Index für den Zugriff auf Daten in einem Rowset.  
  
## <a name="error-class"></a>Error-Klasse  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 Zum Abrufen von Fehlerinformationen der OLE DB verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz der OLE DB-Vorlagen](../../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB-Vorlagen](../../data/oledb/ole-db-templates.md)