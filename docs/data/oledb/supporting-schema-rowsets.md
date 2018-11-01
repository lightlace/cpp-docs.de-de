---
title: Supporting Schema Rowsets
ms.date: 11/04/2016
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
ms.openlocfilehash: 79eafef2f73d95c645eb12855c1918a39b76d26e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512527"
---
# <a name="supporting-schema-rowsets"></a>Supporting Schema Rowsets

Schemarowsets können Kunden zum Abrufen von Informationen über einen Datenspeicher ohne Kenntnis der zugrunde liegenden Struktur bzw. das Schema. Ein Datenspeicher kann z. B. Tabellen, die in einer benutzerdefinierten Hierarchie organisiert werden, damit es keine Möglichkeit gäbe, um das Schema mit Ausnahme des sicherzustellen, dass in diesem Artikel haben. (Ein weiteres Beispiel: Beachten Sie, dass die Visual C++-Assistenten-Schemarowsets verwenden, um Accessoren für den Consumer zu generieren.) Um den Consumer zu diesem Zweck zu ermöglichen, des Anbieters Session-Objekt macht Methoden verfügbar, auf die [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686) Schnittstelle. In Visual C++-Anwendungen, die Sie verwenden die [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) Klasse implementieren `IDBSchemaRowset`.

`IDBSchemaRowsetImpl` unterstützt die folgenden Methoden:

- [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) überprüft die Gültigkeit von Einschränkungen für ein Schemarowset.

- [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) implementiert eine COM-Objekterstellerfunktion für das Objekt, das durch die Template-Parameter angegeben.

- [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) gibt an, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen.

- [IDBSchemaRowset:: GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) gibt ein Schemarowset (geerbt von der Schnittstelle) zurück.

- [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) gibt eine Liste der Schemarowsets zugänglich `IDBSchemaRowsetImpl::GetRowset` (geerbt von der Schnittstelle).

## <a name="atl-ole-db-provider-wizard-support"></a>Die Unterstützung der ATL-OLE DB-Anbieter-Assistenten

Der ATL-OLE DB-Anbieter-Assistent erstellt drei Schemaklassen in der Headerdatei für die Sitzung:

- **C**<em>ShortName</em>**SessionTRSchemaRowset**

- **C**<em>ShortName</em>**SessionColSchemaRowset**

- **C**<em>ShortName</em>**SessionPTSchemaRowset**

Diese Klassen reagieren auf Consumeranforderungen für die Schemainformationen; Beachten Sie, dass der OLE DB-Spezifikation erfordert, dass diese drei Schemarowsets unterstützt werden:

- **C**<em>ShortName</em>**SessionTRSchemaRowset** behandelt Anforderungen für die Informationen in der Tabelle (die `DBSCHEMA_TABLES` Schemarowsets).

- **C**<em>ShortName</em>**SessionColSchemaRowset** behandelt Anforderungen für die Spalteninformationen (die `DBSCHEMA_COLUMNS` Schemarowsets). Der Assistent stellt beispielimplementierungen für diese Klassen, die Schemainformationen für einen DOS-Anbieter zurückgegeben werden sollen.

- **C**<em>ShortName</em>**SessionPTSchemaRowset** verarbeitet Anforderungen, die Informationen zu den Anbietertyp-Schema (die `DBSCHEMA_PROVIDER_TYPES` Schemarowsets). Gibt zurück, die vom Assistenten bereitgestellte Standardimplementierung `S_OK`.

Sie können diese Klassen zum Behandeln von Schemainformationen für den Anbieter geeignete anpassen:

- In **C**<em>ShortName</em>**SessionTRSchemaRowset**, füllen Sie die Felder Katalog, Tabellen- und Beschreibung (`trData.m_szType`, `trData.m_szTable`, und `trData.m_szDesc`). Das vom Assistenten generierten Beispiel verwendet nur eine Zeile (Tabelle). Andere Anbieter möglicherweise mehr als eine Tabelle zurück.

- In **C**<em>ShortName</em>**SessionColSchemaRowset**, Sie übergeben den Namen der Tabelle als eine `DBID`.

## <a name="setting-restrictions"></a>Festlegen von Einschränkungen

Ein wichtiges Konzept bei der Schemarowset-Unterstützung ist Einschränkungen, die Sie dazu das `SetRestrictions`. Einschränkungen ermöglichen es Consumern, nur die übereinstimmende Zeilen abzurufen (z. B. Suche nach allen Spalten in der Tabelle „MyTable“). Einschränkungen sind optional, und wenn keine unterstützt werden (Standardeinstellung), werden immer alle Daten zurückgegeben. Ein Beispiel für einen Anbieter, die Einschränkungen unterstützt, finden Sie unter den [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) Beispiel.

