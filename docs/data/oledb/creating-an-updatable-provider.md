---
title: "Erstellen eines aktualisierbaren Anbieters"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benachrichtigungen, Unterstützung in Anbietern"
  - "OLE DB-Anbieter, Erstellen"
  - "OLE DB-Anbieter, Aktualisierbar"
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen eines aktualisierbaren Anbieters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In Visual C\+\+ 6.0 wurden lediglich schreibgeschützte Anbieter unterstützt.  Visual C\+\+ .NET unterstützt aktualisierbare Anbieter oder Anbieter, die den Datenspeicher aktualisieren \(d. h. in ihn schreiben\) können.  Unter diesem Thema wird erörtert, wie Sie einen aktualisierbaren Anbieter mithilfe von OLE DB\-Vorlagen erstellen.  
  
 Dabei wird davon ausgegangen, dass ein bearbeitungsfähiger Anbieter verwendet wird.  Ein aktualisierbarer Anbieter wird in zwei Schritten erstellt.  Zuerst müssen Sie festlegen, auf welche Weise der Anbieter Änderungen am Datenspeicher vornimmt. Entscheiden Sie insbesondere, ob Änderungen unverzüglich stattfinden oder verzögert werden, bis ein Aktualisierungsbefehl ausgegeben wird.  Im Abschnitt [Konfigurieren eines Anbieters als aktualisierbarer Anbieter](#vchowmakingprovidersupdatable) werden die Änderungen und Einstellungen beschrieben, die Sie im Anbietercode vornehmen müssen.  
  
 Im nächsten Schritt stellen Sie sicher, dass der Anbieter über alle Funktionen verfügt, die zur Unterstützung des Consumers erforderlich sind.  Falls der Consumer eine Aktualisierung des Datenspeichers anfordert, muss der Container über Code verfügen, durch den die im Datenspeicher enthaltenen Daten erhalten bleiben.  Solche Datenquellenoperationen können z. B. mit der C\-Laufzeitbibliothek oder mithilfe von MFC ausgeführt werden.  Im Abschnitt [Schreiboperationen in der Datenquelle](#vchowwritingtothedatasource) wird erläutert, wie Daten in die Datenquelle geschrieben, wie **NULL** und Standardwerte behandelt und wie Spaltenflags gesetzt werden.  
  
> [!NOTE]
>  UpdatePV ist ein Beispiel für einen aktualisierbaren Anbieter.  Abgesehen davon, dass "UpdatePV" Aktualisierungsunterstützung bietet, entspricht dieses Beispiel "MyProv".  
  
##  <a name="vchowmakingprovidersupdatable"></a> Konfigurieren eines Anbieters als aktualisierbarer Anbieter  
 Wie ein Anbieter als aktualisierbarer Anbieter konfiguriert wird, hängt im Wesentlichen davon ab, welche Operationen vom Anbieter für den Datenspeicher ausgeführt werden sollen und wie sie vom Anbieter auszuführen sind.  In erster Linie sollte bestimmt werden, ob Aktualisierungen des Datenspeichers unverzüglich stattfinden oder bis zur Verwendung eines Aktualisierungsbefehls \(in einer Batchoperation\) verzögert werden.  
  
 Zunächst müssen Sie entscheiden, ob die Rowsetklasse von `IRowsetChangeImpl` oder von `IRowsetUpdateImpl` erben soll.  Je nachdem, welche Implementierung Sie wählen, werden hierdurch die Funktionen von drei Methoden beeinflusst: `SetData`, **InsertRows** und `DeleteRows`.  
  
-   Wenn von [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md) geerbt wird, bewirkt der Aufruf dieser drei Methoden direkte Änderungen am Datenspeicher.  
  
-   Wenn von [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md) geerbt wird, werden Änderungen am Datenspeicher durch die Methoden verzögert, bis **Update**, `GetOriginalData` oder **Undo** aufgerufen wird.  Wenn die Aktualisierung mehrere Änderungen umfasst, werden diese im Batchmodus ausgeführt. \(Bedenken Sie, dass sich der Speicherbedarf deutlich erhöhen kann, wenn Änderungen im Batchmodus vorgenommen werden.\)  
  
 Beachten Sie, dass `IRowsetUpdateImpl` von `IRowsetChangeImpl` abgeleitet wird.  Daher bietet `IRowsetUpdateImpl` sowohl Änderungs\- als auch Batchfunktionen.  
  
#### So unterstützen Sie die Aktualisierbarkeit des Anbieters  
  
1.  Legen Sie fest, dass die Rowsetklasse von `IRowsetChangeImpl` oder von `IRowsetUpdateImpl` erbt.  Diese Klassen verfügen über die geeigneten Schnittstellen zum Ändern des Datenspeichers:  
  
     **Hinzufügen von "IRowsetChange"**  
  
     Verwenden Sie die folgende Zeichenfolge, um der Vererbungskette `IRowsetChangeImpl` hinzuzufügen:  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Fügen Sie zusätzlich `COM_INTERFACE_ENTRY(IRowsetChange)` in den `BEGIN_COM_MAP`\-Abschnitt der Rowsetklasse ein.  
  
     **Hinzufügen von "IRowsetUpdate"**  
  
     Verwenden Sie die folgende Zeichenfolge, um der Vererbungskette `IRowsetUpdate` hinzuzufügen:  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Die `IRowsetChangeImpl`\-Zeile sollte aus der Vererbungskette entfernt werden.  Diese Ausnahme von der zuvor erwähnten Direktive muss Code für `IRowsetChangeImpl` enthalten.  
  
2.  Fügen Sie der COM\-Zuordnung folgende Zeichenfolge hinzu \(**BEGIN\_COM\_MAP ... END\_COM\_MAP**\):  
  
    |Implementierung von|Eintrag in COM\-Zuordnung|  
    |-------------------------|-------------------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  Fügen Sie dem Befehl folgende Zeichenfolge für die Zuordnung des Eigenschaftensets hinzu \(**BEGIN\_PROPSET\_MAP ... END\_PROPSET\_MAP**\):  
  
    |Implementierung von|Eintrag in Eigenschaftensetzuordnung|  
    |-------------------------|------------------------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  Die Eigenschaftensetzuordnung sollte darüber hinaus alle nachfolgend aufgeführten Einstellungen enthalten:  
  
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
  
     Die in diesen Makroaufrufen verwendeten Werte entsprechen den Eigenschaften\-IDs und \-werten in der Datei **Atldb.h** \(falls **Atldb.h** von der Onlinedokumentation abweicht, hat **Atldb.h** Vorrang vor der Dokumentation\).  
  
    > [!NOTE]
    >  Viele der **VARIANT\_FALSE**\-Einstellungen und `VARIANT_TRUE`\-Einstellungen sind für die OLE DB\-Vorlagen erforderlich. Laut OLE DB\-Spezifikation können diese Einstellungen zwar Lese\- und Schreiboperationen unterstützen, die OLE DB\-Vorlagen unterstützen jedoch nur einen Wert.  
  
     **Wenn Sie "IRowsetChangeImpl" implementieren**  
  
     Bei der Implementierung von `IRowsetChangeImpl` müssen die folgenden Eigenschaften für den Anbieter festgelegt werden.  Diese Eigenschaften werden hauptsächlich dazu verwendet, Schnittstellen durch **ICommandProperties::SetProperties** anzufordern.  
  
    -   `DBPROP_IRowsetChange`: Durch die automatische Festlegung wird **DBPROP\_IRowsetChange** festgelegt.  
  
    -   `DBPROP_UPDATABILITY`: Eine Bitmaske, die die unterstützten Methoden für `IRowsetChange` angibt: `SetData`, `DeleteRows` oder `InsertRow`.  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: Der Consumer kann **IRowsetChange::DeleteRows** oder `SetData` für neu eingefügte Zeilen aufrufen.  
  
    -   `DBPROP_IMMOBILEROWS`: Rowset ordnet keine eingefügten oder aktualisierten Zeilen neu an.  
  
     **Wenn Sie "IRowsetUpdateImpl" implementieren**  
  
     Bei der Implementierung von `IRowsetUpdateImpl` müssen Sie zusätzlich zu allen oben für `IRowsetChangeImpl` aufgeführten Eigenschaften die folgenden Eigenschaften für den Anbieter festlegen:  
  
    -   `DBPROP_IRowsetUpdate`.  
  
    -   `DBPROP_OWNINSERT`: Muss READ\_ONLY AND VARIANT\_TRUE sein.  
  
    -   `DBPROP_OWNUPDATEDELETE`: Muss READ\_ONLY AND VARIANT\_TRUE sein.  
  
    -   `DBPROP_OTHERINSERT`: Muss READ\_ONLY AND VARIANT\_TRUE sein.  
  
    -   `DBPROP_OTHERUPDATEDELETE`: Muss READ\_ONLY AND VARIANT\_TRUE sein.  
  
    -   `DBPROP_REMOVEDELETED`: Muss READ\_ONLY AND VARIANT\_TRUE sein.  
  
    -   `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  Wenn Sie außerdem Benachrichtigungen implementieren, müssen Sie unter Umständen noch weitere Eigenschaften festlegen. Eine entsprechende Liste finden Sie im Abschnitt über `IRowsetNotifyCP`.  
  
     Ein Beispiel dazu, wie diese Eigenschaften festgelegt werden, finden Sie in der Eigenschaftensetzuordnung in **CUpdateCommand** \(in der Datei **Rowset.h**\) unter [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
##  <a name="vchowwritingtothedatasource"></a> Schreiboperationen in der Datenquelle  
 Sie rufen die **Execute**\-Funktion auf, um Daten aus der Datenquelle zu lesen.  Um Daten in die Datenquelle zu schreiben, rufen Sie die `FlushData`\-Funktion auf. \(Mit Flush werden im Allgemeinen Operationen bezeichnet, mit denen Änderungen an einer Tabelle oder einem Index auf dem Datenträger gespeichert werden.\)  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 Mithilfe der Argumente für das Zeilenhandle \(*HROW*\) und das Accessorhandle \(*HACCESSOR*\) können Sie den Speicherbereich angeben, in den geschrieben werden soll.  Normalerweise werden die Datenfelder einzeln geschrieben.  
  
 Durch die `FlushData`\-Methode werden Daten in dem Format geschrieben, in dem sie ursprünglich gespeichert wurden.  Wenn Sie diese Funktion beibehalten, funktioniert der Anbieter zwar ordnungsgemäß, die Änderungen werden jedoch nicht entfernt und in den Datenspeicher geschrieben.  
  
### Wann "FlushData" aufgerufen werden sollte  
 `FlushData` wird immer dann von den Anbietervorlagen aufgerufen, wenn Daten in den Datenspeicher geschrieben werden müssen. Dies resultiert normalerweise \(jedoch nicht immer\) aus einem Aufruf der folgenden Funktionen:  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** \(wenn neue Daten in die Zeile eingefügt werden müssen\)  
  
-   **IRowsetUpdate::Update**  
  
### Funktionsweise  
 Der Consumer setzt einen Aufruf ab, der eine Flushoperation erforderlich macht \(z. B. **Update**\). Dieser Aufruf wird an den Anbieter übergeben, der immer wie folgt verfährt:  
  
-   Ruft `SetDBStatus` auf, wenn ein gebundener Statuswert vorliegt \(siehe *OLE DB Programmer's Reference*, Kapitel 6, *Data Parts: Status*, nur auf Englisch verfügbar\).  
  
-   Überprüfen der Spaltenflags.  
  
-   Aufrufen von `IsUpdateAllowed`.  
  
 Diese drei Schritte gewährleisten Sicherheit.  Anschließend ruft der Anbieter `FlushData` auf.  
  
### Implementieren von "FlushData"  
 Bei der Implementierung von `FlushData` müssen mehrere Aspekte berücksichtigt werden:  
  
-   Sicherstellen, dass Änderungen vom Datenspeicher verarbeitet werden können.  
  
-   Behandeln von **NULL**\-Werten.  
  
-   Behandeln von Standardwerten.  
  
 Zur Implementierung einer eigenen `FlushData`\-Methode müssen Sie folgende Aufgaben ausführen:  
  
-   Lassen Sie Ihre Rowsetklasse anzeigen.  
  
-   Fügen Sie die folgende Deklaration in die Rowsetklasse ein:  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   Stellen Sie eine Implementierung von `FlushData` bereit.  
  
 Bei einer funktionsfähigen `FlushData`\-Implementierung werden lediglich die derzeit aktualisierten Zeilen und Spalten gespeichert.  Sie können die Parameter *HROW* und *HACCESSOR* verwenden, um die aktuelle Zeile und Spalte zu ermitteln, die zur Optimierung gespeichert werden.  
  
 Die größte Herausforderung besteht normalerweise in der Verwendung des systemeigenen Datenspeichers.  Die folgenden Voraussetzungen sollten möglichst erfüllt werden:  
  
-   Stellen Sie sicher, dass die Methode zum Schreiben von Daten in den Datenspeicher möglichst einfach ist.  
  
-   Achten Sie darauf, dass **NULL**\-Werte behandelt werden \(optional, jedoch empfohlen\).  
  
-   Achten Sie darauf, dass Standardwerte behandelt werden \(optional, jedoch empfohlen\).  
  
 Am besten legen Sie dazu aktuelle Werte für **NULL**\- und Standardwerte im Datenspeicher fest,  die im Idealfall extrapoliert werden können.  Andernfalls sollten Sie keine **NULL**\- und Standardwerte zulassen.  
  
 Der folgende Code ist ein Beispiel für die Implementierung von `FlushData` in der `RUpdateRowset`\-Klasse des [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f)\-Beispiels \(siehe Rowset.h im Beispielcode\):  
  
```  
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
  
### Behandeln von Änderungen  
 Damit der Anbieter auf Änderungen reagieren kann, müssen Sie zunächst sicherstellen, dass der Datenspeicher \(beispielsweise eine Text\- oder Videodatei usw.\) über die nötigen Funktionen verfügt, um Änderungen daran vorzunehmen.  Sind diese Funktionen nicht vorhanden, sollten Sie diesen Code getrennt vom Anbieterprojekt erstellen.  
  
### Behandeln von **NULL**\-Daten  
 Es besteht die Möglichkeit, dass der Endbenutzer **NULL**\-Daten sendet.  Durch das Schreiben von **NULL**\-Werten in Felder in der Datenquelle können potenzielle Probleme entstehen.  Angenommen, Sie entwickeln ein System für die Auftragsannahme, in das Werte für Vorwahl und Postleitzahl eingegeben werden können. Das System könnte entweder einen der beiden Werte oder beide Werte akzeptieren. Es kann jedoch nicht auf beide Werte verzichtet werden, da die Zustellung in diesem Fall unmöglich wäre.  Aus diesem Grund müssen bestimmte Kombinationen von **NULL**\-Werten in Feldern ausgeschlossen werden, die für die Anwendung nicht sinnvoll sind.  
  
 Als Anbieterentwickler müssen Sie berücksichtigen, auf welche Weise diese Daten gespeichert und aus dem Datenspeicher gelesen und für den Benutzer aufbereitet werden.  Dabei ist insbesondere zu beachten, wie der Status von Rowsetdaten in der Datenquelle geändert wird \(z. B. **DataStatus** \= **NULL**\).  Sie bestimmen, welcher Wert zurückgegeben wird, wenn ein Consumer auf ein Feld mit einem **NULL**\-Wert zugreift.  
  
 Anhand des Codes im [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f)\-Beispiel erfahren Sie, wie **NULL**\-Daten durch einen Anbieter verarbeitet werden können.  In "UpdatePV" speichert der Anbieter **NULL**\-Daten, indem die Zeichenfolge "NULL" in den Datenspeicher geschrieben wird.  Beim Auslesen von **NULL**\-Daten aus dem Datenspeicher erkennt der Anbieter die Zeichenfolge und leert dann den Puffer, wodurch eine **NULL**\-Zeichenfolge erstellt wird.  Zusätzlich überschreibt der Anbieter `IRowsetImpl::GetDBStatus`, indem er bei einem leeren Datenwert **DBSTATUS\_S\_ISNULL** zurückgibt.  
  
### Kennzeichnen von Spalten, die einen NULL\-Wert zulassen  
 Wenn Sie zusätzlich Schemarowsets implementieren \(siehe `IDBSchemaRowsetImpl`\), sollte die Implementierung im **DBSCHEMA\_COLUMNS**\-Rowset \(im Anbieter normalerweise durch **C***xxx***SchemaColSchemaRowset** gekennzeichnet\) vorsehen, dass die Spalte NULL\-Werte zulässt.  
  
 Außerdem müssen Sie in Ihrer `GetColumnInfo`\-Version angeben, dass alle Spalten, die NULL\-Werte zulassen, über den **DBCOLUMNFLAGS\_ISNULLABLE**\-Wert verfügen.  
  
 Wenn Sie in der OLE DB\-Vorlagenimplementierung nicht angeben, dass Spalten NULL\-Werte zulassen, geht der Anbieter davon aus, dass die Spalten einen Wert enthalten müssen. In diesem Fall lässt der Anbieter nicht zu, dass der Consumer NULL\-Werte überträgt.  
  
 Das folgende Codebeispiel veranschaulicht, wie die **CommonGetColInfo**\-Funktion in UpdatePV in **CUpdateCommand** \(siehe UpProvRS.cpp\) implementiert wird.  Beachten Sie die Implementierung von **DBCOLUMNFLAGS\_ISNULLABLE** für Spalten, die NULL\-Werte zulassen.  
  
```  
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
  
### Standardwerte  
 Genauso wie **NULL**\-Werte müssen auch geänderte Standardwerte in bestimmter Weise berücksichtigt werden.  
  
 In der Standardeinstellung wird durch `FlushData` und **Execute** der Wert `S_OK` zurückgegeben.  Daher werden die Änderungen beim Beibehalten dieser Funktion zwar anscheinend erfolgreich ausgeführt \(da `S_OK` zurückgegeben wird\), sie werden jedoch nicht an den Datenspeicher übertragen.  
  
 Im [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f)\-Beispiel \(in **Rowset.h**\) behandelt die `SetDBStatus`\-Methode Standardwerte wie folgt:  
  
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
  
### Spaltenflags  
 Wenn Standardwerte für Spalten unterstützt werden, müssen sie mit Metadaten in der **\<***Anbieterklassen\-***\>SchemaRowset**\-Klasse festlegen.  Die Festlegung lautet *m\_bColumnHasDefault* \= `VARIANT_TRUE`.  
  
 Darüber hinaus müssen Sie die Spaltenflags festlegen, die mit dem **DBCOLUMNFLAGS**\-Enumerationstyp angegeben werden.  Mithilfe von Spaltenflags werden Spalteneigenschaften beschrieben.  
  
 Die erste Spalte in der `CUpdateSessionColSchemaRowset`\-Klasse im [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f)\-Beispiel \(in **Session.h**\) ist z. B. wie folgt konfiguriert:  
  
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
  
 Durch diesen Code wird u. a. festgelegt, dass die Spalte den Standardwert 0 unterstützt, dass Schreiboperationen zulässig sind und dass alle Daten in der Spalte über dieselbe Länge verfügen.  Wenn die Daten in einer Spalte über variable Längen verfügen sollen, würden Sie dieses Flag nicht setzen.  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)