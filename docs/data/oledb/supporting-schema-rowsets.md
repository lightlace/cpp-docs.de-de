---
title: "Unterstützen von Schemarowsets | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b4dc655710c9c9cc4bb9a2549136f772b192f739
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="supporting-schema-rowsets"></a>Supporting Schema Rowsets
Schemarowsets ermöglichen es Consumern, Informationen zu einem Datenspeicher abrufen, ohne die zugrunde liegende Struktur bzw. das Schema. Beispielsweise ggf. ein Datenspeicher Tabellen in einer benutzerdefinierten Hierarchie organisiert, damit gäbe es keine Möglichkeit, die Kenntnis des Schemas mit Ausnahme von sichergestellt werden, lesen. (Ein weiteres Beispiel beachten Sie, dass die Visual C++-Assistenten-Schemarowsets verwenden, um die Zugriffsmethoden für den Consumer zu generieren.) Damit wird den Consumer dazu, macht der Anbieter-Sitzungsobjekt Methoden auf die [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) Schnittstelle. In Visual C++-Anwendungen verwenden Sie die [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) Klasse implementieren **IDBSchemaRowset**.  
  
 `IDBSchemaRowsetImpl` unterstützt die folgenden Methoden:  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) überprüft die Gültigkeit von Einschränkungen für ein Schemarowset.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) implementiert eine COM-Objekterstellerfunktion für das mit dem Vorlagenparameter angegebene Objekt.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) gibt an, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen.  
  
-   [IDBSchemaRowset:: GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) gibt ein Schemarowset (von der Schnittstelle geerbt).  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) gibt eine Liste der Schemarowsets zugänglich `IDBSchemaRowsetImpl::GetRowset` (von der Schnittstelle geerbt).  
  
## <a name="atl-ole-db-provider-wizard-support"></a>Unterstützung des ATL-OLE DB-Anbieter-Assistenten  
 Der ATL-OLE DB-Anbieter-Assistent erstellt drei Schemaklassen in der Sitzungsheaderdatei:  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 Diese Klassen reagieren Consumeranforderungen zu Schemainformationen; Beachten Sie, dass der OLE DB-Spezifikation erfordert, dass diese drei Schemarowsets unterstützt werden:  
  
-   **C** *ShortName* **SessionTRSchemaRowset** verarbeitet Anforderungen für den Tabelleninformationen (die `DBSCHEMA_TABLES` -Schemarowsets).  
  
-   **C** *ShortName* **SessionColSchemaRowset** handles requests for column information (the **DBSCHEMA_COLUMNS** schema rowset). Der Assistent stellt die Beispiel-Implementierungen für diese Klassen, die Schemainformationen für einen DOS-Anbieter zurück.  
  
-   **C** *ShortName* **SessionPTSchemaRowset** handles requests for schema information about the provider type (the **DBSCHEMA_PROVIDER_TYPES** schema rowset). Gibt die standardmäßige Implementierung, die vom Assistenten bereitgestellte `S_OK`.  
  
 Sie können diese Klassen zum Behandeln von Schemainformationen für den Anbieter geeignete anpassen:  
  
-   In **C***ShortName***SessionTRSchemaRowset**, müssen Sie die Felder Katalog, Tabellen- und Beschreibung ausfüllen (**M_sztype**, **trData. M_sztable** , und **M_szdesc**). Die vom Assistenten generierten-Beispiel verwendet nur eine Zeile (Tabelle). Andere Anbieter möglicherweise mehr als eine Tabelle zurück.  
  
-   In **C***ShortName***SessionColSchemaRowset**, übergeben Sie den Namen der Tabelle als eine **DBID**.  
  
## <a name="setting-restrictions"></a>Festlegen von Einschränkungen  
 Ein wichtiges Konzept in Schemarowset-Unterstützung ist dies mithilfe von geschieht Einschränkungen festlegen `SetRestrictions`. Einschränkungen ermöglichen es Consumern, nur die übereinstimmende Zeilen abzurufen (z. B. Suche nach allen Spalten in der Tabelle „MyTable“). Einschränkungen sind optional, und wenn keine unterstützt werden (Standardeinstellung), werden immer alle Daten zurückgegeben. Ein Beispiel für einen Anbieter, die Einschränkungen unterstützt, finden Sie unter der [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) Beispiel.  
  
