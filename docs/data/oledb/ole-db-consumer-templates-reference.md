---
title: "Referenz der OLE&#160;DB-Consumervorlagen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc.templates.ole"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Consumervorlagen, Klassen"
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Referenz der OLE&#160;DB-Consumervorlagen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die OLE DB\-Consumervorlagen enthalten die folgenden Klassen.  Das Referenzmaterial enthält auch Themen zu [Makros für OLE DB\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## Sitzungs\-Klassen  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 Verwaltet die Verbindung mit der Datenquelle.  Dies ist eine nützliche Klasse zum Erstellen von Clients, da notwendige Objekte \(Sitzung und Datenquelle\) und zur Arbeit kapselt, die Sie, bei der Verbindung mit einer Datenquelle ausführen müssen.  
  
 [Ableiten](../../data/oledb/cdatasource-class.md)  
 Entspricht einem OLE DB\-Datenquellenobjekt und stellt eine Verbindung durch einen Anbieter zu einer Datenquelle dar.  Eine oder mehrere Datenbanksitzungen, jede, die durch ein `CSession`\-Objekt dargestellt wird, können in einer einzelnen Verbindung stattfinden.  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 Entspricht einem OLE DB\-Enumeratorobjekt, das Rowsetinformationen über verfügbare Datenquellen abgerufen.  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 Wird von `CEnumerator`, um Daten vom Enumeratorrowset zuzugreifen.  Dieses Rowset besteht Datenquellen und den Enumeratoren, die vom aktuellen Enumerator sichtbar sind.  
  
 [CSession](../../data/oledb/csession-class.md)  
 Stellt eine einzelne Datenbankzugriffssitzung dar.  Eine oder mehrere Sitzungen können mit jedem `CDataSource`\-Objekt zugeordnet werden.  
  
## Accessorklassen  
 [CAccessor](../../data/oledb/caccessor-class.md)  
 Wird für Datensätze, die statisch mit einer Datenquelle gebunden werden.  Verwenden Sie diese Accessorklasse, wenn Ihnen die Struktur der Datenquelle kennen.  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 Basisklasse für alle Accessorklassen.  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 Ein Accessor, der zur Laufzeit erstellt werden, auf dem die Spalteninformationen des Rowsets.  Verwenden Sie diese Klasse, um Daten abzurufen, wenn Ihnen die Struktur der Datenquelle kennen.  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 Ein Accessor, der verwendet werden kann, wenn Befehlstypen unbekannt sind.  Setzt die Parameterinformationen durch Aufrufen der `ICommandWithParameters`\-Schnittstelle ein, wenn der Anbieter die Schnittstelle unterstützt.  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 Ermöglicht Ihnen, auf eine Datenquelle zuzugreifen, wenn Sie keine Kenntnisse der zugrunde liegende Struktur der Datenbank verfügen.  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 Wie auch `CDynamicStringAccessor` allerdings zu dieser Klasse benötigt die Daten, die vom Datenspeicher als ANSI\-Zeichenfolgendaten zugegriffen werden.  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 Wie auch `CDynamicStringAccessor` allerdings zu dieser Klasse benötigt die Daten, die vom Datenspeicher als Unicode\-Zeichenfolgen\-Daten zugegriffen werden.  
  
 [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
 Ein Accessor mit Methoden, um Spalten und von Befehlsparametern zu behandeln.  Mit dieser Klasse können Sie alle Datentypen verwenden, sofern der Anbieter konvertieren kann.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Kann als Vorlagenargument verwendet werden, wenn Sie die Klasse Parameter oder Ausgabespalten nicht unterstützen soll.  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 Wie auch `CDynamicStringAccessor` allerdings zu dieser Klasse konvertiert alle Daten, die vom Datenspeicher als \(markiert\) zugegriffen werden Daten im XML\-Format.  
  
## Rowset\-Klassen  
 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)  
 Kapselt ein Rowset und seine zugeordneten Accessoren.  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 Wird verwendet, um auf Elemente eines Rowsets mithilfe von Arraysyntax zuzugreifen.  
  
 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)  
 Wird verwendet, um Zeilen durch das Abrufen von mehrere Zeilenhandles mit einem einzelnen Aufruf in Massenauslagerungsvorgängen abzurufen und zu bearbeiten.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Kann als Vorlagenargument verwendet werden, wenn der Befehl keinen Rowset zurückgibt.  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)  
 Wird verwendet, um Einschränkungen für Schemarowsets anzugeben.  
  
 [CRowset](../../data/oledb/crowset-class.md)  
 Wird verwendet, um Rowsetdaten bearbeiten, festzulegen und abzurufen.  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 Gibt ein `ISequentialStream`\-Objekt statt eines Rowsets zurück; Sie verwenden dann die **Lesen**\-Methode, um Daten in XML\-Format abzurufen. \(SQL Server 2000 führt die Formatierung; Beachten Sie, dass diese Funktion nur mit SQL Server 2000.\)  
  
 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)  
 Enthält eine blinde Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify`\-Methoden `OnFieldChange`, `OnRowChange` und `OnRowsetChange`.  
  
 [Schemarowset\-Klassen und typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)  
  
 Die OLE DB\-Vorlagen bieten einen Satz von Klassen, die in OLE DB\-Schemarowsets entsprechen.  
  
## Befehlsklassen  
 [CCommand](../../data/oledb/ccommand-class.md)  
 Wird verwendet, um einen parameterbasierten OLE DB\-Befehl festzulegen und auszuführen.  Um lediglich ein einfaches Rowset zu öffnen, verwenden Sie stattdessen `CTable`.  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 Wird als Vorlagenargument für die `CCommand` \- Vorlage, wenn Sie den Befehl möchten, mehrere Resultsets behandeln zu können.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Wird als Vorlagenargument für Vorlagenklassen, wie `CCommand` und `CTable`, die ein Accessorklassenargument nehmen.  Verwenden Sie `CNoAccessor`, wenn die Klasse Parameter oder Ausgabespalten nicht unterstützen soll.  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 Wird als Vorlagenargument für die `CCommand` \- Vorlage, wenn Sie den Befehl soll, ein einzelnes Rowset zu behandeln.  `CNoMultipleResults` ist der Standardwert für das Vorlagenargument.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Wird als Vorlagenargument für `CCommand` oder `CTable`, wenn der Befehl oder die Tabelle keinen Rowset zurückgibt.  
  
 [CTable](../../data/oledb/ctable-class.md)  
 Wird verwendet, um ein einfaches Rowset ohne Parameter zugreifen.  
  
## Eigenschaften\-Klassen  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 Wird verwendet, um ein Array Eigenschaften\-IDs übergeben, für die der Consumer Eigenschafteninformationen wünscht.  Die Eigenschaften gehören einem Eigenschaft.  
  
 [CDBPropSet](../../data/oledb/cdbpropset-class.md)  
 Wird verwendet, um Eigenschaften in einem Anbieter festzulegen.  
  
## Bookmark\-Klasse  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 Wird als Index für den Zugriff auf Daten in einem Rowset.  
  
## Fehlertyps  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 Wird verwendet, um DB\-Fehlerinformationen OLE abzurufen.  
  
## Siehe auch  
 [Referenz der OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB\-Vorlagen](../../data/oledb/ole-db-templates.md)