## <a name="setting-up-the-schema-map"></a>Einrichten der Schemazuordnung

Richten Sie eine schemazuordnung in Session.h in UpdatePV wie diese:

```cpp
BEGIN_SCHEMA_MAP(CUpdateSession)
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)
END_SCHEMA_MAP()
```

Zur Unterstützung `IDBSchemaRowset`, müssen Sie unterstützen `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, und `DBSCHEMA_PROVIDER_TYPES`. Sie können zusätzliche Schemarowsets in Ihrem eigenen Ermessen hinzufügen.

Deklarieren Sie eine Schema-Rowset-Klasse mit einer `Execute` Methode, z. B. `CUpdateSessionTRSchemaRowset` in UpdatePV:

```cpp
class CUpdateSessionTRSchemaRowset :
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,
                              CTABLESRow, CUpdateSession >
...
// Execute looks like this; what pointers does the consumer use?
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,
                    ULONG cRestrictions, const VARIANT* rgRestrictions)
```

Beachten Sie, dass `CUpdateSession` erbt `IDBSchemaRowsetImpl`, sodass sie die Einschränkung, die für die Behandlung von Methoden hat. Mithilfe von `CSchemaRowsetImpl`, deklarieren Sie die drei untergeordneten Klassen (aufgeführt in der oben gezeigten Schema-Karte): `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset`, und `CUpdateSessionPTSchemaRowset`. Jede dieser untergeordneten Klassen verfügt über eine `Execute` Methode, die einen entsprechenden Satz von Einschränkungen (Suchkriterien) behandelt. Jede `Execute` Methode vergleicht die Werte der `cRestrictions` und `rgRestrictions` Parameter. Siehe dazu die Beschreibung dieser Parameter in [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).

Weitere Informationen darüber, welche Einschränkungen einem bestimmten Schemarowset entsprechen, finden Sie in der Tabelle der Schemarowset-GUIDs in [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686) in die *OLE DB-Programmierreferenz* in der Windows SDK.

Angenommen, Sie unterstützt die **TABLE_NAME** Einschränkungen im Hinblick auf `DBSCHEMA_TABLES`, würden Sie Folgendes tun:

Sehen Sie sich zuerst um `DBSCHEMA_TABLES` und sehen, dass es vier Einschränkungen (in Reihenfolge) unterstützt.

|Schema-Rowset-Einschränkung|Einschränkungswert|
|-------------------------------|-----------------------|
|**TABLE_CATALOG**|0 x 1 (binär 1)|
|**TABLE_SCHEMA**|0 x 2 (binäre 10)|
|**TABLE_NAME**|0 x 4 (binäre 100)|
|**TABLE_TYPE**|0 x 8 (binäre 1000)|

Als Nächstes, beachten Sie, dass ein Bit für jede Einschränkung. Da Sie unterstützen möchten **TABLE_NAME** nur Sie 0 x 4 im zurückgeben würde die `rgRestrictions` Element. Wenn Sie unterstützt **TABLE_CATALOG** und **TABLE_NAME**, würden Sie 0 x 5 (binär 101) zurückgeben.

Standardmäßig gibt die Implementierung für jede Anforderung (bietet keine Unterstützung für Einschränkungen) 0 zurück. UpdatePV ist ein Beispiel für einen Anbieter, der Einschränkungen unterstützt.

### <a name="example"></a>Beispiel

Dieser Code stammt aus dem [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) Beispiel. UpdatePv unterstützt die drei erforderlichen Schemarowsets: `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, und `DBSCHEMA_PROVIDER_TYPES`. Als Beispiel zum Implementieren von Unterstützung für das in Ihrem Anbieter dieses Thema führt Sie durch die Implementierung der `DBSCHEMA_TABLE` Rowset.

> [!NOTE]
> Der Beispielcode unterscheiden sich von dem hier aufgeführten ist; den Code sollte wie die aktuelleren Version angesehen werden.

Der erste Schritt beim Hinzufügen von Unterstützung für das ist, um zu bestimmen, welche Einschränkungen Sie beabsichtigen, zu unterstützen. Um zu bestimmen, welche Einschränkungen für die Schemarowsets verfügbar sind, sehen Sie sich für die Definition von OLE DB-Spezifikation `IDBSchemaRowset`. Folgende die hauptdefinition sehen Sie eine Tabelle mit den Schemanamen für Rowsets, die Anzahl der Einschränkungen und die Einschränkungsspalten. Wählen Sie das Schemarowset, die, das Sie unterstützen, und notieren Sie sich die Anzahl der Einschränkungen und die Einschränkungsspalten möchten. Z. B. `DBSCHEMA_TABLES` unterstützt vier Einschränkungen (**TABLE_CATALOG**, **TABLE_SCHEMA**, **TABLE_NAME**, und **TABLE_TYPE** ):

