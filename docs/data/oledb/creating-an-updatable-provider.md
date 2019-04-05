---
title: Erstellen eines aktualisierbaren Anbieters
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: d3f8314e7cd57617e35e50a67a4562d4055cb93a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024737"
---
# <a name="creating-an-updatable-provider"></a>Erstellen eines aktualisierbaren Anbieters

Visual C++ unterstützt aktualisierbare Anbieter oder Anbieter, die aktualisiert werden können (Schreiben) dem Datenspeicher. In diesem Thema wird erläutert, wie aktualisierbare Anbieter, die mithilfe von OLE DB-Vorlagen erstellt werden.

In diesem Thema wird davon ausgegangen, dass Sie mit einem praktikable Anbieter starten. Es gibt zwei Schritte zum Erstellen eines aktualisierbaren Anbieters. Zunächst müssen Sie entscheiden, wie der Anbieter Änderungen an den Datenspeicher vereinfachen; insbesondere gibt an, ob Änderungen werden sofort erfolgen oder verzögert, bis ein Updatebefehl ausgegeben wird. Im Abschnitt "[aktualisierbare Anbieter machen](#vchowmakingprovidersupdatable)" beschreibt die Änderungen und die Einstellungen, die Sie in den Anbietercode tun müssen.

Als Nächstes müssen Sie sicherstellen, dass Ihr Anbieter enthält die gesamte Funktionalität zur Unterstützung der Consumer des anfordern kann. Wenn der Consumer den Datenspeicher zu aktualisieren möchte, muss der Anbieter Code enthalten, die Daten im Datenspeicher beibehalten. Beispielsweise können Sie der C-Laufzeitbibliothek oder die MFC-verwenden, um die Vorgänge an der Datenquelle auszuführen. Im Abschnitt "[Schreiben in die Datenquelle](#vchowwritingtothedatasource)" beschreibt, wie Sie mit der Datenquelle zu schreiben, befassen sich mit NULL-und Standardwerten und Spaltenflags festlegen.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) ist ein Beispiel eines aktualisierbaren Anbieters. UpdatePV ist identisch, wie MyProv, jedoch mit aktualisierbaren Unterstützung.

##  <a name="vchowmakingprovidersupdatable"></a> Machen Anbieter aktualisiert

Einen Anbieter aktualisierbare entscheidend besteht im ermitteln welche Vorgänge Sie möchten Ihren Anbieter, führen Sie auf den Datenspeicher und wie der Anbieter diese Vorgänge ausführen soll. Insbesondere das wesentliche Problem ist, ob Updates für den Datenspeicher sind sofort ausgeführt oder verzögert werden soll (Batchverarbeitung) bis ein Update-Befehl ausgegeben wird.

Zunächst müssen Sie entscheiden, ob die von erben `IRowsetChangeImpl` oder `IRowsetUpdateImpl` in der Rowsetklasse. Je nachdem, welche dieser Sie implementieren, die Funktionalität von drei Methoden sind betroffen: `SetData`, `InsertRows`, und `DeleteRows`.

- Wenn das erben [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), ändert sich den Datenspeicher diese drei Methoden direkt aufzurufen.

- Wenn das erben [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), die Methoden Änderungen an den Datenspeicher verzögern, bis zum Aufruf von `Update`, `GetOriginalData`, oder `Undo`. Wenn das Update mehrere Änderungen betrifft, werden sie ausgeführt, im Modus "Batch" (Beachten Sie, dass die Batchverarbeitung von Änderungen viel Speicher-Overhead hinzufügen kann).

Beachten Sie, dass `IRowsetUpdateImpl` leitet sich von `IRowsetChangeImpl`. Daher `IRowsetUpdateImpl` erhalten Sie die Funktion und der Batch-Funktion ändern.

### <a name="to-support-updatability-in-your-provider"></a>Zur Unterstützung von aktualisierbarkeit im Anbieter

