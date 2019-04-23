---
title: Referenz der OLE DB-Consumervorlagen
ms.date: 11/04/2016
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
ms.openlocfilehash: fb0b24798b3f2682bbbec7624df34b40a2a9f4cc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032270"
---
# <a name="ole-db-consumer-templates-reference"></a>Referenz der OLE DB-Consumervorlagen

Die OLE DB-Consumervorlagen enthalten die folgenden Klassen. Das Referenzmaterial enthält außerdem Themen, in der [Makros für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

## <a name="session-classes"></a>Sitzungsklassen

[CDataConnection](../../data/oledb/cdataconnection-class.md)<br/>
Verwaltet die Verbindung mit der Datenquelle an. Dies ist eine nützliche für Clients erstellen, da er kapselt erforderlichen Objekte (Datenquelle und Sitzung) und einige der Aufgaben, die Sie tun, wenn eine Verbindung mit einer Datenquelle herstellen möchten.

[CDataSource](../../data/oledb/cdatasource-class.md)<br/>
Entspricht ein OLE DB-Datenquellenobjekt, das eine Verbindung über einen Anbieter mit einer Datenquelle darstellt. Eine oder mehrere datenbanksitzungen, von jeder dargestellt eine `CSession` Objekt, kann über eine einzelne Verbindung stattfinden.

[CEnumerator](../../data/oledb/cenumerator-class.md)<br/>
Entspricht ein OLE DB-Enumerator-Objekt, das Rowsetinformationen zu verfügbaren Datenquellen abruft.

[CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)<br/>
Ein, die `CEnumerator` Zugriff auf die Daten aus dem Enumerator-Rowset. Dieses Rowset besteht aus den Datenquellen und Enumeratoren, die der aktuelle Enumerator sichtbar.

[CSession](../../data/oledb/csession-class.md)<br/>
Stellt eine einzelne Datenbank-Access-Sitzung dar. Eine oder mehrere Sitzungen können zugeordnet werden, mit jedem `CDataSource` Objekt.

## <a name="accessor-classes"></a>Accessorklassen

[CAccessor](../../data/oledb/caccessor-class.md)<br/>
Verwendet für Datensätze, die statisch mit einer Datenquelle gebunden sind. Verwenden Sie diese Accessorklasse, wenn Sie wissen, dass die Struktur der Datenquelle.

[CAccessorBase](../../data/oledb/caccessorbase-class.md)<br/>
Die Basisklasse für alle Accessorklassen.

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
Ein Accessor, der zur Laufzeit erstellt werden kann, anhand der Spalteninformationen des Rowsets. Verwenden Sie diese Klasse zum Abrufen von Daten, wenn Sie nicht, dass die Struktur der Datenquelle wissen.

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
Ein Accessor, der verwendet werden kann, wenn Befehlstypen unbekannt sind. Ruft die Parameterinformationen durch Aufrufen der `ICommandWithParameters` Schnittstelle, wenn der Anbieter die Schnittstelle unterstützt.

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnis der zugrunde liegende Struktur verfügen.

[CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse aus dem Datenspeicher als ANSI-Zeichenfolgendaten verwendete Daten anfordert.

[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse aus dem Datenspeicher als UNICODE-Zeichenfolgendaten verwendete Daten anfordert.

[CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
Ein Accessor mit Methoden, sowohl die Spalten als auch die Parameter des Befehls zu behandeln. Mit dieser Klasse können Sie alle Datentypen verwenden, solange der Anbieter den Typ konvertieren kann.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
Kann als Vorlagenargument verwendet werden, wenn Sie nicht die Klasse zum unterstützen Parameter oder Spalten ausgeben möchten.

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)<br/>
Ähnlich wie `CDynamicStringAccessor` mit dem Unterschied, dass diese Klasse alle Daten aus dem Datenspeicher als XML-Format (tagged) Daten konvertiert.

## <a name="rowset-classes"></a>Schemarowset-Klassen

[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)<br/>
Kapselt ein Rowset und die zugehörigen Accessoren.

[CArrayRowset](../../data/oledb/carrayrowset-class.md)<br/>
Zugriff auf Elemente eines Rowsets mit Arraysyntax verwendet.

[CBulkRowset](../../data/oledb/cbulkrowset-class.md)<br/>
Zum Abrufen und Bearbeiten von Zeilen in einer Massenoperation durch mehrere Zeilenhandles mit einem einzigen Aufruf abrufen verwendet.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
Kann als Vorlagenargument verwendet werden, wenn der Befehl kein Rowset zurückgibt.

[CRestrictions](../../data/oledb/crestrictions-class.md)<br/>
Dient zum Angeben von Einschränkungen für Schemarowsets.

[CRowset](../../data/oledb/crowset-class.md)<br/>
Zum Bearbeiten, festlegen und Abrufen von Rowsetdaten verwendet.

[CStreamRowset](../../data/oledb/cstreamrowset-class.md)<br/>
Gibt eine `ISequentialStream` -Objekt statt eines Rowsets, die Sie verwenden, klicken Sie dann die `Read` Methode zum Abrufen von Daten im XML-Format. (SQL Server 2000 ist die Formatierung, beachten Sie, dass dieses Feature nur mit SQL Server 2000 funktioniert.)

[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)<br/>
Bietet eine dummy-Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify` Methoden `OnFieldChange`, `OnRowChange`, und `OnRowsetChange`.

[Schemarowset-Klassen und Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)

OLE DB-Vorlagen bieten Ihnen eine Reihe von Klassen, die die OLE DB-Schemarowsets entsprechen.

## <a name="command-classes"></a>Command-Klassen

[CCommand](../../data/oledb/ccommand-class.md)<br/>
Zum Festlegen und einen Parameter-basierte OLE DB-Befehl ausführen. Verwenden Sie zum Öffnen von lediglich eines einfachen Rowsets `CTable` stattdessen.

[CMultipleResults](../../data/oledb/cmultipleresults-class.md)<br/>
Als Vorlagenargument für die `CCommand` Vorlage, wenn der Befehl mehrere Resultsets verarbeiten soll.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
Verwendet als Vorlagenargument für Vorlagenklassen, z. B. `CCommand` und `CTable`, diese nehmen ein Argument der Accessor-Klasse. Verwendung `CNoAccessor` , wenn Sie nicht die Klasse zum unterstützen Parameter oder Spalten ausgeben möchten.

[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)<br/>
Als Vorlagenargument für die `CCommand` Vorlage, wenn der Befehl, um ein einzelnes Rowset verarbeiten soll. `CNoMultipleResults` ist der Standardwert für die Template-Argument.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
Als Vorlagenargument für `CCommand` oder `CTable` , wenn der Befehl oder eine Tabelle kein Rowset zurückgibt.

[CTable](../../data/oledb/ctable-class.md)<br/>
Auf der eines einfachen Rowsets ohne Parameter verwendet.

## <a name="property-classes"></a>Eigenschaftenklassen

[CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)<br/>
Wird verwendet, um ein Array von Eigenschaften-IDs übergeben, für die der Consumer Informationen wünscht. Die Eigenschaften gehören zu einer Eigenschaft festgelegt.

[CDBPropSet](../../data/oledb/cdbpropset-class.md)<br/>
Zum Festlegen von Eigenschaften für einen Anbieter.

## <a name="bookmark-class"></a>Lesezeichen-Klasse

[CBookmark](../../data/oledb/cbookmark-class.md)<br/>
Verwendet als Index für den Zugriff auf Daten in einem Rowset.

## <a name="error-class"></a>Error-Klasse

[CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)<br/>
Zum Abrufen von Fehlerinformationen der OLE DB verwendet.

## <a name="see-also"></a>Siehe auch

[Referenz der OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB-Vorlagen](../../data/oledb/ole-db-templates.md)