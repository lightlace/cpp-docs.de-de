---
title: "Unterst&#252;tzen von Schemarowsets | Microsoft Docs"
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
  - "OLE DB-Consumervorlagen, Schemarowsets"
  - "OLE DB-Anbieter, Schemarowsets"
  - "OLE DB, Schemarowsets"
  - "Schemarowsets"
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Unterst&#252;tzen von Schemarowsets
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mithilfe von Schemarowsets können Consumer Informationen über einen Datenspeicher abrufen, ohne die zugrunde liegende Struktur bzw. das Schema zu kennen.  Beispielsweise kann ein Datenspeicher Tabellen enthalten, die in einer benutzerdefinierten Hierarchie angeordnet sind. Es besteht also keine andere Möglichkeit, den Aufbau des Schemas festzustellen, als das Schema selbst zu lesen. \(Ein weiteres Beispiel stellen die Visual C\+\+\-Assistenten dar, die Schemarowsets einsetzen, um Accessoren für den Consumer zu generieren.\) Um dem Consumer diese Vorgehensweise zu ermöglichen, macht das Sitzungsobjekt des Anbieters Methoden über die [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)\-Schnittstelle verfügbar.  In Visual C\+\+\-Anwendungen wird die [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)\-Klasse zum Implementieren von **IDBSchemaRowset** verwendet.  
  
 `IDBSchemaRowsetImpl` unterstützt die folgenden Methoden:  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) überprüft, ob Beschränkungen für ein Schemarowset gültig sind.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) implementiert eine COM\-Objekterstellerfunktion für das mit dem Vorlagenparameter angegebene Objekt.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) legt fest, welche Beschränkungen bei einem bestimmten Schemarowset unterstützt werden.  
  
-   [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) gibt \(ein von der Schnittstelle geerbtes\) Schemarowset zurück.  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) gibt eine Liste der Schemarowsets zurück, auf die durch `IDBSchemaRowsetImpl::GetRowset` zugegriffen werden kann \(von der Schnittstelle geerbt\).  
  
## Unterstützung des ATL\-OLE DB\-Anbieter\-Assistenten  
 Der ATL\-OLE DB\-Anbieter\-Assistent erstellt drei Schemaklassen in der Sitzungsheaderdatei:  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 Durch diese Klassen werden Consumeranforderungen zu Schemainformationen beantwortet. Beachten Sie, dass diese drei Schemarowsets gemäß OLE DB\-Spezifikation unterstützt werden müssen:  
  
-   **C** *ShortName* **SessionTRSchemaRowset** behandelt Anforderungen von Tabelleninformationen \(`DBSCHEMA_TABLES`\-Schemarowset\).  
  
-   **C** *ShortName* **SessionColSchemaRowset** behandelt Anforderungen von Spalteninformationen \(**DBSCHEMA\_COLUMNS**\-Schemarowset\).  Der Assistent bietet Beispielimplementierungen für diese Klassen, durch die Schemainformationen für einen DOS\-Anbieter zurückgegeben werden.  
  
-   **C** *ShortName* **SessionPTSchemaRowset** behandelt Anforderungen von Schemainformationen zum Anbietertyp \(**DBSCHEMA\_PROVIDER\_TYPES**\-Schemarowset\).  In der vom Assistenten bereitgestellten Standardimplementierung wird `S_OK` zurückgegeben.  
  
 Sie können diese Klassen anpassen, damit für den Anbieter geeignete Schemainformationen verarbeitet werden:  
  
-   In **C***ShortName***SessionTRSchemaRowset** müssen die Katalog\-, Tabellen\- und Beschreibungsfelder ausgefüllt werden \(**trData.m\_szType**, **trData.m\_szTable** und **trData.m\_szDesc**\).  In dem vom Assistenten generierten Beispiel wird nur eine Zeile \(Tabelle\) verwendet.  Andere Anbieter geben unter Umständen mehrere Tabellen zurück.  
  