```cpp
void SetRestrictions(ULONG cRestrictions, GUID* rguidSchema,
   ULONG* rgRestrictions)
{
    for (ULONG l=0; l<cRestrictions; l++)
    {
        if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))
            rgRestrictions[l] = 0x0C;
        else if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_COLUMNS))
                 rgRestrictions[l] = 0x04;
             else if (InlineIsEqualGUID(rguidSchema[l],
                                        DBSCHEMA_PROVIDER_TYPES))
                      rgRestrictions[l] = 0x00;
   }
}
```

Eine Bit stellt jede Einschränkungsspalte dar. Wenn Sie eine Einschränkung unterstützen möchten (d. h. Sie können für eine Abfrage verwendet werden), dieses Bit auf 1 festgelegt. Wenn Sie nicht, um eine Einschränkung zu unterstützen möchten, können Sie dieses Bit auf 0 festgelegt. Über die Befehlszeile des oben angegeben Codes UpdatePV unterstützt die **TABLE_NAME** und **TABLE_TYPE** Einschränkungen für die `DBSCHEMA_TABLES` Rowset. Dies sind die dritte (Bitmaske "100") und die Einschränkungen der vierten (Bitmaske 1000). Daher ist die Bitmaske für UpdatePv 1100 (oder 0x0C):

```cpp
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))
    rgRestrictions[l] = 0x0C;
```

Die folgenden `Execute` Funktion ist vergleichbar mit denen in reguläre Rowsets. Sie verfügen über drei Argumente: *PcRowsAffected*, *cRestrictions*, und *RgRestrictions*. Die *PcRowsAffected* Variable ist ein Output-Parameter, dass der Anbieter die Anzahl der Zeilen im Schemarowset zurückgeben kann. Die *cRestrictions* Parameter ist ein Eingabeparameter, die die Anzahl der Einschränkungen, die vom Consumer übergeben werden an dem Anbieter enthält. Die *RgRestrictions* -Parameter ist ein Array von `VARIANT` Werte, die der Einschränkungswerte enthalten.

```cpp
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,
                const VARIANT* rgRestrictions)
```

Die `cRestrictions` Variable basiert darauf, dass die Gesamtanzahl der Einschränkungen für ein Schemarowset, unabhängig davon, ob der Anbieter unterstützt. Da UpdatePv zwei Einschränkungen (der dritte und vierte) unterstützt, wird dieser Code nur für sieht eine `cRestrictions` Wert größer als oder gleich 3.

Der Wert für die **TABLE_NAME** Einschränkung befindet sich in `rgRestrictions[2]` (in diesem Fall ist die dritte Beschränkung in einem nullbasierten Array 2). Sie müssen überprüfen, ob die Einschränkung nicht VT_EMPTY tatsächlich unterstützt ist. Beachten Sie, dass VT_NULL VT_EMPTY nicht entspricht. VT_NULL gibt einen Wert für die gültige Einschränkung an.

Die UpdatePv Definition einen Tabellennamen ist ein vollständig qualifizierter Pfadname in eine Textdatei. Extrahieren Sie den Einschränkungswert ein, und dann versuchen Sie, öffnen Sie die Datei aus, um sicherzustellen, dass die Datei vorhanden ist. Wenn die Datei nicht vorhanden ist, gibt S_OK zurück. Dies mag etwas rückwärts Zweck des Codes teilt dem Consumer ist ist jedoch, dass keine unterstützten Tabellen durch den Namen, die angegeben wurden. S_OK zurückgegeben, bedeutet, dass den Code ordnungsgemäß ausgeführt.

```cpp
USES_CONVERSION;
enum {
            sizeOfszFile = 255
};
CTABLESRow  trData;
FILE        *pFile = NULL;
TCHAR       szFile[ sizeOfszFile ];
errcode     err = 0;

// Handle any restrictions sent to us. This only handles
// the TABLE_NAME & TABLE_TYPE restictions (the 3rd and 4th
// restrictions in DBSCHEMA_TABLES...look in IDBSchemaRowsets
// in part 2 of the prog. ref) so your restrictions are 0x08 & 0x04
// for a total of (0x0C)
if (cRestrictions >= 3 && rgRestrictions[2].vt != VT_EMPTY)
{
    CComBSTR bstrName = rgRestrictions[2].bstrVal;
    if ((rgRestrictions[2].vt == VT_BSTR) && (bstrName != (BSTR)NULL))
    {
        // Check to see if the file exists
        _tcscpy_s(&szFile[0], sizeOfszFile, OLE2T(bstrName));
        if (szFile[0] == _T('\0') ||
           ((err = _tfopen(&pFile, &szFile[0], _T("r"))) == 0))
        {
            return S_OK;// Their restriction was invalid return no data
        }
        else
        {
            fclose(pFile);
        }
    }
}
```