## <a name="setting-up-the-schema-map"></a>Einrichten der Schemazuordnung  
 Richten Sie eine schemazuordnung in Session.h in UpdatePV wie diese:  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 Zur Unterstützung **IDBSchemaRowset**, Sie müssen den support `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**, und **DBSCHEMA_PROVIDER_TYPES**. Sie können zusätzliche Schemarowsets in Ihrem eigenen Ermessen hinzufügen.  
  
 Deklarieren Sie eine Schemarowsetklasse mit einer `Execute` Methode z. B. `CUpdateSessionTRSchemaRowset` in UpdatePV:  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 Beachten Sie, dass `CUpdateSession` erbt von `IDBSchemaRowsetImpl`, sodass er die Einschränkung, die für die Behandlung von Methoden verfügt. Mit `CSchemaRowsetImpl`, deklarieren Sie die drei untergeordneten Klassen (in der schemazuordnung, die oben aufgelistet): `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset`, und `CUpdateSessionPTSchemaRowset`. Jedes dieser untergeordneten Klassen verfügt über eine `Execute` Methode, die einen entsprechenden Satz von Einschränkungen (Suchkriterien) behandelt. Jede `Execute` Methode vergleicht die Werte der `cRestrictions` und `rgRestrictions` Parameter. Finden Sie in der Beschreibung dieser Parameter in [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
 Weitere Informationen darüber, welche Einschränkungen einem bestimmten Schemarowset entsprechen, finden Sie in der Tabelle der Schemarowset-GUIDs in [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB Programmer's Reference* in der Windows SDK.  
  
 Angenommen, Sie unterstützt die **TABLE_NAME** Beschränkung `DBSCHEMA_TABLES`, würden Sie Folgendes tun:  
  
 Erstens Nachschlagen `DBSCHEMA_TABLES` und sehen, dass es vier Einschränkungen (in entsprechender Reihenfolge) unterstützt.  
  
|Schema-Rowset-Einschränkung|Einschränkungswert|  
|-------------------------------|-----------------------|  
|**TABLE_CATALOG**|0 x 1 (binär 1)|  
|**TABLE_SCHEMA**|0 x 2 (binär 10)|  
|**TABLE_NAME**|0 x 4 (binär 100)|  
|**TABLE_TYPE**|0 x 8 (binär 1000)|  
  
 Als Nächstes, beachten Sie, dass ein Bit für jede Einschränkung. Da Sie unterstützen möchten **TABLE_NAME** nur, würden Sie zurückkehren, 0 x 4 in der `rgRestrictions` Element. Wenn Sie unterstützten **"TABLE_CATALOG"** und **TABLE_NAME**, würden Sie 0 x 5 (binär 101) zurückgeben.  
  
 Die Implementierung gibt standardmäßig 0 (unterstützt keine Einschränkungen) für jede Anforderung zurück. UpdatePV ist ein Beispiel für einen Anbieter, der Einschränkungen unterstützt.  
  
### <a name="example"></a>Beispiel  
 Mit diesem Code stammt aus dem [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) Beispiel. UpdatePv unterstützt die drei erforderlichen Schemarowsets: `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**, und **DBSCHEMA_PROVIDER_TYPES**. Als Beispiel das schemaunterstützung in Ihrem Anbieter implementieren, dieses Thema führt Sie durch Implementieren der **DBSCHEMA_TABLE** Rowset.  
  
