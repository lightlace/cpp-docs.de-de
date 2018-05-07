---
title: Verwenden mehrerer Accessoren für ein Rowset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a30108ec344091631094cd55f6a3bd3f0f4a4a54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Verwenden mehrerer Zugriffsmethoden für ein Rowset
Es gibt drei grundlegende Szenarien, in denen Sie mehrere Accessoren für Ereigniseigenschaften verwenden müssen:  
  
-   **Mehrere Rowsets von Lese-/Schreibzugriff.** In diesem Szenario müssen Sie eine Tabelle mit einem Primärschlüssel. Sie möchten können alle Spalten in der Zeile, einschließlich des primären Schlüssels lesen. Sie sollten auch in der Lage, Daten für alle Spalten außer dem Primärschlüssel zu schreiben (da Sie in der Primärschlüsselspalte schreiben können). In diesem Fall richten Sie zwei Zugriffsmethoden:  
  
    -   Accessor 0 enthält alle Spalten.  
  
    -   Accessor 1 enthält alle Spalten außer dem Primärschlüssel.  
  
-   **Leistung:** In diesem Szenario enthält eine oder mehrere Spalten eine große Menge an Daten, z. B. Grafiken, Audio oder video-Dateien. Jedes Mal, wenn Sie auf eine Zeile verschieben, möchten wahrscheinlich nicht Sie die Spalte mit der Datei große Datenmengen abrufen, da dadurch die Leistung Ihrer Anwendung so verlangsamen würde.  
  
     Sie können separate Accessoren einrichten, in dem die erste Accessor enthält alle Spalten außer der Datensatz mit großen Datenmengen und er ruft Daten aus diesen Spalten automatisch; Dies ist die automatische-Zugriffsmethode. Der zweite Accessor ruft nur die Spalte, die umfangreiche Daten enthält, aber es Ruft Daten aus dieser Spalte nicht automatisch ab. Sie können die anderen Methoden aktualisieren oder Abrufen umfangreichen Daten bei Bedarf verwenden.  
  
    -   0-Accessor ist eine automatische Accessor; alle Spalten außer dem mit umfangreichen Daten abgerufen.  
  
    -   Accessor 1 kann es sich nicht um einen automatischen Accessor; die Spalte mit großen Datenmengen abgerufen.  
  
     Verwenden Sie das Autoargument, um anzugeben, ob der Accessor eine automatische-Zugriffsmethode ist.  
  
-   **Mehrere ISequentialStream-Spalten.** In diesem Szenario haben Sie mehr als eine Spalte mit `ISequentialStream` Daten. Jeder Accessor ist jedoch beschränkt auf einen `ISequentialStream` -Datenstrom. Um dieses Problem zu lösen, Einrichten mehrere Accessoren mit je einer `ISequentialStream` Zeiger.  
  
 Normalerweise erstellen Sie Accessoren mit der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros. Sie können auch die [Db_accessor](../../windows/db-accessor.md) Attribut. (Zugriffsmethoden sind in der beschriebenen [Benutzerdatensätze](../../data/oledb/user-records.md).) Die Makros oder das Attribut angeben, ob ein Accessor eine automatische oder einen Accessor nicht automatische:  
  
-   Verschieben Sie bei einem automatischen Accessor Methoden wie z. B. **MoveFirst**, `MoveLast`, `MoveNext`, und `MovePrev` Abrufen von Daten für alle Spalten automatisch angegeben. Accessor 0 sollte der automatische Accessor sein.  
  
-   In einem Accessor nicht automatische der Abruf erfolgt erst, wenn Sie explizit einer Methode wie z. B. Aufrufen **Update**, **einfügen**, **Fetch**, oder **Löschen**. In den oben beschriebenen Szenarien können Sie nicht alle Spalten, die bei jedem Wechsel abrufen möchten. Sie können eine oder mehrere Spalten in einem separaten Accessor platzieren und stellen, dass einen Accessor nicht automatische, wie unten dargestellt.  
  
 Im folgende Beispiel werden mehrere Accessoren für Lese- und Schreibberechtigungen für die Tabelle mit Aufträgen des SQL Server Pubs-Datenbank verwenden mehrerer Accessoren verwendet. Dies ist die häufigste Verwendung von mehreren Accessoren; finden Sie unter "mehrere Lese-/Schreibzugriff Rowsets" Szenario oben.  
  
 Die Benutzerdatensatz-Klasse lautet wie folgt. Er richtet zwei Zugriffsmethoden: Accessor 0 enthält nur die Primärschlüsselspalte (ID) und Accessor 1 enthält andere Spalten.  
  