-   In **C***KurzerName***SessionColSchemaRowset** wird der Name der Tabelle als **DBID** übergeben.  
  
## Festlegen von Beschränkungen  
 Ein wichtiger Aspekt bei der Unterstützung von Schemarowsets ist das Festlegen von Beschränkungen mithilfe von `SetRestrictions`.  Durch Beschränkungen hat der Consumer die Möglichkeit, nur exakt übereinstimmende Zeilen abzurufen \(beispielsweise alle Spalten in der Tabelle "MyTable"\).  Beschränkungen sind optional. Falls keine Beschränkung unterstützt wird \(Standard\), werden automatisch alle Daten zurückgegeben.  Ein Beispiel für einen Anbieter, der keine Beschränkungen unterstützt, finden Sie im [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f)\-Beispiel.  
  
## Einrichten der Schemazuordnung  
 Richten Sie eine mit dem folgenden Beispiel vergleichbare Schemazuordnung in der Datei **Session.h** von "UpdatePV" ein:  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 Damit **IDBSchemaRowset** unterstützt wird, müssen Sie Unterstützung für `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** und **DBSCHEMA\_PROVIDER\_TYPES** vorsehen.  Sie können ggf. weitere Schemarowsets hinzufügen.  
  
 Deklarieren Sie eine Schemarowsetklasse mit einer `Execute`\-Methode, z. B. `CUpdateSessionTRSchemaRowset`, in "UpdatePV":  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 Beachten Sie, dass `CUpdateSession` von `IDBSchemaRowsetImpl` erbt, sodass alle Behandlungsmethoden für Beschränkungen verfügbar sind.  Deklarieren Sie mit `CSchemaRowsetImpl` drei untergeordnete Klassen \(siehe oben aufgeführte Schemazuordnung\): `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset` und `CUpdateSessionPTSchemaRowset`.  Jede dieser untergeordneten Klassen verfügt über eine `Execute`\-Methode, durch die die jeweilige Gruppe von Beschränkungen \(Suchkriterien\) behandelt wird.  Die einzelnen `Execute`\-Methoden vergleichen die Werte der Parameter `cRestrictions` und `rgRestrictions`.  Eine Beschreibung dieser Parameter finden Sie unter [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
 Weitere Informationen dazu, welche Beschränkungen einem bestimmten Schemarowset entsprechen, finden Sie in der Tabelle zu Schemarowset\-GUIDs unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx), die sich in der *OLE DB Programmer's Reference* im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] befindet.  
  
 Wenn z. B. die **TABLE\_NAME**\-Beschränkung für `DBSCHEMA_TABLES` unterstützt werden soll, verfahren Sie wie folgt:  
  
 Informieren Sie sich zunächst über `DBSCHEMA_TABLES`, und stellen Sie fest, dass vier Beschränkungen \(in der folgenden Reihenfolge\) unterstützt werden:  
  
|Schemarowsetbeschränkung|Beschränkungswert|  
|------------------------------|-----------------------|  
|**TABLE\_CATALOG**|0x1 \(binär 1\)|  
|**TABLE\_SCHEMA**|0x2 \(binär 10\)|  
|**TABLE\_NAME**|0x4 \(binär 100\)|  
|**TABLE\_TYPE**|0x8 \(binär 1000\)|  
  
 Beachten Sie, dass für jede Beschränkung ein Bit verwendet wird.  Da lediglich **TABLE\_NAME** unterstützt werden soll, müsste "0x4" im `rgRestrictions`\-Element zurückgegeben werden.  Würden **TABLE\_CATALOG** und **TABLE\_NAME** unterstützt, müsste "0x5" \(binär 101\) zurückgegeben werden.  
  
 Durch die Implementierung wird auf jede Anforderung standardmäßig 0 zurückgegeben \(es werden keine Beschränkungen unterstützt\).  "UpdatePV" ist ein Beispiel für einen Anbieter, der keine Beschränkungen unterstützt.  
  
### Beispiel  
 Dieser Code stammt aus dem [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f)\-Beispiel.  "UpdatePv" unterstützt die drei erforderlichen Schemarowsets: `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** und **DBSCHEMA\_PROVIDER\_TYPES**.  Um ein Beispiel für die Implementierung der Schemaunterstützung im Anbieter zu vermitteln, enthält dieses Thema eine Schritt\-für\-Schritt\-Anweisung zur Implementierung des **DBSCHEMA\_TABLE**\-Rowsets.  
  