1. In der Rowsetklasse erben `IRowsetChangeImpl` oder `IRowsetUpdateImpl`. Diese Klassen bieten die entsprechende Schnittstellen für das Ändern des Datenspeichers:

   **Hinzufügen von IRowsetChange**

   Hinzufügen `IRowsetChangeImpl` der Vererbungskette, die mit dieser Form:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Auch hinzufügen, `COM_INTERFACE_ENTRY(IRowsetChange)` auf die `BEGIN_COM_MAP` Abschnitt in der Rowsetklasse.

   **IRowsetUpdate hinzufügen**

   Hinzufügen `IRowsetUpdate` der Vererbungskette, die mit dieser Form:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > Entfernen Sie die `IRowsetChangeImpl` Zeile aus der Vererbungskette. Diese Ausnahme von der zuvor erwähnten Direktive muss den Code für enthalten `IRowsetChangeImpl`.

1. Fügen Sie Folgendes der COM-Zuordnung (`BEGIN_COM_MAP ... END_COM_MAP`):

   |  Wenn Sie implementieren   |           COM-Zuordnung hinzufügen             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | Wenn Sie implementieren | Fügen Sie zum Festlegen der eigenschaftenzuordnung |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. Fügen Sie in zunutze, Folgendes ein, um die Zuordnung des Set (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):

   |  Wenn Sie implementieren   |                                             Fügen Sie zum Festlegen der eigenschaftenzuordnung                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. In der Zuordnung des Eigenschaftensets sollten Sie auch alle der folgenden Einstellungen hinzufügen wie sie unten angezeigt werden:

    ```cpp
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)

    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)
    ```

   Sie finden die Werte in diesen anhand Atldb.h für die Eigenschaft-IDs und Werte (wenn die Onlinedokumentation Atldb.h unterscheidet, Atldb.h Vorrang vor der Dokumentation).

   > [!NOTE]
   > Viele der `VARIANT_FALSE` und `VARIANT_TRUE` Einstellungen sind erforderlich, durch die OLE DB-Vorlagen, die OLE DB-Spezifikation sagt, können sie Lese-/Schreibzugriff sein, aber die OLE DB-Vorlagen unterstützt nur einen Wert.

   **Wenn Sie IRowsetChangeImpl implementieren**

   Wenn Sie implementieren `IRowsetChangeImpl`, Sie müssen die folgenden Eigenschaften festlegen, für den Anbieter. Diese Eigenschaften werden in erster Linie verwendet, um die Schnittstellen durch anzufordern `ICommandProperties::SetProperties`.

   - `DBPROP_IRowsetChange`: Diesem automatisch die Einstellung `DBPROP_IRowsetChange`.

   - `DBPROP_UPDATABILITY`: Bitmaske, die die unterstützten Methoden für `IRowsetChange`: `SetData`, `DeleteRows`, oder `InsertRow`.

   - `DBPROP_CHANGEINSERTEDROWS`: Consumer kann Aufrufen `IRowsetChange::DeleteRows` oder `SetData` für neu eingefügte Zeilen.

   - `DBPROP_IMMOBILEROWS`: Rowset nicht eingefügte oder aktualisierte Zeilen neu angeordnet.

   **Wenn Sie IRowsetUpdateImpl implementieren**

   Wenn Sie implementieren `IRowsetUpdateImpl`, müssen Sie die folgenden Eigenschaften festlegen für den Anbieter darüber hinaus mit dem Festlegen aller Eigenschaften für `IRowsetChangeImpl` oben aufgeführt:

   - `DBPROP_IRowsetUpdate`sein.

   - `DBPROP_OWNINSERT`: READ_ONLY und VARIANT_TRUE ist erforderlich.

   - `DBPROP_OWNUPDATEDELETE`: READ_ONLY und VARIANT_TRUE ist erforderlich.

   - `DBPROP_OTHERINSERT`: READ_ONLY und VARIANT_TRUE ist erforderlich.

   - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY und VARIANT_TRUE ist erforderlich.

   - `DBPROP_REMOVEDELETED`: READ_ONLY und VARIANT_TRUE ist erforderlich.

   - `DBPROP_MAXPENDINGROWS`sein.

   > [!NOTE]
   > Wenn Sie Benachrichtigungen unterstützen, müssen Sie auch einige andere Eigenschaften sowie möglicherweise; finden Sie im Abschnitt `IRowsetNotifyCP` für diese Liste.

##  <a name="vchowwritingtothedatasource"></a> Das Schreiben in die Datenquelle

