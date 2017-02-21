---
title: "Zugreifen auf XML-Daten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStreamRowset-Klasse, Abrufen von XML-Daten"
  - "CXMLAccessor-Klasse, Abrufen von XML-Daten"
  - "Daten [C++], XML-Datenzugriff"
  - "Datenzugriff [C++], XML-Daten"
  - "Rowsets [C++], Abrufen von XML-Daten"
  - "XML [C++], Zugreifen auf Daten"
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Zugreifen auf XML-Daten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei verschiedene Methoden zum Abrufen von XML\-Daten aus einer Datenquelle: Die eine verwendet [CStreamRowset](../../data/oledb/cstreamrowset-class.md), und die andere verwendet [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  
  
|Funktionalität|CStreamRowset|CXMLAccessor|  
|--------------------|-------------------|------------------|  
|Menge der übertragenen Daten|Ruft Daten aus allen Spalten und Zeilen gleichzeitig ab.|Ruft Daten aus allen Spalten ab, jedoch für jede Spalte einzeln.  Sie müssen mithilfe von Methoden \(z. B. `MoveNext`\) durch Zeilen navigieren.|  
|Formatieren der Zeichenfolge|SQL Server formatiert die XML\-Zeichenfolge und sendet sie an den Consumer.|Ruft Rowsetdaten im systemeigenen Format ab. \(Der Anbieter muss diese als Unicode\-Zeichenfolgen übermitteln.\) Erstellt anschließend die Zeichenfolge mit den Daten im XML\-Format.|  
|Steuerung der Formatierung|Sie können die Formatierung der XML\-Zeichenfolge bis zu einem gewissen Grad steuern, indem Sie einige SQL Server 2000\-spezifische Eigenschaften einstellen.|Sie haben keine Möglichkeit, das Format der generierten XML\-Zeichenfolge zu steuern.|  
  
 `CStreamRowset` stellt zwar insgesamt die effizientere Art zum Abrufen von Daten im XML\-Format dar, sie wird jedoch nur von SQL Server 2000 unterstützt.  
  
## Abrufen von XML\-Daten mit CStreamRowset  
 Sie müssen [CStreamRowset](../../data/oledb/cstreamrowset-class.md) als Rowsettyp in der `CCommand`\-Deklaration oder `CTable`\-Deklaration angeben.  Sie können hierbei einen eigenen Accessor oder gar keinen Accessor verwenden, beispielsweise:  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 \- oder \-  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 Wenn Sie `CCommand::Open` \(z. B. `CRowset` als `TRowset`\-Klasse\) aufrufen, wird ein `IRowset`\-\-Zeiger abgerufen.  `ICommand::Execute` gibt einen `IRowset`\-Zeiger zurück, der im `m_spRowset`\-Member des `CRowset`\-Objekts gespeichert wird.  Methoden wie `MoveFirst`, `MoveNext` und `GetData` verwenden diesen Zeiger zum Abrufen der Daten.  
  
 Wenn Sie im Gegensatz hierzu `CCommand::Open` aufrufen \(aber `CStreamRowset` als `TRowset`\-Klasse angeben\), gibt `ICommand::Execute` einen `ISequentialStream`\-Zeiger zurück, der im `m_spStream`\-Datenmember von [CStreamRowset](../../data/oledb/cstreamrowset-class.md) gespeichert wird.  Anschließend verwenden Sie die `Read`\-Methode, um die Daten \(Unicode\-Zeichenfolge\) im XML\-Format abzurufen.  Beispiel:  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000 führt die XML\-Formatierung durch und gibt alle Spalten und Zeilen des Rowsets als eine XML\-Zeichenfolge zurück.  
  
 Ein Beispiel zur Verwendung der `Read`\-Methode finden Sie unter "Hinzufügen von XML\-Unterstützung zum Consumer" in [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md).  
  
> [!NOTE]
>  XML\-Unterstützung mit `CStreamRowset` ist nur mit SQL Server 2000 möglich und setzt den OLE DB Anbieter für SQL Server 2000 \(mit MDAC installiert\) voraus.  
  
## Abrufen von XML\-Daten mit CXMLAccessor  
 Mit [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) können Sie auf Daten einer Datenquelle als Zeichenfolgendaten zugreifen, wenn das Schema des Datenspeichers nicht bekannt ist.  `CXMLAccessor` arbeitet wie `CDynamicStringAccessorW`. Das erste Objekt konvertiert allerdings alle Daten, auf die vom Datenspeicher als Daten im XML\-Format \(markiert\) zugegriffen wurde.  Dabei wird eine größtmögliche Entsprechung zwischen den XML\-Tagnamen und den Spaltennamen des Datenspeichers angestrebt.  
  
 Verwenden Sie `CXMLAccessor` wie jede andere Accessorklasse, indem Sie sie als einen Vorlagenparameter an `CCommand` oder `CTable` übergeben:  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 Verwenden Sie [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) zum zeilenweisen Abrufen von Daten aus der Tabelle und zum Navigieren durch Zeilen mithilfe von Methoden \(z. B. `MoveNext`\). Beispiel:  
  
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
  
 Sie können [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) verwenden, um Spalteninformationen \(Datentypinformationen\) als XML\-formatierte Zeichenfolgedaten abzurufen.  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)