> [!NOTE]
>  Der Beispielcode kann von dem hier aufgeführten Code abweichen, sollte jedoch als aktuellere Version angesehen werden.  
  
 Der erste Schritt beim Hinzufügen der Schemaunterstützung besteht darin, festzulegen, welche Beschränkungen unterstützt werden sollen.  Welche Beschränkungen für Ihr Schemarowset zur Verfügung stehen, erfahren Sie in der OLE DB\-Spezifikation für die **IDBSchemaRowset**\-Definition.  Im Anschluss an die Hauptdefinition finden Sie eine Tabelle mit dem Schemarowsetnamen, der Anzahl von Beschränkungen und den Beschränkungsspalten.  Wählen Sie das zu unterstützende Schemarowset aus, und notieren Sie die Anzahl der Beschränkungen und Beschränkungsspalten.  `DBSCHEMA_TABLES` unterstützt z. B. vier Beschränkungen \(**TABLE\_CATALOG**, **TABLE\_SCHEMA**, **TABLE\_NAME** und **TABLE\_TYPE**\):  
  
```  
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
  
 Jede Beschränkungsspalte wird durch ein Bit dargestellt.  Wenn eine Beschränkung unterstützt werden soll \(d. h., sie kann für eine Abfrage verwendet werden\), legen Sie dieses Bit auf 1 fest.  Bei einer Beschränkung, die nicht unterstützt werden soll, legen Sie das Bit auf 0 \(null\) fest.  Aus der oben dargestellten Codezeile ist ersichtlich, dass "UpdatePV" die Beschränkungen **TABLE\_NAME** und **TABLE\_TYPE** für das `DBSCHEMA_TABLES`\-Rowset unterstützt.  Hierbei handelt es sich um die dritte \(Bitmaske 100\) und die vierte \(Bitmaske 1000\) Einschränkung.  Daher lautet die Bitmaske für "UpdatePv" 1100 \(oder 0x0C\):  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 Die folgende `Execute`\-Funktion ist vergleichbar mit den Funktionen in regulären Rowsets.  Sie verfügen über drei Argumente: `pcRowsAffected`, `cRestrictions` und `rgRestrictions`.  Die `pcRowsAffected`\-Variable ist ein Ausgabeparameter, durch den der Anbieter die Anzahl der im Schemarowset enthaltenen Zeilen zurückgeben kann.  Der `cRestrictions`\-Parameter ist ein Ausgabeparameter, der die Anzahl der vom Consumer an den Anbieter übergebenen Beschränkungen enthält.  Der `rgRestrictions`\-Parameter ist ein Array von **VARIANT**\-Werten, die die Beschränkungswerte enthalten.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 Die `cRestrictions`\-Variable basiert auf der Gesamtzahl der Beschränkungen für ein Schemarowset, und zwar unabhängig davon, ob sie vom Anbieter unterstützt werden.  Da UpdatePv zwei Beschränkungen \(die dritte und vierte\) unterstützt, sucht dieser Code lediglich nach einem `cRestrictions`\-Wert, der größer oder gleich 3 ist.  
  
 Der Wert für die **TABLE\_NAME**\-Beschränkung wird in `rgRestrictions[2]` gespeichert \(auch hier entspricht die dritte Beschränkung in einem nullbasierten Array dem Wert 2\).  Damit die Beschränkung unterstützt wird, müssen Sie sicherstellen, dass sie nicht `VT_EMPTY` entspricht.  Beachten Sie, dass **VT\_NULL** nicht gleichwertig mit `VT_EMPTY` ist.  Mit **VT\_NULL** wird ein gültiger Beschränkungswert angegeben.  
  
 Die "UpdatePv"\-Definition eines Tabellennamens entspricht einem voll gekennzeichneten Pfad zu einer Textdatei.  Extrahieren Sie den Beschränkungswert, und versuchen Sie dann, die Datei zu öffnen, um sicherzustellen, dass sie tatsächlich vorhanden ist.  Wenn die Datei nicht vorhanden ist, geben Sie `S_OK` zurück.  Dieser Vorgang erscheint etwas gegenläufig, der Code teilt dem Consumer jedoch mit, dass unter dem angegebenen Namen keine unterstützten Tabellen vorhanden waren.  Wenn `S_OK` zurückgegeben wird, wurde der Code ordnungsgemäß ausgeführt.  
  
```  
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
  
 Die vierte Beschränkung \(**TABLE\_TYPE**\) wird auf ähnliche Weise unterstützt wie die dritte Beschränkung.  Stellen Sie sicher, dass der Wert ungleich `VT_EMPTY` ist.  Durch diese Beschränkung wird lediglich der Tabellentyp **TABLE** zurückgegeben.  Die gültigen Werte für `DBSCHEMA_TABLES` finden Sie in Anhang B der *OLE DB Programmer's Reference* in Abschnitt zum **TABLES**\-Rowset.  
  
