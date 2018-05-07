---
title: Abrufen von Metadaten mit Schemarowsets | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: da5a715be2ac6dc94ace25ee98781d2e9a4c5f8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>Abrufen von Metadaten mit Schemarowsets
Möglicherweise müssen Sie Informationen über Anbieter, Rowsets, Tabellen, Spalten oder andere Datenbankinformationen beziehen, ohne dafür das Rowset zu öffnen. Daten mit Angaben über die Datenbankstruktur werden als Metadaten bezeichnet und können mithilfe einer Anzahl verschiedener Methoden abgerufen werden. Die Verwendung von Schemarowsets ist eine dieser Methoden.  
  
 OLE DB-Vorlagen bieten eine Reihe von Klassen zum Abrufen von Schemainformationen; Diese Klassen erstellen vordefinierte Schemarowsets und sind in aufgeführt [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
> [!NOTE]
>  Wenn Sie OLAP verwenden und einige der Rowsets nicht von den Schemarowset-Klassen unterstützt werden (wenn Sie z. B. eine variable Spaltenanzahl haben), sollten Sie versuchen, `CManualAccessor` oder `CDynamicAccessor` zu verwenden. Sie können durch die Spalten scrollen und case-Anweisungen verwenden, um die möglichen Datentypen für jede einzelne Spalte zu behandeln.  
  
## <a name="catalogschema-model"></a>Das Katalog-/Schemamodell  
 ANSI SQL definiert ein Katalog-/Schemamodell für Datenspeicher. OLE DB verwendet dieses Modell. In diesem Modell enthalten Kataloge (Datenbanken) Schemas, und Schemas enthalten Tabellen.  
  
-   **Katalog** ein Katalog ist ein anderer Name für eine Datenbank. Kataloge sind Auflistungen von verwandten Schemas. Verwenden Sie zum Auflisten der Kataloge (Datenbanken), die zu einer bestimmten Datenquelle gehören [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md). Da viele Datenbanken nur einen Katalog besitzen, werden Metadaten manchmal einfach als Schemainformationen bezeichnet.  
  
-   **Schema** ein Schema ist eine Auflistung von Datenbankobjekten, die Besitzer oder von einem bestimmten Benutzer erstellt wurden. Verwenden Sie zum Auflisten der Schemas im Besitz eines gegebenen Benutzers [CSchemata](../../data/oledb/cschemata-cschematainfo.md).  
  
     In Microsoft SQL Server und ODBC 2.x, ist ein Schema einen Besitzer (die Dbo ist beispielsweise ein typischer Schemaname). Darüber hinaus speichert SQL Server Metadaten in einem Satz von Tabellen: eine Tabelle enthält eine Liste aller Tabellen und eine andere Tabelle enthält eine Liste aller Spalten. In einer Microsoft Access -Datenbank gibt es kein Äquivalent zu einem Schema.  
  
-   **Tabelle** Tabellen sind Auflistungen von Spalten, die in einer bestimmten Reihenfolge angeordnet sind. Verwenden Sie zum Auflisten der Tabellen in einem bestimmten Katalog (Datenbank) und Informationen zu diesen Tabellen definiert [CTables](../../data/oledb/ctables-ctableinfo.md)).  
  
## <a name="restrictions"></a>Beschränkungen  
 Wenn Sie eine Abfrage nach Schemainformationen durchführen, können Sie Einschränkungen verwenden, um den gewünschten Informationstyp genauer anzugeben. Sie können sich diese Einschränkungen wie einen Filter oder Qualifizierer in einer Abfrage vorstellen. Beispielsweise ist in der Abfrage:  
  
```  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 `l_name` eine Einschränkung. Dies ist ein sehr einfaches Beispiel mit nur einer Einschränkung. Die Schemarowset-Klassen unterstützen mehrere Einschränkungen.  
  
 Die [Schemarowset Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) kapseln alle OLE DB-Schemarowsets, damit Sie ein Schemarowset wie beliebiges anderes Rowset zugreifen können, indem instanziieren und öffnen. Z. B. die-typedefklasse [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) ist definiert als:  
  
```  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 Die [CRestrictions](../../data/oledb/crestrictions-class.md) -Klasse stellt Unterstützung für die Einschränkung. Rufen Sie nach der Erstellung einer Instanz des Schemarowsets [CRestrictions:: Open](../../data/oledb/crestrictions-open.md). Diese Methode gibt auf der Grundlage der von Ihnen angegebenen Einschränkungen ein Resultset zurück.  
  
 Zum Angeben von Einschränkungen finden Sie unter [Anhang B: Schemarowsets](http://go.microsoft.com/fwlink/p/?linkid=64681) , und suchen Sie das Rowset, das Sie verwenden. Beispielsweise **CColumns** entspricht der [COLUMNS-Rowset](http://go.microsoft.com/fwlink/p/?linkid=64682); in diesem Thema werden die einchränkungsspalten im COLUMNS-Rowset aufgelistet: TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME. Sie müssen diese Reihenfolge beim Angeben der Einschränkungen einhalten.  
  
 Also z. B. Wenn Sie anhand des Tabellennamens beschränken möchten, beachten Sie, dass TABLE_NAME die dritte Einschränkungsspalte ist, und rufen Sie anschließend **öffnen**, den gewünschten Tabellennamen als dritten Einschränkungsparameter angeben, wie im folgenden Beispiel gezeigt.  
  
#### <a name="to-use-schema-rowsets"></a>So verwenden Sie Schemarowsets  
  
1.  Sie müssen die Headerdatei „Atldbsch.h“ einfügen. (Natürlich benötigen Sie auch Atldbcli.h für die Consumerunterstützung.)  
  
2.  Instanziieren Sie ein Schemarowsetobjekt in der Consumer- oder Dokumentheaderdatei. Wenn Sie Tabelleninformationen möchten, deklarieren einen **CTables** Objekt; Wenn Sie Spalteninformationen möchten, deklarieren einen **CColumns** Objekt. In diesem Beispiel wird veranschaulicht, wie die Spalten der Tabelle „Authors“ abgerufen werden können:  
  
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
  
3.  Greifen Sie zum Abrufen der Informationen auf den entsprechenden Datenmember des Schemarowsetobjekts zu (z. B. `ColumnSchemaRowset.m_szColumnName`). Dies entspricht COLUMN_NAME. Welche OLE DB-Spalte welchem Datenmember entspricht, finden Sie unter [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md).  
  
 Für den Verweis des Schemarowsets TypeDef-Klassen, die in den OLE DB-Vorlagen bereitgestellt (siehe [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)).  
  
 Weitere Informationen zu OLE DB-Schemarowsets, einschließlich der einchränkungsspalten, finden Sie unter [Anhang B: Schemarowsets](http://go.microsoft.com/fwlink/p/?linkid=64681) in der OLE DB Programmer's Reference.  
  
 Komplexere Beispiele zur Verwendung von Schemarowset-Klassen finden Sie unter der [CatDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046) und [DBViewer](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) Beispiele.  
  
 Informationen über anbieterunterstützung für Schemarowsets finden Sie unter [unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)