> [!NOTE]
>  Der Beispielcode weicht möglicherweise von den hier genannten der; den Code sollte als aktuellere Version angesehen werden.  
  
 Der erste Schritt beim Hinzufügen der Unterstützung von Schemas ist, um zu bestimmen, welche Einschränkungen Sie unterstützen möchten. Um zu bestimmen, welche Einschränkungen für die Schemarowsets verfügbar sind, sehen Sie sich die OLE DB-Spezifikation für die Definition des **IDBSchemaRowset**. Folgende die hauptdefinition sehen Sie eine Tabelle mit den Schemanamen für das Rowset, die Anzahl der Einschränkungen und die Einschränkungsspalten. Wählen Sie das Schemarowset, die, das Sie unterstützen, und notieren Sie sich die Anzahl der Einschränkungen und Einschränkungsspalten möchten. Beispielsweise `DBSCHEMA_TABLES` unterstützt vier Einschränkungen (**"TABLE_CATALOG"**, **TABLE_SCHEMA**, **TABLE_NAME**, und **TABLE_TYPE** ):  
  
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
  
 Eine Bit stellt jede Einschränkungsspalte dar. Wenn Sie eine Einschränkung unterstützen möchten (d. h., Sie können für eine Abfrage verwendet werden), das Bit auf 1 festgelegt. Wenn Sie nicht, um eine Einschränkung zu unterstützen möchten, wird das Bit auf 0 festgelegt. Aus der Zeile des oben angegeben Codes UpdatePV unterstützt die **TABLE_NAME** und **TABLE_TYPE** Einschränkungen für die `DBSCHEMA_TABLES` Rowset. Dies sind die dritte (Bitmaske 100) und die vierte (Bitmaske 1000)-Einschränkungen. Daher ist die Bitmaske für UpdatePv 1100 (oder 0x0C):  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 Die folgenden `Execute` Funktion ist vergleichbar mit denen in regulären Rowsets. Sie verfügen über drei Argumente: `pcRowsAffected`, `cRestrictions`, und `rgRestrictions`. Die `pcRowsAffected` Variable ist ein Ausgabeparameter, dass der Anbieter die Anzahl der Zeilen im Schemarowset zurückgeben kann. Die `cRestrictions` Parameter ist ein Eingabeparameter, enthält die Anzahl der Einschränkungen, die vom Consumer an dem Anbieter übergeben. Die `rgRestrictions` Parameter ist ein Array von **VARIANT** Werte, die der Einschränkungswerte enthalten.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 Die `cRestrictions` Variable basiert darauf, dass die Gesamtanzahl der Einschränkungen für ein Schemarowset, unabhängig davon, ob Sie vom Anbieter unterstützt. Da UpdatePv zwei Einschränkungen (der dritte und vierte) unterstützt, wird dieser Code nur nach einem `cRestrictions` Wert größer als oder gleich 3.  
  
 Der Wert für die **TABLE_NAME** Einschränkung befindet sich in `rgRestrictions[2]` (erneut aus, für die dritte Beschränkung in einem nullbasierten Array ist 2). Müssen Sie überprüfen, dass die Einschränkung nicht `VT_EMPTY` unterstützt. Beachten Sie, dass **VT_NULL** stimmt nicht mit `VT_EMPTY`. **VT_NULL** gibt den Wert ein gültige Einschränkung an.  
  
 Die Definition UpdatePv einen Tabellennamen wird einen voll gekennzeichneten Pfadnamen in eine Textdatei. Extrahieren Sie den Einschränkungswert ein, und dann versuchen Sie, öffnen Sie die Datei, um sicherzustellen, dass die Datei tatsächlich vorhanden ist. Wenn die Datei nicht vorhanden ist, zurück `S_OK`. Dies mag etwas Abwärtskompatibilität jedoch Zweck des Codes tatsächlich teilt dem Consumer besteht darin, dass keine unterstützten Tabellen anhand des Namens angegeben wurden. Die `S_OK` Return bedeutet, dass den Code ordnungsgemäß ausgeführt.  
  
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
  
 Die vierte Beschränkung (**TABLE_TYPE**) ähnelt die dritte Beschränkung. Stellen Sie sicher, dass der Wert nicht `VT_EMPTY`. Diese Einschränkung gibt nur den Tabellentyp **Tabelle**. Zur Bestimmung der gültigen Werte für die `DBSCHEMA_TABLES`, suchen Sie in Anhang B die *OLE DB Programmer's Reference* in der **Tabellen** Rowset-Abschnitt.  
  
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
  
 Dies ist in dem Sie einen Zeileneintrag für das Rowset erstellen. Die Variable `trData` entspricht **CTABLESRow**, eine Struktur, die in der OLE DB-Anbietervorlagen definiert. **CTABLESRow** entspricht der **Tabellen** Rowsetdefinition in Anhang B der OLE DB-Spezifikation. Sie müssen nur eine Zeile hinzugefügt werden, da Sie nur eine Tabelle zu einem Zeitpunkt unterstützen können.  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV nur drei Spalten: **TABLE_NAME**, **TABLE_TYPE**, und **Beschreibung**. Sie sollten notieren die Spalten für die Informationen zurückgegeben werden, da Sie diese Informationen sind erforderlich, bei der Implementierung `GetDBStatus`:  
  
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
  
 Die `GetDBStatus` Funktion ist sehr wichtig, den korrekten Betrieb des-Schemarowsets. Da Sie keine Daten für jede Spalte in Zurückgeben der **Tabellen** Rowset, müssen Sie angeben, welche Spalten, auf die Daten zurückgegeben werden und welche nicht.  
  
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
  
 Da Ihre `Execute` Funktion gibt Daten für die **TABLE_NAME**, **TABLE_TYPE**, und **Beschreibung** Felder aus der **Tabellen**Rowset, suchen Sie im Anhang B der OLE DB-Spezifikation und bestimmt werden kann (durch die Zählung von oben nach unten) Ordinalzahlen, 3, 4 und 6 sind. Für jede dieser Spalten zurückgeben **DBSTATUS_S_OK**. Für alle anderen Spalten zurückgeben **DBSTATUS_S_ISNULL**. Es ist wichtig, dass dieser Status zurückgegeben, da ein Consumer nicht interpretieren kann, dass der zurückgegebene Wert ist **NULL** oder etwas anderes. Beachten Sie, dass erneut **NULL** entspricht nicht leer.  
  
 Weitere Informationen zu den OLE DB-Schemarowset-Schnittstelle, finden Sie unter der [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) -Schnittstelle in der OLE DB Programmer's Reference.  
  
 Informationen zur Verwendung von Consumern **IDBSchemaRowset** Methoden, finden Sie unter [Abrufen von Metadaten mit Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).  
  
 Ein Beispiel für einen Anbieter, der Schemarowsets unterstützt, finden Sie unter der [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)