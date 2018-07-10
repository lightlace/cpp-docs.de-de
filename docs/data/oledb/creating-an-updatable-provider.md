---
title: Erstellen eines aktualisierbaren Anbieters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 317ccd043b3a69489f9cbd2737ad7741389863c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098640"
---
# <a name="creating-an-updatable-provider"></a>Erstellen eines aktualisierbaren Anbieters
Visual C++ unterstützt aktualisierbare Anbieter oder Anbieter, die aktualisiert werden können (Schreiben) den Datenspeicher. In diesem Thema erläutert, wie aktualisierbare Anbieter mithilfe von OLE DB-Vorlagen zu erstellen.  
  
 In diesem Thema wird davon ausgegangen, dass Sie mit einem praktikable Anbieter gestartet werden. Es gibt zwei Schritte zum Erstellen eines aktualisierbaren Anbieters aus. Zuerst müssen Sie entscheiden, wie der Anbieter Änderungen im Datenspeicher vornehmen. insbesondere, ob Änderungen werden sofort ausgeführt werden oder verzögert, bis ein Updatebefehl ausgegeben wird. Im Abschnitt "[aktualisierbare Anbieter machen](#vchowmakingprovidersupdatable)" beschreibt die Änderungen und die Einstellungen, die Sie in den Anbietercode ausführen müssen.  
  
 Als Nächstes müssen Sie sicherstellen, dass Ihr Anbieter enthält die gesamte Funktionalität zur Unterstützung der Consumer davon anfordern kann. Wenn der Consumer den Datenspeicher zu aktualisieren möchte, muss der Anbieter Code enthalten, die Daten im Datenspeicher beibehält. Beispielsweise können Sie die C-Laufzeitbibliothek oder MFC für solche Vorgänge auf Ihre Datenquelle verwenden. Im Abschnitt "[in die Datenquelle schreibt](#vchowwritingtothedatasource)" wird beschrieben, wie mit der Datenquelle zu schreiben, damit zurecht **NULL** Standardwerte fest und legen Flags für Miningmodellspalten.  
  
> [!NOTE]
>  UpdatePV ist ein Beispiel eines aktualisierbaren Anbieters. UpdatePV entspricht dem als MyProv jedoch mit Unterstützung für aktualisierbare.  
  
##  <a name="vchowmakingprovidersupdatable"></a> Anbieter aktualisierbar machen  
 Der Schlüssel zum Erstellen eines Anbieters aktualisierbare besteht im ermitteln welche Vorgänge Sie Ihren Anbieter für den Datenspeicher und Vorstellung den Anbieter zum Ausführen dieser Vorgänge ausführen möchten. Insbesondere das größte Problem ist, ob Updates für den Datenspeicher sind sofort ausgeführt oder zurückgestellt werden (Batch), bis ein Updatebefehl ausgegeben wird.  
  
 Zunächst müssen Sie entscheiden, ob die von erben `IRowsetChangeImpl` oder `IRowsetUpdateImpl` in der Rowsetklasse. Je nachdem, was Sie implementieren möchten, die Funktionalität der drei Methoden betroffen: `SetData`, **InsertRows**, und `DeleteRows`.  
  
-   Erben von [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), den Datenspeicher ändert diese drei Methoden direkt aufzurufen.  
  
-   Erben von [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), die Methoden Änderungen an den Datenspeicher verzögern, bis zum Aufruf von **Update**, `GetOriginalData`, oder **Rückgängig**. Wenn das Update mehrere Änderungen beteiligt ist, werden sie ausgeführt, im Batchmodus (Beachten Sie, dass Batchverarbeitung Änderungen viel Arbeitsspeicher hinzufügen kann).  
  
 Beachten Sie, dass `IRowsetUpdateImpl` leitet sich von `IRowsetChangeImpl`. Folglich `IRowsetUpdateImpl` erhalten Sie die Funktion plus Batch-Funktion ändern.  
  
#### <a name="to-support-updatability-in-your-provider"></a>Zur Unterstützung von aktualisierbarkeit im Anbieter  
  
1.  In der Rowsetklasse, die von erben `IRowsetChangeImpl` oder `IRowsetUpdateImpl`. Diese Klassen bieten die entsprechende Schnittstellen für das Ändern des Datenspeichers:  
  
     **Hinzufügen von IRowsetChange**  
  
     Hinzufügen `IRowsetChangeImpl` der Vererbungskette dieser Form verwenden:  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Auch hinzufügen `COM_INTERFACE_ENTRY(IRowsetChange)` auf die `BEGIN_COM_MAP` Abschnitt in der Rowsetklasse.  
  
     **Hinzufügen von IRowsetUpdate**  
  
     Hinzufügen `IRowsetUpdate` der Vererbungskette dieser Form verwenden:  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Entfernen Sie die `IRowsetChangeImpl` Zeile aus der Vererbungskette. Diese Ausnahme von der zuvor erwähnten Direktive muss den Code für enthalten `IRowsetChangeImpl`.  
  