Um Daten aus der Datenquelle zu lesen, rufen Sie die `Execute` Funktion. Rufen Sie zum Schreiben an die Datenquelle die `FlushData` Funktion. (In einem allgemeinen Sinn, leeren Sie die Möglichkeit, Änderungen zu speichern, die Sie an einer Tabelle oder eines Indexes auf dem Datenträger.)

```cpp
FlushData(HROW, HACCESSOR);
```

Das Zeilenhandle (HROW) Argumente und das Accessorhandle (HACCESSOR) können Sie angeben, die Region, in Sie schreiben. In der Regel schreiben Sie ein einzelnes Datenfeld zu einem Zeitpunkt.

Die `FlushData` Methode schreibt Daten in das Format, in dem sie ursprünglich gespeichert. Wenn Sie diese Funktion nicht überschreiben, Ihrem Anbieter richtig funktioniert, aber Änderungen im Datenspeicher werden nicht geleert.

### <a name="when-to-flush"></a>Beim leeren

Die Anbietervorlagen FlushData aufgerufen, wenn Daten an den Datenspeicher geschrieben werden müssen. Dies geschieht in der Regel (aber nicht immer) als Ergebnis der Aufrufe an die folgenden Funktionen:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (wenn es sich um eine neue Daten zum Einfügen in die Zeile vorhanden sind)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>So funktioniert es

Der Consumer aufruft, die eine Bereinigung (z. B. Update) erforderlich sind, und dieser Aufruf an den Anbieter, der immer den folgenden Funktionen übergeben wird:

- Aufrufe `SetDBStatus` jedes Mal, wenn Sie einen Statuswert gebunden haben.

- Überprüft die Spaltenflags.

- Ruft `IsUpdateAllowed`.

Diese drei Schritte stellen die Sicherheit bereit. Anschließend ruft der Anbieter `FlushData`.

### <a name="how-to-implement-flushdata"></a>Gewusst wie: Implementieren von FlushData

Zum Implementieren `FlushData`, müssen Sie einige Aspekte berücksichtigt:

Sicherstellen, dass der Datenspeicher Änderungen verarbeiten kann.

Behandeln von NULL-Werte.

### <a name="handling-default-values"></a>Behandeln von Standardwerten.

Zur Implementierung einer eigenen `FlushData` -Methode, Sie möchten:

- Wechseln Sie zu Ihrem Rowset-Klasse.

- Fügen Sie in das Rowset die Deklaration der Klasse:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- Eine Implementierung der `FlushData`.

Eine gute Implementierung `FlushData` speichert nur die Zeilen und Spalten, die tatsächlich aktualisiert werden. Sie können die HROW und HACCESSOR-Parameter verwenden, um zu bestimmen, die aktuelle Zeile und Spalte für die Optimierung gespeichert werden.

In der Regel ist die größte Herausforderung mit Ihren eigenen systemeigenen Datenspeicher arbeiten. Wenn möglich, versuchen Sie es auf:

- Behalten Sie die Methode beim Schreiben in Ihrem Datenspeicher, die so einfach wie möglich.

- Behandeln von NULL-Werten (optional, jedoch empfohlen).

- Behandeln Sie die Standardwerte (optional, jedoch empfohlen).

Die beste Vorgehensweise besteht darin aktuelle Werte im Datenspeicher für NULL-und Standardwerten. Es wird empfohlen, wenn Sie diese Daten extrapolieren können. Wenn dies nicht der Fall ist, sollten Sie keine NULL-und Standardwerten zu ermöglichen.

Das folgende Beispiel zeigt wie `FlushData` wird implementiert, der `RUpdateRowset` -Klasse in der `UpdatePV` Beispiel (siehe Rowset.h im Beispielcode):

