---
title: Zugreifen auf XML-Daten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 654fab0aa5a5bf96e145f37ae4855f556f79bebf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="accessing-xml-data"></a>Zugreifen auf XML-Daten
Es gibt zwei separate Methoden zum Abrufen von XML-Daten aus einer Datenquelle: eine verwendet [CStreamRowset](../../data/oledb/cstreamrowset-class.md) und die andere Verwendungen [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  
  
|Funktionalität|CStreamRowset|CXMLAccessor|  
|-------------------|-------------------|------------------|  
|Menge der übertragenen Daten|Ruft Daten aus allen Spalten und Zeilen auf einmal ab.|Ruft Daten aus allen Spalten jedoch nur eine Zeile zu einem Zeitpunkt. Müssen Sie Zeilen mithilfe von Methoden wie z. B. navigieren `MoveNext`.|  
|Formatieren der Zeichenfolge|SQL Server formatiert die XML-Zeichenfolge und sendet sie an den Consumer.|Rowsetdaten im systemeigenen Format (Anforderungen, die der Anbieter senden als Unicode-Zeichenfolgen) abruft, und klicken Sie dann die Zeichenfolge, enthält die Daten im XML-Format erstellt.|  
|Steuern der Formatierung|Sie haben einige Maß an Kontrolle bestimmen, wie die XML-Zeichenfolge formatiert ist, indem Sie einige SQL Server 2000-spezifische Eigenschaften festlegen.|Sie haben keine Kontrolle über das Format der generierten XML-Zeichenfolge.|  
  
 Während `CStreamRowset` bietet eine weitere allgemeine effiziente Möglichkeit zum Abrufen von Daten im XML-Format wird nur von SQL Server 2000 unterstützt.  
  
## <a name="retrieving-xml-data-using-cstreamrowset"></a>Abrufen von XML-Daten mit CStreamRowset  
 Geben Sie [CStreamRowset](../../data/oledb/cstreamrowset-class.md) als die Rowset-Datentyp in Ihre `CCommand` oder `CTable` Deklaration. Sie können es mit Ihren eigenen-Zugriffsmethode oder nicht über einen Accessor, z. B. verwenden:  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 - oder -   
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 Normalerweise beim Aufruf `CCommand::Open` (angeben, z. B. `CRowset` als die `TRowset` Klasse), erhält er eine `IRowset` Zeiger. `ICommand::Execute`Gibt eine `IRowset` -Zeiger ist, die in gespeichert ist die `m_spRowset` Mitglied der `CRowset` Objekt. Methoden, z. B. `MoveFirst`, `MoveNext`, und `GetData` verwenden Sie diesen Zeiger, um die Daten abzurufen.  
  
 Dagegen beim Aufruf `CCommand::Open` (aber angeben `CStreamRowset` als die `TRowset` Klasse), `ICommand::Execute` gibt ein `ISequentialStream` Zeiger, die in gespeichert ist die `m_spStream` Datenmember [CStreamRowset](../../data/oledb/cstreamrowset-class.md). Verwenden Sie dann die `Read` Methode zum Abrufen der Daten (Unicode-Zeichenfolge) im XML-Format. Zum Beispiel:  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000 führt die XML-Formatierung und gibt alle Spalten und alle Zeilen des Rowsets als eine XML-Zeichenfolge zurück.  
  
 Ein Beispiel mit der `Read` -Methode finden Sie unter "Hinzufügen von XML-Unterstützung zum Consumer" in [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md).  
  
> [!NOTE]
>  XML-Unterstützung mit `CStreamRowset` funktioniert nur mit SQL Server 2000, und setzt voraus, dass Sie den OLE DB-Anbieter für SQL Server 2000 (mit MDAC installiert) verfügen.  
  
## <a name="retrieving-xml-data-using-cxmlaccessor"></a>Abrufen von XML-Daten mit CXMLAccessor  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) können Sie Daten aus einer Datenquelle als Zeichenfolgendaten zugreifen, wenn Sie keine Kenntnisse der Datenspeicher Schema verfügen. `CXMLAccessor`funktioniert wie `CDynamicStringAccessorW` mit dem Unterschied, dass erstere alle Daten, die aus dem Datenspeicher als XML-Format (tagged) Daten zugegriffen konvertiert. Die XML-Tagnamen entsprechen Spaltennamen für den Datenspeicher so getreu wie möglich.  
  
 Verwendung `CXMLAccessor` wie jede andere Accessorklasse, und übergeben sie als einen Vorlagenparameter `CCommand` oder `CTable`:  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 Verwendung [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) zum Abrufen von Daten aus der Tabelle eine Zeile zu einem Zeitpunkt, und navigieren Zeilen mithilfe von Methoden wie z. B. `MoveNext`, beispielsweise:  
  
```  
// Open data source, session, and rowset  
hr = rs.MoveFirst();  
while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
{  
    CStringW strRowData;  
    myCmd.GetXMLRowData(strRowData);  
  
    printf_s( "%S\n", strRowData );  
  
    hr = rs.MoveNext();  
}  
```  
  
 Sie können [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) die Spalteninformationen (Datentyp) als XML-formatierte Zeichenfolgedaten abrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)