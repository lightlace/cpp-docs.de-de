---
title: Abrufen von Metadaten mit Schemarowsets | Microsoft-Dokumentation
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
ms.openlocfilehash: 8c4e3003beb0e50887f6b765904095c65dd8f1b6
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083657"
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>Abrufen von Metadaten mit Schemarowsets

Möglicherweise müssen Sie Informationen über Anbieter, Rowsets, Tabellen, Spalten oder andere Datenbankinformationen beziehen, ohne dafür das Rowset zu öffnen. Daten mit Angaben über die Datenbankstruktur werden als Metadaten bezeichnet und können mithilfe einer Anzahl verschiedener Methoden abgerufen werden. Die Verwendung von Schemarowsets ist eine dieser Methoden.  
  
OLE DB-Vorlagen bieten eine Reihe von Klassen zum Abrufen von Schemainformationen; Diese Klassen erstellen vordefinierte Schemarowsets und sind in aufgeführt [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
> [!NOTE]
>  Wenn Sie OLAP verwenden und einige der Rowsets nicht von den Schemarowset-Klassen unterstützt werden (wenn Sie z. B. eine variable Spaltenanzahl haben), sollten Sie versuchen, `CManualAccessor` oder `CDynamicAccessor` zu verwenden. Sie können durch die Spalten scrollen und case-Anweisungen verwenden, um die möglichen Datentypen für jede einzelne Spalte zu behandeln.  
  
## <a name="catalogschema-model"></a>Das Katalog-/Schemamodell  

ANSI SQL definiert ein Katalog-/Schemamodell für Datenspeicher. OLE DB verwendet dieses Modell. In diesem Modell enthalten Kataloge (Datenbanken) Schemas, und Schemas enthalten Tabellen.  
  
- **Katalog** ein Katalog ist ein anderer Name für eine Datenbank. Kataloge sind Auflistungen von verwandten Schemas. Verwenden Sie zum Auflisten der Kataloge (Datenbanken), die zu einer bestimmten Datenquelle gehören [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md). Da viele Datenbanken nur einen Katalog besitzen, werden Metadaten manchmal einfach als Schemainformationen bezeichnet.  
  
- **Schema** ein Schema ist eine Sammlung von Datenbankobjekten, die Besitzer oder von einem bestimmten Benutzer erstellt wurden. Verwenden Sie zum Auflisten der Schemas im Besitz von eines bestimmten Benutzers [CSchemata](../../data/oledb/cschemata-cschematainfo.md).  
  
     In Microsoft SQL Server und ODBC 2.x stellt ein Schema ist ein Besitzer (Dbo ist beispielsweise ein typischer Schemaname). SQL Server speichert außerdem Metadaten in einem Satz von Tabellen: eine Tabelle enthält eine Liste aller Tabellen und einer anderen Tabelle enthält eine Liste aller Spalten. In einer Microsoft Access -Datenbank gibt es kein Äquivalent zu einem Schema.  
  
- **Tabelle** Tabellen sind Auflistungen von Spalten, die in einer bestimmten Reihenfolge angeordnet. Verwenden Sie zum Auflisten der Tabellen in einem bestimmten Katalog (Datenbank) und Informationen zu diesen Tabellen definiert [CTables](../../data/oledb/ctables-ctableinfo.md)).  
  
## <a name="restrictions"></a>Beschränkungen  

Wenn Sie eine Abfrage nach Schemainformationen durchführen, können Sie Einschränkungen verwenden, um den gewünschten Informationstyp genauer anzugeben. Sie können sich diese Einschränkungen wie einen Filter oder Qualifizierer in einer Abfrage vorstellen. Beispielsweise ist in der Abfrage:  
  
```sql  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
`l_name` eine Einschränkung. Dies ist ein sehr einfaches Beispiel mit nur einer Einschränkung. Die Schemarowset-Klassen unterstützen mehrere Einschränkungen.  
  
Die [Schemarowset Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) zu kapseln alle OLE DB-Schemarowsets, damit Sie ein Schemarowset wie beliebiges anderes Rowset zugreifen können, durch das Instanziieren und ihn zu öffnen. Z. B. die TypeDef-Klasse [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) ist definiert als:  
  
```cpp  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
Die [CRestrictions](../../data/oledb/crestrictions-class.md) -Klasse stellt Unterstützung für die Einschränkung. Rufen Sie nach der Erstellung einer Instanz des Schemarowsets [CRestrictions:: Open](../../data/oledb/crestrictions-open.md). Diese Methode gibt auf der Grundlage der von Ihnen angegebenen Einschränkungen ein Resultset zurück.  
  
Einschränkungen finden Sie unter [Anhang B: Schemarowsets](/previous-versions/windows/desktop/ms712921) und suchen Sie das Rowset, das Sie verwenden. Z. B. `CColumns` entspricht der [COLUMNS-Rowset](/previous-versions/windows/desktop/ms723052\(v%3dvs.85\)); dieses Themas werden die einchränkungsspalten im COLUMNS-Rowset aufgelistet: TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME. Sie müssen diese Reihenfolge beim Angeben der Einschränkungen einhalten.  
  
Also beispielsweise, wenn Sie möchten die Grundlage des Tabellennamens einzuschränken, beachten Sie, dass TABLE_NAME die dritte Einschränkungsspalte ist, und rufen Sie anschließend `Open`, den gewünschten Tabellennamen als dritten Einschränkungsparameter an, angeben, wie im folgenden Beispiel gezeigt.  
  
#### <a name="to-use-schema-rowsets"></a>So verwenden Sie Schemarowsets  
  
1. Sie müssen die Headerdatei „Atldbsch.h“ einfügen. (Natürlich benötigen Sie auch Atldbcli.h für die Consumerunterstützung.)  
  
1. Instanziieren Sie ein Schemarowsetobjekt in der Consumer- oder Dokumentheaderdatei. Wenn Sie Tabelleninformationen möchten, deklarieren ein `CTables` Objekt; Wenn Sie Informationen möchten, deklarieren eine `CColumns` Objekt. In diesem Beispiel wird veranschaulicht, wie die Spalten der Tabelle „Authors“ abgerufen werden können:  
  
    ```cpp  
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
  
1. Greifen Sie zum Abrufen der Informationen auf den entsprechenden Datenmember des Schemarowsetobjekts zu (z. B. `ColumnSchemaRowset.m_szColumnName`). Dies entspricht COLUMN_NAME. Der OLE DB-Spalte welchem Datenmember entspricht, finden Sie unter [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md).  
  
Für den Verweis auf das Schemarowset, TypeDef-Klassen, die in den OLE DB-Vorlagen bereitgestellt (siehe [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)).  
  
Weitere Informationen zu OLE DB-Schemarowsets, einschließlich der einchränkungsspalten, finden Sie unter [Anhang B: Schemarowsets](/previous-versions/windows/desktop/ms712921) in der OLE DB Programmer's Reference.  
  
Komplexere Beispiele zur Verwendung von Schemarowset-Klassen finden Sie in der [CatDB](https://github.com/Microsoft/VCSamples) und [DBViewer](https://github.com/Microsoft/VCSamples) Beispiele.  
  
Weitere Informationen über anbieterunterstützung für Schemarowsets finden Sie unter [unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md).  
  
## <a name="see-also"></a>Siehe auch  

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)