```cpp
///////////////////////////////////////////////////////////////////////////
// class RUpdateRowset (in rowset.h)
...
HRESULT FlushData(HROW, HACCESSOR)
{
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");

    USES_CONVERSION;
    enum {
        sizeOfString = 256,
        sizeOfFileName = MAX_PATH
    };
    FILE*    pFile = NULL;
    TCHAR    szString[sizeOfString];
    TCHAR    szFile[sizeOfFileName];
    errcode  err = 0;

    ObjectLock lock(this);

    // From a filename, passed in as a command text,
    // scan the file placing data in the data array.
    if (m_strCommandText == (BSTR)NULL)
    {
        ATLTRACE( "RRowsetUpdate::FlushData -- "
                  "No filename specified\n");
        return E_FAIL;
    }

    // Open the file
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));
    if ((szFile[0] == _T('\0')) ||
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))
    {
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");
        return DB_E_NOTABLE;
    }

    // Iterate through the row data and store it.
    for (long l=0; l<m_rgRowData.GetSize(); l++)
    {
        CAgentMan am = m_rgRowData[l];

        _putw((int)am.dwFixed, pFile);

        if (_tcscmp(&am.szCommand[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);
    }

    if (fflush(pFile) == EOF || fclose(pFile) == EOF)
    {
        ATLTRACE("RRowsetUpdate::FlushData -- "
                 "Couldn't flush or close file\n");
    }

    return S_OK;
}
```

### <a name="handling-changes"></a>Behandeln von Änderungen

Für Ihren Anbieter, um Änderungen zu bewältigen müssen Sie zunächst sicherstellen, dass Ihrer Data Store (z. B. eine Textdatei oder eine Videodatei) verfügt über Funktionen, mit die Sie Änderungen daran vornehmen können. Wenn dies nicht der Fall ist, sollten Sie diesen Code separat aus dem Anbieterprojekt erstellen.

### <a name="handling-null-data"></a>Behandeln von NULL-Daten

Es ist möglich, dass ein Endbenutzer mit NULL-Daten gesendet werden. Wenn Sie NULL-Werte für Felder in der Datenquelle schreiben, können potenzielle Probleme vorhanden sein. Stellen Sie sich vor einer Order-erstellen-Anwendung, die Werte für Stadt und Postleitzahl akzeptiert; Es konnte eine oder beide Werte verwenden, aber nicht beide, annehmen, da in diesem Fall die Übermittlung nicht möglich wäre. Aus diesem Grund müssen Sie bestimmte Kombinationen von NULL-Werte in Feldern, die für Ihre Anwendung sinnvoll.

Als Entwickler des Anbieters müssen Sie berücksichtigen, wie Sie diese Daten gespeichert werden, wie Sie die Daten aus dem Datenspeicher gelesen werden und wie Sie angeben, dass für den Benutzer. Insbesondere müssen Sie berücksichtigen, wie den Status von Rowsetdaten in der Datenquelle zu ändern (z. B. DataStatus = NULL). Sie entscheiden, welcher Wert zurückgegeben, wenn ein Consumer ein Feld, enthält einen NULL-Wert zugreift.

Sehen Sie sich den Code im Beispiel UpdatePV; Es wird veranschaulicht, wie NULL-Daten von ein Anbieter verarbeitet werden kann. In UpdatePV speichert der Anbieter durch Schreiben die Zeichenfolge "NULL" NULL-Daten im Datenspeicher an. Wenn sie NULL-Daten aus dem Datenspeicher liest, wird diese Zeichenfolge und anschließend leert den Puffer, erstellen Sie eine NULL-Zeichenfolge. Sie hat auch eine Überschreibung der `IRowsetImpl::GetDBStatus` in dem sie DBSTATUS_S_ISNULL zurückgegeben werden soll, wenn der Wert dieser Daten leer ist.

### <a name="marking-nullable-columns"></a>Auf NULL festlegbare Spalten markieren

Wenn Sie die Schemarowsets auch implementieren (finden Sie unter `IDBSchemaRowsetImpl`), Ihre Implementierung sollten im DBSCHEMA_COLUMNS-Rowset (normalerweise in Ihrem Anbieter von CxxxSchemaColSchemaRowset gekennzeichnet) angeben, dass die Spalte NULL-Werte zulässt.

Sie müssen auch angeben, dass alle auf NULL festlegbare Spalten, den DBCOLUMNFLAGS_ISNULLABLE-Wert in Ihrer Version von enthalten der `GetColumnInfo`.

In der Implementierung des OLE DB-Vorlagen Wenn Sie nicht zum Kennzeichnen von Spalten als NULL-Werte zulässt, wird davon ausgegangen des Anbieters, dass sie einen Wert enthalten müssen, und sich nicht auf den Consumer zum Senden von null-Werte lässt.

