---
title: Abrufen von Metadaten mit Schemarowsets
ms.date: 10/24/2018
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
ms.openlocfilehash: 12c3de79626411b76a402a7f5407f40a7b054318
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026028"
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>Abrufen von Metadaten mit Schemarowsets

Möglicherweise müssen Sie Informationen über Anbieter, Rowsets, Tabellen, Spalten oder andere Datenbankinformationen beziehen, ohne dafür das Rowset zu öffnen. Daten mit Angaben über die Datenbankstruktur werden als Metadaten bezeichnet und können mithilfe einer Anzahl verschiedener Methoden abgerufen werden. Die Verwendung von Schemarowsets ist eine dieser Methoden.

OLE DB-Vorlagen bieten eine Reihe von Klassen zum Abrufen von Schemainformationen; Diese Klassen erstellen vordefinierte Schemarowsets und sind in aufgeführt [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).

> [!NOTE]
> Wenn Sie OLAP verwenden und einige der Rowsets nicht von den Schemarowset-Klassen unterstützt werden (wenn Sie z. B. eine variable Spaltenanzahl haben), sollten Sie versuchen, `CManualAccessor` oder `CDynamicAccessor` zu verwenden. Sie können durch die Spalten scrollen und case-Anweisungen verwenden, um die möglichen Datentypen für jede einzelne Spalte zu behandeln.

## <a name="catalogschema-model"></a>Das Katalog-/Schemamodell

ANSI SQL definiert ein Katalog-/Schemamodell für Datenspeicher. OLE DB verwendet dieses Modell. In diesem Modell Kataloge (Datenbanken) Schemas und Schemas Tabellen.

- **Katalog** ein Katalog ist ein anderer Name für eine Datenbank. Es ist eine Auflistung von verwandten Schemas. Verwenden Sie zum Auflisten der Kataloge (Datenbanken), die zu einer bestimmten Datenquelle gehören [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md). Da viele Datenbanken nur einen Katalog besitzen, werden Metadaten manchmal als Schemainformationen bezeichnet.

- **Schema** ein Schema ist eine Sammlung von Datenbankobjekten, die Besitzer oder von einem bestimmten Benutzer erstellt wurden. Verwenden Sie zum Auflisten der Schemas im Besitz von eines bestimmten Benutzers [CSchemata](../../data/oledb/cschemata-cschematainfo.md).

   In Microsoft SQL Server und ODBC 2.x stellt ein Schema ist ein Besitzer (Dbo ist beispielsweise ein typischer Schemaname). SQL Server speichert außerdem Metadaten in einem Satz von Tabellen: eine Tabelle enthält eine Liste aller Tabellen und einer anderen Tabelle enthält eine Liste aller Spalten. Es gibt keine Entsprechung zu einem Schema in einer Microsoft Access-Datenbank.

- **Tabelle** Tabellen sind Auflistungen von Spalten, die in einer bestimmten Reihenfolge angeordnet. Verwenden Sie zum Auflisten der Tabellen in einem bestimmten Katalog (Datenbank) und Informationen zu diesen Tabellen definiert [CTables](../../data/oledb/ctables-ctableinfo.md)).

## <a name="restrictions"></a>Beschränkungen

Wenn Sie eine Abfrage nach Schemainformationen durchführen, können Sie Einschränkungen verwenden, um die Art der Informationen anzugeben, an denen Sie interessiert sind. Sie können sich diese Einschränkungen wie einen Filter oder Qualifizierer in einer Abfrage vorstellen. Beispielsweise ist in der Abfrage:

```sql
SELECT * FROM authors WHERE l_name = 'pivo'
```

`l_name` ist eine Einschränkung. Dies ist ein einfaches Beispiel mit nur einer Einschränkung. die Schemarowset-Klassen unterstützen mehrere Einschränkungen.

Die [Schemarowset Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) zu kapseln alle OLE DB-Schemarowsets, damit Sie ein Schemarowset wie beliebiges anderes Rowset zugreifen können, durch das Instanziieren und ihn zu öffnen. Z. B. die TypeDef-Klasse [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) ist definiert als:

```cpp
CRestrictions<CAccessor<CColumnsInfo>
```

Die [CRestrictions](../../data/oledb/crestrictions-class.md) -Klasse stellt Unterstützung für die Einschränkung. Rufen Sie nach der Erstellung einer Instanz des Schemarowsets [CRestrictions:: Open](../../data/oledb/crestrictions-open.md). Diese Methode gibt auf der Grundlage der von Ihnen angegebenen Einschränkungen ein Resultset zurück.

Einschränkungen finden Sie unter [Anhang B: Schemarowsets](/previous-versions/windows/desktop/ms712921(v=vs.85)) und suchen Sie das Rowset, das Sie verwenden. Z. B. `CColumns` entspricht der [COLUMNS-Rowset](/previous-versions/windows/desktop/ms723052(v=vs.85)); in diesem Thema werden die einchränkungsspalten im COLUMNS-Rowset: TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME. Sie müssen diese Reihenfolge beim Angeben der Einschränkungen einhalten.

Also z. B. Wenn Sie möchten die Grundlage des Tabellennamens einzuschränken, TABLE_NAME ist die dritte Einschränkungsspalte, und rufen dann `Open`, den gewünschten Tabellennamen als dritten Einschränkungsparameter an, angeben, wie im folgenden Beispiel gezeigt.

### <a name="to-use-schema-rowsets"></a>So verwenden Sie Schemarowsets

1. Fügen Sie die Headerdatei `Atldbsch.h` (Sie müssen `Atldbcli.h` für die Consumerunterstützung).

1. Instanziieren Sie ein Schemarowsetobjekt in der Consumer- oder Dokumentheaderdatei. Wenn Sie Tabelleninformationen möchten, deklarieren ein `CTables` Objekt; Wenn Sie Informationen möchten, deklarieren eine `CColumns` Objekt. In diesem Beispiel wird veranschaulicht, wie die Spalten der Tabelle „Authors“ abgerufen werden können:

    ```cpp
    CDataSource ds;
    ds.Open();
    CSession ss;
    ss.Open(ds);
    CColumns columnSchemaRowset;
    // TABLE_NAME is the third restriction column, so
    // specify "authors" as the third restriction parameter:
    HRESULT hr = columnSchemaRowset.Open(ss, NULL, NULL, L"authors");
    hr = columnSchemaRowset.MoveFirst();
    while (hr == S_OK)
    {
       hr = columnSchemaRowset.MoveNext();
    }
    ```

1. Greifen Sie zum Abrufen der Informationen auf den entsprechenden Datenmember des Schemarowsetobjekts zu (z. B. `ColumnSchemaRowset.m_szColumnName`). Dieses Datenelement entspricht COLUMN_NAME. Der OLE DB-Spalte welchem Datenmember entspricht, finden Sie unter [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md).

Für den Verweis auf das Schemarowset, TypeDef-Klassen, die in den OLE DB-Vorlagen bereitgestellt (siehe [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)).

Weitere Informationen zu OLE DB-Schemarowsets, einschließlich der einchränkungsspalten, finden Sie unter [Anhang B: Schemarowsets](/previous-versions/windows/desktop/ms712921(v=vs.85)) in die **OLE DB-Programmierreferenz**.

Komplexere Beispiele zur Verwendung von Schemarowset-Klassen finden Sie in der [CatDB](https://github.com/Microsoft/VCSamples) und [DBViewer](https://github.com/Microsoft/VCSamples) Beispiele.

Weitere Informationen über anbieterunterstützung für Schemarowsets finden Sie unter [unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von Accessoren](../../data/oledb/using-accessors.md)