```  
class CJobs  
{  
public:  
    enum {  
        sizeOfDescription = 51  
    };  
  
    short nID;  
    char szDescription[ sizeOfDescription ];  
    short nMinLvl;  
    short nMaxLvl;  
  
    DWORD dwID;  
    DWORD dwDescription;  
    DWORD dwMinLvl;  
    DWORD dwMaxLvl;  
  
BEGIN_ACCESSOR_MAP(CJobs, 2)  
    // Accessor 0 is the automatic accessor  
    BEGIN_ACCESSOR(0, true)  
        COLUMN_ENTRY_STATUS(1, nID, dwID)  
    END_ACCESSOR()  
    // Accessor 1 is the non-automatic accessor  
    BEGIN_ACCESSOR(1, true)  
        COLUMN_ENTRY_STATUS(2, szDescription, dwDescription)  
        COLUMN_ENTRY_STATUS(3, nMinLvl, dwMinLvl)  
        COLUMN_ENTRY_STATUS(4, nMaxLvl, dwMaxLvl)  
    END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 Die Hauptcodedatei lautet wie folgt. Aufrufen von `MoveNext` automatisch Ruft Daten aus der Primärschlüsselspalte ID mit Accessor 0 ab. Hinweis wie die **einfügen** Methode in der Nähe der Accessor End verwendet 1, um das Schreiben in die Primärschlüsselspalte zu vermeiden.  
  
```  
int main(int argc, char* argv[])  
{  
    // Initalize COM  
    ::CoInitialize(NULL);  
  
    // Create instances of the data source and session  
    CDataSource source;  
    CSession session;  
    HRESULT hr = S_OK;  
  
    // Set initialization properties  
    CDBPropSet dbinit(DBPROPSET_DBINIT);  
    dbinit.AddProperty(DBPROP_AUTH_USERID, OLESTR("my_user_id"));  
    dbinit.AddProperty(DBPROP_INIT_CATALOG, OLESTR("pubs"));  
    dbinit.AddProperty(DBPROP_INIT_DATASOURCE, OLESTR("(local)"));  
  
    hr = source.Open("SQLOLEDB.1", &dbinit);  
    if (hr == S_OK)  
    {  
        hr = session.Open(source);  
        if (hr == S_OK)  
        {  
            // Ready to fetch/access data  
            CTable<CAccessor<CJobs>> jobs;  
  
            // Set properties for making the rowset a read/write cursor  
            CDBPropSet dbRowset(DBPROPSET_ROWSET);  
            dbRowset.AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
            dbRowset.AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
            dbRowset.AddProperty(DBPROP_IRowsetChange, true);  
            dbRowset.AddProperty(DBPROP_UPDATABILITY,  
                DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE |  
                DBPROPVAL_UP_DELETE);  
  
            hr = jobs.Open(session, "jobs", &dbRowset);  
            if (hr == S_OK)  
            {  
                // Calling MoveNext automatically retrieves ID  
                // (using accessor 0)  
                while(jobs.MoveNext() == S_OK)  
                   printf_s("Description = %s\n", jobs.szDescription);  
  
                hr = jobs.MoveFirst();  
                if (hr == S_OK)  
                {  
                    jobs.nID = 25;  
                    strcpy_s(&jobs.szDescription[0],  
                             jobs.sizeOfDescription,  
                             "Developer");  
                    jobs.nMinLvl = 10;  
                    jobs.nMaxLvl = 20;  
  
                    jobs.dwDescription = DBSTATUS_S_OK;  
                    jobs.dwID = DBSTATUS_S_OK;  
                    jobs.dwMaxLvl = DBSTATUS_S_OK;  
                    jobs.dwMinLvl = DBSTATUS_S_OK;  
  
                    // Insert method uses accessor 1  
                    // (to avoid writing to the primary key column)  
                    hr = jobs.Insert(1);     
                }  
                jobs.Close();  
            }  
            session.Close();  
        }  
        source.Close();  
    }  
  
    // Uninitialize COM  
    ::CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)   
 [Benutzerdatensätze](../../data/oledb/user-records.md)