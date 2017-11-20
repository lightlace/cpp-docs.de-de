---
title: OLE DB-Consumer-Vorlagenreferenz | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
dev_langs: C++
helpviewer_keywords: OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4c401cebf9fd09686a532031322793fd9bedac50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ole-db-consumer-templates-reference"></a>Referenz der OLE DB-Consumervorlagen
Der OLE DB-Consumervorlagen enthalten die folgenden Klassen. Das Referenzmaterial enthält außerdem Themen auf der [Makros für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## <a name="session-classes"></a>Sitzungsklassen  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 Verwaltet die Verbindung mit der Datenquelle. Dies ist eine nützliche für Clients erstellen, da sie kapselt erforderlichen Objekte (Datenquelle und Sitzung), und einige der Aufgaben, die Sie beim Verbinden mit einer Datenquelle ausführen müssen.  
  
 [CDataSource](../../data/oledb/cdatasource-class.md)  
 Entspricht einem OLE DB-Datenquellenobjekt, über einen Anbieter eine Verbindung mit einer Datenquelle darstellt. Eine oder mehrere datenbanksitzungen, von jeder dargestellt ein `CSession` Objekt, kann über eine einzelne Verbindung stattfinden.  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 Entspricht einem OLE DB-Enumerator-Objekt, das Rowsetinformationen zu verfügbaren Datenquellen abruft.  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 Verwendet von `CEnumerator` für den Datenzugriff aus dem Enumerator-Rowset. Dieses Rowset besteht aus den Datenquellen und Enumeratoren, die aus dem aktuellen Enumerator sichtbar.  
  
 [CSession](../../data/oledb/csession-class.md)  
 Stellt eine einzelne Datenbank-Access-Sitzung dar. Eine oder mehrere Sitzungen kann mit jedem zugeordneten `CDataSource` Objekt.  
  
## <a name="accessor-classes"></a>Accessorklassen  
 [CAccessor](../../data/oledb/caccessor-class.md)  
 Verwendet für Datensätze, die statisch mit einer Datenquelle gebunden sind. Verwenden Sie diese Zugriffsmethode-Klasse, wenn Sie wissen, dass die Struktur der Datenquelle.  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 Die Basisklasse für alle Accessorklassen.  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 Ein Accessor, der zur Laufzeit basierend auf den Informationen in der Spalte des Rowsets erstellt werden kann. Verwenden Sie diese Klasse zum Abrufen von Daten, wenn Sie nicht, dass die Struktur der Datenquelle wissen.  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 Ein Accessor, der verwendet werden kann, wenn Befehlstypen unbekannt sind. Ruft die Parameterinformationen durch Aufrufen der `ICommandWithParameters` -Schnittstelle ein, wenn der Anbieter die Schnittstelle unterstützt.  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse der zugrunde liegende Struktur der Datenbank verfügen.  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse aus dem Datenspeicher als ANSI-Zeichenfolgendaten verwendete Daten anfordert.  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse aus dem Datenspeicher als Unicode-Zeichenfolgendaten verwendete Daten anfordert.  
  
 [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
 Ein Accessor mit Methoden zum Behandeln von Spalten und Parameter des Befehls. Mit dieser Klasse können Sie alle Datentypen verwenden, solange der Anbieter den Typ konvertieren kann.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Kann als ein Vorlagenargument verwendet werden, wenn Sie nicht die Klasse zur Unterstützung von Parametern oder Spalten ausgeben möchten.  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse alle Daten, die aus dem Datenspeicher als XML-Format (tagged) Daten zugegriffen konvertiert.  
  
## <a name="rowset-classes"></a>Schemarowset-Klassen  
 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)  
 Kapselt ein Rowset und ihre zugeordneten Accessoren.  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 Zugriff auf Elemente eines Rowsets mit Arraysyntax verwendet.  
  
 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)  
 Zum Abrufen und Bearbeiten von Zeilen in einer Massenoperation durch das Abrufen von mehreren Zeilenhandles mit einem einzigen Aufruf verwendet werden.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Kann als ein Vorlagenargument verwendet werden, wenn der Befehl kein Rowset zurückgibt.  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)  
 Dient zum Angeben von Einschränkungen für Schemarowsets.  
  
 [CRowset](../../data/oledb/crowset-class.md)  
 Zum Bearbeiten, festlegen und Abrufen von Rowsetdaten verwendet.  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 Gibt eine `ISequentialStream` -Objekt anstelle eines Rowsets werden; verwenden Sie dann die **lesen** Methode zum Abrufen von Daten im XML-Format. (SQL Server 2000 ist die Formatierung, beachten Sie, dass dieses Feature nur mit SQL Server 2000 funktioniert.)  
  
 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)  
 Stellt eine dummy-Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify` Methoden `OnFieldChange`, `OnRowChange`, und `OnRowsetChange`.  
  
 [Schemarowset-Klassen und Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)  
  
 Der OLE DB-Vorlagen bieten Ihnen eine Reihe von Klassen, die die OLE DB-Schemarowsets entsprechen.  
  
## <a name="command-classes"></a>Befehlsklassen  
 [CCommand](../../data/oledb/ccommand-class.md)  
 Zum Festlegen und einen Parameter-basierte OLE DB-Befehl ausführen. Verwenden, um lediglich öffnen ein einfaches Rowsets `CTable` stattdessen.  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 Verwendet als Vorlagenargument für die `CCommand` Vorlage, wenn Sie den Befehl aus, um mehrere Resultsets verarbeiten soll.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Verwendet als Vorlagenargument für Vorlagenklassen, z. B. `CCommand` und `CTable`, nehmen ein Argument der Accessor-Klasse. Verwendung `CNoAccessor` , wenn Sie nicht die Klasse zur Unterstützung von Parametern oder Spalten ausgeben möchten.  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 Verwendet als Vorlagenargument für die `CCommand` Vorlage, wenn Sie den Befehl aus, um ein einzelnes Rowset behandeln soll. `CNoMultipleResults`ist der Standardwert für das Vorlagenargument an.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Verwendet als Vorlagenargument für `CCommand` oder `CTable` , wenn der Befehl oder die Tabelle kein Rowset zurückgibt.  
  
 [CTable](../../data/oledb/ctable-class.md)  
 Verwendet, um den Zugriff eines einfachen Rowsets ohne Parameter.  
  
## <a name="property-classes"></a>Eigenschaftenklassen  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 Verwendet, um ein Array von Eigenschaften-IDs zu übergeben, für die der Consumer Informationen wünscht. Die Eigenschaften gehören zum einen Eigenschaftensatz.  
  
 [CDBPropSet](../../data/oledb/cdbpropset-class.md)  
 Zum Festlegen von Eigenschaften für einen Anbieter verwendet.  
  
## <a name="bookmark-class"></a>Bookmark-Klasse  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 Als Index verwendet für den Zugriff auf Daten in einem Rowset.  
  
## <a name="error-class"></a>Error-Klasse  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 Zum Abrufen von Fehlerinformationen der OLE DB verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbieter-Vorlagenreferenz](../../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB-Vorlagen](../../data/oledb/ole-db-templates.md)