Die vierte Beschränkung (**TABLE_TYPE**) ist die dritte Beschränkung vergleichbar. Überprüfen, ob der Wert nicht VT_EMPTY ist. Diese Einschränkung gibt nur den Tabellentyp **Tabelle**. Zur Bestimmung der gültigen Werte für die `DBSCHEMA_TABLES`, suchen Sie in Anhang B der der *OLE DB-Programmierreferenz* in die **Tabellen** Rowset-Abschnitt.

```cpp
// TABLE_TYPE restriction:
if (cRestrictions >=4 && rgRestrictions[3].vt != VT_EMPTY)
{
    CComBSTR bstrType = rgRestrictions[3].bstrVal;
    if ((rgRestrictions[3].vt == VT_BSTR) && (bstrType != (BSTR)NULL))
    {
        // This is kind of a blind restriction.
        // This only actually supports
        // TABLES so if you get anything else,
        // just return an empty rowset.
        if (_tcscmp(_T("TABLE"), OLE2T(bstrType)) != 0)
            return S_OK;
    }
}
```

Dies ist in dem Sie einen Zeileneintrag, für das Rowset erstellen. Die Variable `trData` entspricht `CTABLESRow`, eine Struktur, in der OLE DB-Anbietervorlagen definiert. `CTABLESRow` entspricht der **Tabellen** Rowsetdefinition in Anhang B der OLE DB-Spezifikation. Sie müssen nur eine Zeile hinzufügen, da Sie nur eine Tabelle zu einem Zeitpunkt unterstützen können.

```cpp
// Bring over the data:
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());
```

UpdatePV nur drei Spalten: **TABLE_NAME**, **TABLE_TYPE**, und **Beschreibung**. Da Sie diese Informationen benötigen, bei der Implementierung, notieren Sie sich die Spalten, die für die Informationen zurückgegeben werden, sollten `GetDBStatus`:

```cpp
    _ATLTRY
    {
        m_rgRowData.Add(trData);
    }
    _ATLCATCHALL()
    {
        return E_OUTOFMEMORY;
    }
    //if (!m_rgRowData.Add(trData))
    //    return E_OUTOFMEMORY;
    *pcRowsAffected = 1;
    return S_OK;
}
```

Die `GetDBStatus` Funktion ist sehr wichtig, den ordnungsgemäßen Betrieb des-Schemarowsets. Da Sie keine Daten für jede Spalte in Zurückgeben der **Tabellen** Rowset, müssen Sie angeben, welche Spalten Sie Daten zurückgegeben werden und welche nicht.

```cpp
virtual DBSTATUS GetDBStatus(CSimpleRow* , ATLCOLUMNINFO* pColInfo)
{
    ATLASSERT(pColInfo != NULL);

    switch(pColInfo->iOrdinal)
    {
    case 3:     // TABLE_NAME
    case 4:     // TABLE_TYPE
    case 6:     // DESCRIPTION
        return DBSTATUS_S_OK;
        break;
    default:
        return DBSTATUS_S_ISNULL;
    break;
    }
}
```

Da Ihre `Execute` Funktion gibt Daten für die **TABLE_NAME**, **TABLE_TYPE**, und **Beschreibung** Felder aus der **Tabellen**Rowset, suchen Sie in Anhang B der OLE DB-Spezifikation und bestimmt werden kann (durch Zählen von oben nach unten), dass sie die Ordinalzahlen, 3, 4 und 6 sind. Zurückgeben Sie für jede dieser Spalten DBSTATUS_S_OK. Geben Sie für alle anderen Spalten DBSTATUS_S_ISNULL zurück. Es ist wichtig, dass dieser Status zurückgegeben, da ein Consumer nicht erkennen kann, dass der zurückgegebene Wert NULL oder etwas anderes ist. Beachten Sie in diesem Fall, dass NULL keine leerer entspricht.

Weitere Informationen zu den OLE DB-Schemarowset-Schnittstelle, finden Sie unter den [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) -Schnittstelle in der OLE DB Programmer's Reference.

Informationen zur Verwendung von Consumern `IDBSchemaRowset` Methoden finden Sie unter [Abrufen von Metadaten mit Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).

Ein Beispiel für einen Anbieter, der Schemarowsets unterstützt, finden Sie unter dem Beispiel [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) .

## <a name="see-also"></a>Siehe auch

[Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)