2.  Fügen Sie die folgenden der COM-Karte (**BEGIN_COM_MAP... END_COM_MAP**):  
  
    |Wenn Sie implementieren|Fügen zu COM-Karte hinzu|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  In Ihrem Befehl fügen Sie die folgenden der Eigenschaft Set-Karte (**BEGIN_PROPSET_MAP... END_PROPSET_MAP**):  
  
    |Wenn Sie implementieren|Festlegen der eigenschaftenzuordnung hinzufügen|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  In Ihrer Zuordnung Eigenschaft festlegen sollten Sie auch alle der folgenden Einstellungen einschließen, wie diese unten angezeigt werden:  
  
    ```  
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
  
     Sie finden die Werte in diesen Makros aufrufen durch einen Blick in "Atldb.h" für die Eigenschaft-IDs und Werte verwendet (Wenn "Atldb.h" aus der Onlinedokumentation abweicht, "Atldb.h" Vorrang vor der Dokumentation).  
  
    > [!NOTE]
    >  Anzahl der **VARIANT_FALSE** und `VARIANT_TRUE` Einstellungen sind erforderlich, durch den OLE DB-Vorlagen, die OLE DB-Spezifikation besagt, dass Lese-/Schreibzugriff sein, aber die OLE DB-Vorlagen unterstützen nur einen Wert.  
  
     **Wenn Sie IRowsetChangeImpl implementieren**  
  
     Wenn Sie implementieren `IRowsetChangeImpl`, müssen Sie die folgenden Eigenschaften für den Anbieter festlegen. Diese Eigenschaften sind in erster Linie verwendet, um über Schnittstellen anzufordern **ICommandProperties:: SetProperties**.  
  
    -   `DBPROP_IRowsetChange`: Wenn dieser automatisch festgelegt **DBPROP_IRowsetChange**.  
  
    -   `DBPROP_UPDATABILITY`: Eine Bitmaske, die die unterstützten Methoden auf `IRowsetChange`: `SetData`, `DeleteRows`, oder `InsertRow`.  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: Der Consumer kann Aufrufen **IRowsetChange:: DeleteRows** oder `SetData` für neu eingefügte Zeilen.  
  
    -   `DBPROP_IMMOBILEROWS`: Rowset eingefügte oder aktualisierte Zeilen nicht neu angeordnet.  
  
     **Wenn Sie IRowsetUpdateImpl implementieren**  
  
     Wenn Sie implementieren `IRowsetUpdateImpl`, müssen Sie die folgenden Eigenschaften für den Anbieter darüber hinaus auf festlegen Festlegen der Eigenschaften für `IRowsetChangeImpl` zuvor aufgeführt:  
  
    -   `DBPROP_IRowsetUpdate`  
  
    -   `DBPROP_OWNINSERT`: READ_ONLY und VARIANT_TRUE muss sein werden.  
  
    -   `DBPROP_OWNUPDATEDELETE`: READ_ONLY und VARIANT_TRUE muss sein werden.  
  
    -   `DBPROP_OTHERINSERT`: READ_ONLY und VARIANT_TRUE muss sein werden.  
  
    -   `DBPROP_OTHERUPDATEDELETE`: READ_ONLY und VARIANT_TRUE muss sein werden.  
  
    -   `DBPROP_REMOVEDELETED`: READ_ONLY und VARIANT_TRUE muss sein werden.  
  
    -   `DBPROP_MAXPENDINGROWS`  
  
        > [!NOTE]
        >  Wenn Sie Benachrichtigungen unterstützen, müssen Sie möglicherweise auch über einige andere Eigenschaften als auch; Siehe den Abschnitt `IRowsetNotifyCP` für diese Liste.  
  
     Z. B. wie die Eigenschaften festgelegt werden, finden Sie unter die Eigenschaftensatz-Zuordnung **CUpdateCommand** (in Rowset.h) in [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
##  <a name="vchowwritingtothedatasource"></a> Das Schreiben in die Datenquelle  
 Rufen Sie zum Lesen aus der Datenquelle die **Execute** Funktion. Rufen Sie zum Schreiben an die Datenquelle die `FlushData` Funktion. (In einem allgemeinen Sinn, leeren Sie die Möglichkeit zum Speichern von Änderungen, die Sie an einer Tabelle oder eines Indexes, auf den Datenträger.)  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 Das Zeilenhandle (*HROW*) und Accessorhandle (*HACCESSOR*) Argumente ermöglichen es Ihnen, geben Sie die Region, in Sie schreiben. Schreiben Sie in der Regel ein einzelnes Datenfeld zu einem Zeitpunkt.  
  
 Die `FlushData` -Methode schreibt Daten in das Format, in dem sie ursprünglich gespeichert. Wenn Sie diese Funktion nicht überschreiben, Ihren Anbieter ordnungsgemäß funktioniert, aber Änderungen werden im Datenspeicher nicht geleert werden.  
  
### <a name="when-to-flush"></a>Wenn beim leeren  
 Die Anbietervorlagen rufen `FlushData` Wenn Daten in den Datenspeicher geschrieben werden müssen; dies in der Regel (aber nicht immer) tritt als Ergebnis der Aufrufe an die folgenden Funktionen:  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** (wenn neue Daten zum Einfügen in die Zeile)  
  
-   **IRowsetUpdate::Update**  
  
### <a name="how-it-works"></a>Funktionsweise  
 Der Consumer aufruft, die eine Bereinigung erforderlich sind (z. B. **Update**) und dieser Aufruf an den Anbieter, der immer die wie folgt vorgeht übergeben wird:  
  
-   Aufrufe `SetDBStatus` immer Sie einen Statuswert gebunden haben (finden Sie unter *OLE DB Programmer's Reference*, Kapitel 6, *Datenausschnitte: Status*).  
  
-   Überprüft die Flags für Miningmodellspalten.  
  
-   Ruft `IsUpdateAllowed`.  
  
 Diese drei Schritte können Sicherheit zu gewährleisten. Anschließend ruft der Anbieter `FlushData`.  
  
### <a name="how-to-implement-flushdata"></a>Gewusst wie: Implementieren von FlushData  
 Implementiert `FlushData`, müssen Sie mehrere Aspekte berücksichtigt:  
  
-   Sicherstellen, dass der Datenspeicher Änderungen verarbeiten kann.  
  
-   Behandlung von **NULL** Werte.  
  
-   Behandlung von Standardwerten.  
  
 Zur Implementierung einer eigenen `FlushData` -Methode, müssen Sie:  
  
-   Fahren Sie mit der Rowsetklasse.  
  
-   Platzieren Sie im Rowset die Deklaration der Klasse:  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   Stellen Sie eine Implementierung von `FlushData`.  
  
 Eine gute Implementierung der `FlushData` speichert nur die Zeilen und Spalten, die tatsächlich aktualisiert werden. Sie können die *HROW* und *HACCESSOR* Parameter, um zu bestimmen, die aktuelle Zeile und Spalte für die Optimierung gespeichert werden.  
  
 In der Regel ist die größte Herausforderung mit Ihren eigenen systemeigenen Datenspeicher arbeiten. Versuchen Sie nach Möglichkeit auf:  
  
-   Behalten Sie die Methode zum Schreiben von Daten in den Datenspeicher so einfach wie möglich.  
  
-   Behandeln **NULL** Werte (optional, jedoch empfohlen).  
  
-   Behandeln Sie die Standardwerte (optional, jedoch empfohlen).  
  
 Die beste Vorgehensweise ist damit angegebenen Istwerte in den Datenspeicher für **NULL** und Standardwerte. Es wird empfohlen, wenn Sie diese Daten extrapolieren können. Wenn nicht der Fall, wird empfohlen, nicht zu erlauben **NULL** und Standardwerte.  
  
 Das folgende Beispiel zeigt wie `FlushData` implementiert wird, der `RUpdateRowset` -Klasse in der [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) Beispiel (siehe Rowset.h im Beispielcode):  
  
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
  
### <a name="handling-changes"></a>Behandlung von Änderungen  
 Für den Anbieter so behandeln Sie Änderungen müssen Sie zunächst sicherstellen, dass der Datenspeicher (z. B. eine Textdatei oder eine Videodatei) Funktionen verfügt, die Ihnen ermöglichen, die sie ändern möchten. Wenn dies nicht der Fall ist, sollten Sie diesen Code separat aus dem Anbieterprojekt erstellen.  
  
### <a name="handling-null-data"></a>Behandlung von NULL-Daten  
 Es ist möglich, dass ein Endbenutzer sendet **NULL** Daten. Beim Erstellen von **NULL** Werte zu Feldern in der Datenquelle werden potenzielle Probleme. Angenommen Sie, eine Order-Aufnahme-Anwendung, die Werte für Stadt und Postleitzahl akzeptiert; Es konnte eine oder beide Werte verwenden, aber nicht beide, annehmen, weil in diesem Fall die Übermittlung nicht möglich wäre. Aus diesem Grund müssen Sie bestimmte Kombinationen von **NULL** Werte in Feldern, die für Ihre Anwendung sinnvoll.  
  
 Als Entwickler des Anbieters müssen Sie berücksichtigen, wie Sie die Daten speichern möchten, wie Sie die Daten aus dem Datenspeicher gelesen werden und wie Sie angeben, dass für den Benutzer. Insbesondere müssen Sie überlegen, wie den Status von Rowsetdaten in der Datenquelle zu ändern (z. B. DataStatus = **NULL**). Sie entscheiden, welcher Wert zurückgegeben, wenn ein Consumer ein Feld mit greift auf eine **NULL** Wert.  
  
 Sehen Sie sich den Code in der [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) Beispiel; es wird veranschaulicht, wie ein Anbieter behandeln kann **NULL** Daten. In "UpdatePV" die Anbieter speichert **NULL** Daten durch die Zeichenfolge "NULL" in den Datenspeicher schreiben. Beim Lesen **NULL** Daten aus den Daten zu speichern, erkennt diese Zeichenfolge und anschließend leert den Puffer, erstellen eine **NULL** Zeichenfolge. Sie hat auch eine Überschreibung der `IRowsetImpl::GetDBStatus` in, die es zurück **DBSTATUS_S_ISNULL** Wenn dieser Wert leer ist.  
  
### <a name="marking-nullable-columns"></a>Markieren die Spalten NULL-Werte zulässt  
 Wenn Sie Schemarowsets auch implementieren (finden Sie unter `IDBSchemaRowsetImpl`), die Implementierung sollten angeben, der **DBSCHEMA_COLUMNS** Rowset (markiert in der Regel im Anbieter von **C***Xxx***SchemaColSchemaRowset**), dass die Spalte NULL-Werte zulässt.  
  
 Sie müssen auch angeben, dass alle Spalten enthalten die **DBCOLUMNFLAGS_ISNULLABLE** Wert in Ihrer Version von der `GetColumnInfo`.  
  
 In der Implementierung der OLE DB-Vorlagen, wenn Sie ein Failover zum Kennzeichnen von Spalten als NULL-Werte zulässt, geht davon aus der Anbieter muss einen Wert enthalten und lässt sich nicht auf den Consumer zum Senden von null-Werte.  
  
 Das folgende Beispiel zeigt wie die **CommonGetColInfo** -Funktion ist implementiert **CUpdateCommand** (Siehe UpProvRS.cpp) in UpdatePV. Beachten Sie, wie die Spalten dieser haben **DBCOLUMNFLAGS_ISNULLABLE** für Spalten NULL-Werte zulässt.  
  
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
 Wie bei **NULL** Daten, haben Sie die Verantwortung für den Umgang mit Standardwerten zu ändern.  
  
 Die Standardeinstellung von `FlushData` und **Execute** besteht in der Rückgabe `S_OK`. Aus diesem Grund, wenn Sie diese Funktion nicht überschrieben, die Änderungen scheinbar erfolgreich verlaufen (`S_OK` zurückgegeben werden), aber sie werden nicht in den Datenspeicher übertragen werden.  
  
 In der [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) -Beispiel (in Rowset.h), die `SetDBStatus` Methode Standardwerte wie folgt verarbeitet:  
  
```  
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
  
### <a name="column-flags"></a>Flags für Miningmodellspalten  
 Wenn Sie Standardwerte für Spalten unterstützt, müssen Sie mithilfe von Metadaten im Festlegen der **\<***Anbieterklasse***>SchemaRowset** Klasse. Legen Sie *lautet M_bColumnHasDefault* = `VARIANT_TRUE`.  
  
 Sie haben auch die Flags für Miningmodellspalten festlegen, die angegeben werden, mithilfe der **DBCOLUMNFLAGS** Aufzählungstyp. Die Flags für Miningmodellspalten werden Spalteneigenschaften beschrieben.  
  
 Beispielsweise ist in der `CUpdateSessionColSchemaRowset` -Klasse im [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) (in Session.h), die erste Spalte auf diese Weise einrichten:  
  
```  
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
  
 Dieser Code gibt an, unter anderem, dass die Spalte einen Standardwert von 0 (null) unterstützt, sodass es geschrieben werden kann, und alle Daten in der Spalte die gleiche Länge aufweisen. Wenn Sie die Daten in eine Spalte Variablen Länge haben möchten, legen Sie dieses Flag nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)