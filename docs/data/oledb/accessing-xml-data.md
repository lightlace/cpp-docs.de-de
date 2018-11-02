---
title: Zugreifen auf XML-Daten
ms.date: 10/18/2018
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
ms.openlocfilehash: 8f77ebf41e741d74443fbae3398589c77fbf6c01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665542"
---
# <a name="accessing-xml-data"></a>Zugreifen auf XML-Daten

Es gibt zwei separate Methoden zum Abrufen von XML-Daten aus einer Datenquelle: eine verwendet [CStreamRowset](../../data/oledb/cstreamrowset-class.md) , die andere verwendet [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).

|Funktionalität|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|Menge der übertragenen Daten|Ruft Daten aus allen Spalten und Zeilen auf einmal ab.|Ruft Daten aus allen Spalten jedoch nur eine Zeile zu einem Zeitpunkt. Sie müssen die Zeilen mithilfe von Methoden wie z. B. navigieren `MoveNext`.|
|Formatieren der Zeichenfolge|SQL Server, formatiert die XML-Zeichenfolge und sendet sie an den Consumer.|Rowsetdaten im systemeigenen Format (Anforderungen, die der Anbieter senden als Unicode-Zeichenfolgen) abruft und erstellt dann die Zeichenfolge, die mit den Daten im XML-Format.|
|Steuern der Formatierung|Sie haben einige Maß an Kontrolle über die Formatierung der XML-Zeichenfolge durch einige SQL Server 2000-spezifische Eigenschaften festlegen.|Sie haben keine Kontrolle über das Format der generierten XML-Zeichenfolge.|

Während `CStreamRowset` bietet eine weitere allgemeine effiziente Möglichkeit zum Abrufen von Daten im XML-Format wird nur von SQL Server 2000 unterstützt.

## <a name="retrieving-xml-data-using-cstreamrowset"></a>Abrufen von XML-Daten mit CStreamRowset

Sie geben [CStreamRowset](../../data/oledb/cstreamrowset-class.md) als den Rowsettyp in Ihre `CCommand` oder `CTable` Deklaration. Sie können es z. B. mit Ihren eigenen Accessor oder keine Accessor verwenden:

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

- oder - 

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

Normalerweise beim Aufruf `CCommand::Open` (angeben, z. B. `CRowset` als die `TRowset` Klasse), wird ein `IRowset` Zeiger. `ICommand::Execute` Gibt eine `IRowset` -Zeiger ist, die in gespeichert ist die `m_spRowset` Mitglied der `CRowset` Objekt. Methoden, z. B. `MoveFirst`, `MoveNext`, und `GetData` verwenden Sie diesen Zeiger, um die Daten abzurufen.

Im Gegensatz dazu beim Aufruf `CCommand::Open` (aber angeben `CStreamRowset` als die `TRowset` Klasse), `ICommand::Execute` gibt ein `ISequentialStream` -Zeiger ist, die in gespeichert ist die `m_spStream` Datenmember [CStreamRowset](../../data/oledb/cstreamrowset-class.md). Sie verwenden, klicken Sie dann die `Read` Methode zum Abrufen von Daten im XML-Format (Unicode-Zeichenfolge). Zum Beispiel:

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000 ist die XML-Formatierung und gibt alle Spalten und Zeilen des Rowsets als eine XML-Zeichenfolge.

Ein Beispiel mit der `Read` -Methode finden Sie unter **Hinzufügen von XML-Unterstützung für den Consumer** in [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md).

> [!NOTE]
> XML-Unterstützung mit `CStreamRowset` funktioniert nur mit SQL Server 2000, und setzt voraus, dass Sie den OLE DB-Anbieter für SQL Server 2000 (installiert mit MDAC) verfügen.

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>Abrufen von XML-Daten mit CXMLAccessor

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) können Sie Daten als Zeichenfolgendaten aus einer Datenquelle zugreifen, wenn Sie keine Kenntnis des Schemas mit dem Datenspeicher haben. `CXMLAccessor` funktioniert wie `CDynamicStringAccessorW` abgesehen davon, dass die erste alle Daten aus dem Datenspeicher als XML-Format (tagged) Daten konvertiert. Die XML-Tag-Namen werden die Spaltennamen der Datenspeicher so weit wie möglich übereinstimmen.

Verwendung `CXMLAccessor` wie jede andere Accessorklasse, und übergeben sie als einen Vorlagenparameter `CCommand` oder `CTable`:

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

Verwendung [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) zum Abrufen von Daten aus der Tabelle eine Zeile zu einem Zeitpunkt, und navigieren Zeilen mithilfe von Methoden wie z. B. `MoveNext`, z.B.:

```cpp
// Open data source, session, and rowset
hr = rs.MoveFirst();

while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
{
    CStringW strRowData;
    myCmd.GetXMLRowData(strRowData);

    printf_s( "%S\n", strRowData );

    hr = rs.MoveNext();
}
```

Sie können [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) zum Abrufen von Informationen als XML-formatierte Zeichenfolge mit Daten (Daten-Typ).

## <a name="see-also"></a>Siehe auch

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)