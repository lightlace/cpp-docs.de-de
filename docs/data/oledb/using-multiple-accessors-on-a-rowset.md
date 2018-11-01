---
title: Verwenden mehrerer Zugriffsmethoden für ein Rowset
ms.date: 10/24/2018
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
ms.openlocfilehash: 2f88213fce0c5aa1d91f94d7fbeb26eab6432207
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483290"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Verwenden mehrerer Zugriffsmethoden für ein Rowset

Es gibt drei grundlegende Szenarien, in denen Sie mehrere Accessoren für Ereigniseigenschaften verwenden möchten:

- **Mehrere Rowsets von Lese-/Schreibzugriff.** In diesem Szenario müssen Sie eine Tabelle mit einem Primärschlüssel. Sie möchten können alle Spalten in der Zeile, einschließlich des primären Schlüssels lesen. Sie möchten auch in der Lage, zum Schreiben von Daten für alle Spalten außer dem Primärschlüssel (da Sie in der Primärschlüsselspalte schreiben können). In diesem Fall richten Sie zwei Zugriffsmethoden:

   - Accessor 0 enthält alle Spalten.

   - Accessor 1 enthält alle Spalten außer dem Primärschlüssel.

- **Leistung:** In diesem Szenario müssen einer oder mehreren Spalten eine große Menge von Daten, z. B. Grafiken, Audio- oder video-Dateien. Jedes Mal, wenn Sie auf eine Zeile verschieben, möchten Sie wahrscheinlich nicht die Spalte mit der Datei große Datenmengen abrufen, da dadurch die Leistung Ihrer Anwendung also verlangsamen würde.

   Sie können separate Accessoren einrichten, in der die erste Accessor enthält alle Spalten mit Ausnahme des mit großen Datenmengen, und er ruft Daten aus diesen Spalten automatisch; der erste-Accessor ist der Autoaccessor. Der zweite Accessor ruft nur die Spalte, die große Datenmengen enthalten, aber es nicht abrufen von Daten aus dieser Spalte automatisch. Sie können die anderen Methoden aktualisieren oder Abrufen umfangreicher Datenmengen bei Bedarf verwenden.

   - Accessor 0 ist eine automatische Accessor verfügbar. alle Spalten mit Ausnahme des mit umfangreichen Daten abgerufen.

   - Accessor 1 ist eine automatische Accessor nicht. Sie ruft die Spalte mit großen Datenmengen ab.

   Verwenden Sie das automatische-Argument, um anzugeben, ob der Accessor ein Autoaccessor ist.

- **Mehrere Spalten von einer ISequentialStream-Schnittstelle.** In diesem Szenario haben Sie mehr als eine Spalte enthalten `ISequentialStream` Daten. Jeder Accessor kann jedoch nur einmal `ISequentialStream` -Datenstrom. Um dieses Problem zu beheben, legen Sie mehrere Accessoren jeweils eine `ISequentialStream` Zeiger.

Normalerweise erstellen Sie Accessoren mit der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros. Sie können auch die [Db_accessor](../../windows/db-accessor.md) Attribut. (Accessoren werden ausführlich in [Benutzerdatensätze](../../data/oledb/user-records.md).) Die Makros oder das Attribut angeben, ob eine Zugriffsmethode eine automatische oder eine nicht automatische-Accessor ist:

- Bei einem automatischen Accessor, verschieben Sie Methoden wie z. B. `MoveFirst`, `MoveLast`, `MoveNext`, und `MovePrev` Abrufen von Daten für alle Spalten automatisch angegebenen. Accessor 0 sollte die automatische Zugriffsmethode.

- Das Abrufen nicht in einem Accessor nicht automatische auftreten, bis Sie explizit eine Methode z. B. Aufrufen `Update`, `Insert`, `Fetch`, oder `Delete`. In den oben beschriebenen Szenarien können Sie nicht alle Spalten für jede einzelne Verschiebung abrufen möchten. Können Sie eine oder mehrere Spalten in einem separaten Accessor zu platzieren und stellen, dass einen nicht automatische-Accessor, wie unten dargestellt.

Im folgende Beispiel werden mehrere Accessoren zum Lesen und Schreiben in die Tabelle der Aufträge des SQL Server Pubs-Datenbank verwenden mehrerer Zugriffsmethoden verwendet. In diesem Beispiel ist die häufigste Verwendung mehrere Accessoren. finden Sie unter dem oben beschriebenen Szenario für "mehrere Lese-/Schreibzugriff Rowsets".

Die Benutzerdatensatz-Klasse lautet wie folgt aus. Richtet zwei Zugriffsmethoden: 0-Accessor enthält nur die Primärschlüsselspalte (ID) und 1-Accessor enthält andere Spalten.

```cpp
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

Die wichtigsten Code lautet wie folgt aus. Aufrufen von `MoveNext` automatisch Ruft Daten aus der Primärschlüsselspalte-ID, die mit Accessor 0 ab. Beachten Sie die `Insert` Methode in der Nähe der Accessor End verwendet 1, um das Schreiben in die Primärschlüsselspalte zu vermeiden.

```cpp
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

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)<br/>
[Benutzerdatensätze](../../data/oledb/user-records.md)