```  
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
  
 An dieser Stelle erstellen Sie einen Zeileneintrag für das Rowset.  Die `trData`\-Variable entspricht **CTABLESRow**, einer in den OLE DB\-Anbietervorlagen definierten Struktur.  **CTABLESRow** entspricht der **TABLES**\-Rowsetdefinition in Anhang B der OLE DB\-Spezifikation.  Es muss lediglich eine Zeile hinzugefügt werden, da jeweils nur eine Tabelle unterstützt werden kann.  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  
wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  
wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 Durch UpdatePV werden nur die drei Spalten **TABLE\_NAME**, **TABLE\_TYPE** und **DESCRIPTION** festgelegt.  Sie sollten die Spalten notieren, für die Informationen zurückgegeben werden, da Sie diese bei der Implementierung von `GetDBStatus` benötigen:  
  
```  
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
  
 Die `GetDBStatus`\-Funktion ist für das einwandfreie Funktionieren des Schemarowsets äußerst wichtig.  Da nicht für alle Spalten im **TABLES**\-Rowset Daten zurückgegeben werden, müssen Sie angeben, für welche Spalten Daten zurückgegeben werden und für welche nicht.  
  
```  
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
  
 Da die `Execute`\-Funktion Daten für die Felder **TABLE\_NAME**, **TABLE\_TYPE** und **DESCRIPTION** aus dem **TABLES**\-Rowset zurückgibt, können Sie in Anhang B der OLE DB\-Spezifikation nachschlagen und \(indem Sie von oben nach unten zählen\) feststellen, dass es sich um die Ordnungszahlen 3, 4 und 6 handelt.  Lassen Sie für jede dieser Spalten **DBSTATUS\_S\_OK** zurückgeben.  Für alle anderen Spalten sollte **DBSTATUS\_S\_ISNULL** zurückgegeben werden.  Es ist wichtig, dass dieser Status zurückgegeben wird, da ein Consumer u. U. nicht erkennen kann, ob der zurückgegebene Wert **NULL** oder einen anderen Wert darstellt.  Auch hier ist zu beachten, dass **NULL** nicht äquivalent zu einer leeren Rückgabe ist.  
  
 Weitere Informationen zur OLE DB\-Schemarowset\-Schnittstelle finden Sie unter der [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md)\-Schnittstelle in der OLE DB Programmer's Reference.  
  
 Informationen dazu, wie Consumer **IDBSchemaRowset**\-Methoden verwenden können, finden Sie unter [Abrufen von Metadaten mit Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).  
  
 Ein Beispiel für einen Anbieter, der Schemarowsets unterstützt, finden Sie im [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f)\-Beispiel.  
  
## Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)