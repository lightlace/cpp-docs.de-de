---
title: "Abrufen von Metadaten mit Schemarowsets | Microsoft Docs"
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
  - "Metadaten, Abrufen (OLE DB-Vorlagen)"
  - "OLE DB-Consumervorlagen, Abrufen von Anbietermetadaten"
  - "Schemarowsets, Abrufen von OLE DB-Anbietermetadaten"
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Abrufen von Metadaten mit Schemarowsets
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Möglicherweise müssen Sie Informationen über Anbieter, Rowsets, Tabellen, Spalten oder andere Datenbankinformationen beziehen, ohne dafür das Rowset zu öffnen.  Daten mit Angaben über die Datenbankstruktur werden als Metadaten bezeichnet und können mithilfe einer Anzahl verschiedener Methoden abgerufen werden.  Die Verwendung von Schemarowsets ist eine dieser Methoden.  
  
 OLE DB\-Vorlagen bieten Klassen zum Abrufen von Schemainformationen. Diese Klassen erstellen vordefinierte Schemarowsets und sind unter [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) aufgelistet.  
  
> [!NOTE]
>  Wenn Sie OLAP verwenden und einige der Rowsets nicht von den Schemarowset\-Klassen unterstützt werden \(wenn Sie z. B. eine variable Spaltenanzahl haben\), sollten Sie versuchen, `CManualAccessor` oder `CDynamicAccessor` zu verwenden.  Sie können durch die Spalten scrollen und case\-Anweisungen verwenden, um die möglichen Datentypen für jede einzelne Spalte zu behandeln.  
  
## Das Katalog\-\/Schemamodell  
 ANSI SQL definiert ein Katalog\-\/Schemamodell für Datenspeicher. OLE DB verwendet dieses Modell.  In diesem Modell enthalten Kataloge \(Datenbanken\) Schemas, und Schemas enthalten Tabellen.  
  
-   **Katalog** Katalog ist eine andere Bezeichnung für eine Datenbank.  Kataloge sind Auflistungen von verwandten Schemas.  Verwenden Sie [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md) zum Auflisten der Kataloge \(Datenbanken\), die zu einer bestimmten Datenquelle gehören.  Da viele Datenbanken nur einen Katalog besitzen, werden Metadaten manchmal einfach als Schemainformationen bezeichnet.  
  
-   **Schema** Ein Schema ist eine Auflistung von Datenbankobjekten, die im Besitz eines bestimmten Benutzers sind oder von diesem erstellt wurden.  Um alle im Besitz eines bestimmten Benutzers befindlichen Schemas aufzulisten, verwenden Sie [CSchemata](../../data/oledb/cschemata-cschematainfo.md).  
  
     In Microsoft SQL Server und ODBC 2.x stellt ein Schema einen Besitzer dar \(dbo ist beispielsweise ein typischer Schemaname\).  Darüber hinaus speichert SQL Server Metadaten in einer Tabellengruppe: Eine Tabelle enthält eine Liste aller Tabellen, und eine weitere Tabelle enthält eine Liste aller Spalten.  In einer Microsoft Access \-Datenbank gibt es kein Äquivalent zu einem Schema.  
  
-   **Tabelle** Tabellen sind Auflistungen von Spalten, die in einer bestimmten Reihenfolge geordnet sind.  Um alle in einem bestimmten Katalog \(einer bestimmten Datenbank\) definierten Tabellen sowie Informationen über diese Tabellen aufzulisten, verwenden Sie [CTables](../../data/oledb/ctables-ctableinfo.md)\).  
  
## Beschränkungen  
 Wenn Sie eine Abfrage nach Schemainformationen durchführen, können Sie Einschränkungen verwenden, um den gewünschten Informationstyp genauer anzugeben.  Sie können sich diese Einschränkungen wie einen Filter oder Qualifizierer in einer Abfrage vorstellen.  Beispielsweise ist in der Abfrage:  
  