Das folgende Beispiel zeigt die `CommonGetColInfo` in CUpdateCommand Funktion implementiert ist (Siehe UpProvRS.cpp) in UpdatePV. Beachten Sie, wie die Spalten auf NULL festlegbare Spalten DBCOLUMNFLAGS_ISNULLABLE für.

```cpp
/////////////////////////////////////////////////////////////////////////////
// CUpdateCommand (in UpProvRS.cpp)

ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)
{
    static ATLCOLUMNINFO _rgColumns[6];
    ULONG ulCols = 0;

    if (bBookmark)
    {
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                            sizeof(DWORD), DBTYPE_BYTES,
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                            DBCOLUMNFLAGS_ISBOOKMARK)
        ulCols++;
    }

    // Next set the other columns up.
    // Add a fixed length entry for OLE DB conformance testing purposes
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,
                        10, 255, GUID_NULL, CAgentMan, dwFixed,
                        DBCOLUMNFLAGS_WRITE |
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    if (pcCols != NULL)
    {
        *pcCols = ulCols;
    }

    return _rgColumns;
}
```

### <a name="default-values"></a>Standardwerte

Wie bei NULL-Daten, müssen Sie die Verantwortung für den Umgang mit der Änderung der Standardwerte.

Die Standardeinstellung `FlushData` und `Execute` wird S_OK zurückgegeben. Aus diesem Grund, wenn Sie diese Funktion nicht überschreiben, die Änderungen angezeigt werden erfolgreich ausgeführt werden kann (S_OK zurückgegeben), aber sie werden nicht an den Datenspeicher übertragen werden.

In der `UpdatePV` Beispiel (in Rowset.h) die `SetDBStatus` Methode Standardwerte wie folgt verarbeitet:

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,
                            ATLCOLUMNINFO* pColInfo)
{
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);

    void* pData = NULL;
    char* pDefaultData = NULL;
    DWORD* pFixedData = NULL;

    switch (*pdbStatus)
    {
        case DBSTATUS_S_DEFAULT:
            pData = (void*)&m_rgRowData[pRow->m_iRowset];
            if (pColInfo->wType == DBTYPE_STR)
            {
                pDefaultData = (char*)pData + pColInfo->cbOffset;
                strcpy_s(pDefaultData, "Default");
            }
            else
            {
                pFixedData = (DWORD*)((BYTE*)pData +
                                          pColInfo->cbOffset);
                *pFixedData = 0;
                return S_OK;
            }
            break;
        case DBSTATUS_S_ISNULL:
        default:
            break;
    }
    return S_OK;
}
```

### <a name="column-flags"></a>Spaltenflags

Wenn Sie Standardwerte für Spalten unterstützt, müssen Sie mithilfe von Metadaten im Festlegen der \<Anbieterklasse\>SchemaRowset-Klasse. Legen Sie `m_bColumnHasDefault = VARIANT_TRUE` fest.

Sie können auch dafür verantwortlich, die Spaltenflags, die festlegen, mit dem DBCOLUMNFLAGS-Enumerationstyp angegeben werden. Die Spaltenflags werden Spalteneigenschaften beschrieben.

Z. B. in der `CUpdateSessionColSchemaRowset` -Klasse im `UpdatePV` (in Session.h), die erste Spalte auf diese Weise eingerichtet:

```cpp
// Set up column 1
trData[0].m_ulOrdinalPosition = 1;
trData[0].m_bIsNullable = VARIANT_FALSE;
trData[0].m_bColumnHasDefault = VARIANT_TRUE;
trData[0].m_nDataType = DBTYPE_UI4;
trData[0].m_nNumericPrecision = 10;
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));
m_rgRowData.Add(trData[0]);
```

Dieser Code gibt an, unter anderem, dass die Spalte den Standardwert 0 (null) unterstützt, dass sie beschreibbar sein und alle Daten in der Spalte auf die gleiche Länge besitzen. Wenn Sie die Daten in eine Spalte Variablen Länge haben möchten, würden Sie dieses Flag nicht festgelegt.

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](creating-an-ole-db-provider.md)