```  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 `l_name` eine Einschränkung.  Dies ist ein sehr einfaches Beispiel mit nur einer Einschränkung. Die Schemarowset\-Klassen unterstützen mehrere Einschränkungen.  
  
 Die [Schemarowset\- und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) kapseln alle OLE DB\-Schemarowsets. So können Sie auf ein Schemarowset wie auf ein beliebiges anderes Rowset zugreifen, indem Sie es instanziieren und öffnen.  Die Typedef\-Klasse [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) ist beispielsweise definiert als:  
  
```  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 Die [CRestrictions](../../data/oledb/crestrictions-class.md)\-Klasse enthält die Unterstützung für die Einschränkung.  Rufen Sie nach dem Erstellen einer Instanz des Schemarowsets [CRestrictions::Open](../../data/oledb/crestrictions-open.md) auf.  Diese Methode gibt auf der Grundlage der von Ihnen angegebenen Einschränkungen ein Resultset zurück.  
  
 Nähere Informationen zum Bestimmen der Einschränkungen finden Sie im [Anhang B: Schemarowsets](http://go.microsoft.com/fwlink/?LinkId=64681). Suchen Sie nach dem von Ihnen verwendeten Rowset.  **CColumns** entspricht beispielsweise dem [COLUMNS\-Rowset](http://go.microsoft.com/fwlink/?LinkId=64682). In diesem Thema werden die Einchränkungsspalten im COLUMNS\-Rowset aufgelistet: TABLE\_CATALOG, TABLE\_SCHEMA, TABLE\_NAME, COLUMN\_NAME.  Sie müssen diese Reihenfolge beim Angeben der Einschränkungen einhalten.  
  
 Wenn Sie also beispielsweise eine Einschränkung nach Tabellennamen vornehmen möchten, müssen Sie beachten, dass TABLE\_NAME die dritte Einschränkungsspalte ist. Rufen Sie anschließend **Open** auf, und geben Sie den gewünschten Tabellennamen als dritten Einschränkungsparameter an, wie im folgenden Beispiel dargestellt.  
  
#### So verwenden Sie Schemarowsets  
  
1.  Sie müssen die Headerdatei „Atldbsch.h“ einfügen. \(Natürlich benötigen Sie auch Atldbcli.h für die Consumerunterstützung.\)  
  
2.  Instanziieren Sie ein Schemarowsetobjekt in der Consumer\- oder Dokumentheaderdatei.  Wenn Sie Tabelleninformationen abrufen möchten, deklarieren Sie ein **CTables**\-Objekt. Wenn Sie Spalteninformationen abrufen möchten, deklarieren Sie ein **CColumns**\-Objekt.  In diesem Beispiel wird veranschaulicht, wie die Spalten der Tabelle „Authors“ abgerufen werden können:  
  
    ```  
    CDataSource ds;  
    ds.Open();  
    CSession ss;  
    ss.Open();  
    CColumns ColumnSchemaRowset;  
    // TABLE_NAME is the third restriction column, so  
    // specify "authors" as the third restriction parameter:  
    hr = ColumnSchemaRowset.Open(ss, NULL, NULL, "authors");  
    hr = ColumnSchemaRowset.MoveFirst();  
    while (hr == S_OK)  
    {  
       hr = ColumnSchemaRowset.MoveNext();  
    }  
    ```  
  
3.  Greifen Sie zum Abrufen der Informationen auf den entsprechenden Datenmember des Schemarowsetobjekts zu \(z. B. `ColumnSchemaRowset.m_szColumnName`\).  Dies entspricht COLUMN\_NAME.  Welche OLE DB\-Spalte welchem Datenmember entspricht, können Sie unter [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) nachlesen.  
  
 Informationen zur Referenz der in den OLE DB\-Vorlagen enthaltenen Schemarowset\-Klassen und Typedef\-Klassen finden Sie unter [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
 Weitere Informationen zu OLE DB\-Schemarowsets, einschließlich der Einchränkungsspalten, finden Sie im [Anhang B: Schemarowsets](http://go.microsoft.com/fwlink/?LinkId=64681) in der OLE DB\-Programmierreferenz.  
  
 Unter [CatDB](assetId:///003d516b-2bf6-444e-8be5-4ebaa0b66046) und [DBViewer](assetId:///07620f99-c347-4d09-9ebc-2459e8049832) finden Sie komplexere Beispiele zur Verwendung von Schemarowset\-Klassen.  
  
 Informationen über Anbieterunterstützung für Schemarowsets finden Sie unter [Unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md).  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)