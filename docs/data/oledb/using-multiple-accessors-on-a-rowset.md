---
title: "Verwenden mehrerer Accessoren f&#252;r ein Rowset | Microsoft Docs"
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
  - "Accessoren [C++], Rowsets"
  - "BEGIN_ACCESSOR-Makro"
  - "BEGIN_ACCESSOR-Makro, Mehrere Accessoren"
  - "Rowsets [C++], Mehrere Accessoren"
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Verwenden mehrerer Accessoren f&#252;r ein Rowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es gibt drei grundlegende Szenarien, in denen die Arbeit mit mehreren Accessoren erforderlich ist:  
  
-   **Rowsets mit mehrfachem Lese\-\/Schreibzugriff.** In diesem Szenario verfügen Sie über eine Tabelle mit einem Primärschlüssel.  Sie möchten alle Spalten der Zeile lesen können, einschließlich des Primärschlüssels.  Gleichzeitig möchten Sie Daten in alle Spalten außer dem Primärschlüssel schreiben können \(Schreibvorgänge in der Primärschlüsselspalte sind nicht möglich\).  In diesem Fall richten Sie zwei Accessoren ein:  
  
    -   Accessor 0 enthält alle Spalten.  
  
    -   Accessor 1 enthält alle Spalten mit Ausnahme des Primärschlüssels.  
  
-   **Leistung:** In diesem Szenario enthält mindestens eine Spalte große Datenmengen, z. B. Grafiken, Sound\- oder Videodateien.  Nun möchten Sie wahrscheinlich nicht bei jedem Wechsel in eine andere Zeile die Spalte mit der umfangreichen Datendatei abrufen, da sich dies nachteilig auf die Anwendungsleistung auswirken würde.  
  
     Sie können separate Accessoren einrichten, von denen der erste alle Spalten bis auf die mit den großen Datenmengen enthält und Daten aus diesen Spalten automatisch abruft. Dies ist der Autoaccessor.  Der zweite Accessor ruft nur Daten aus der Spalte mit den großen Datenmengen ab, dies erfolgt allerdings nicht automatisch.  Sie können die großen Datenmengen bei Bedarf mit anderen Methoden aktualisieren oder abrufen.  
  
    -   Accessor 0 ist ein automatischer Accessor, der alle Spalten bis auf die mit den großen Datenmengen abruft.  
  
    -   Accessor 1 ist kein automatischer Accessor, der nur die Spalte mit den großen Datenmengen abruft.  
  
     Mit dem Autoargument können Sie festlegen, ob der Accessor ein Autoaccessor ist.  
  
-   **Mehrere ISequentialStream\-Spalten.** In diesen Szenario sind mehrere Spalten vorhanden, die `ISequentialStream`\-Daten enthalten.  Dabei ist jedoch jeder Accessor auf einen `ISequentialStream`\-Datenstream begrenzt.  Um dieses Problem zu lösen, richten Sie mehrere Accessoren ein, von denen jeder einen `ISequentialStream`\-Zeiger enthält.  
  
 Normalerweise erstellen Sie Accessoren mit den Makros [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) und [END\_ACCESSOR](../../data/oledb/end-accessor.md).  Sie können auch das [db\_accessor](../../windows/db-accessor.md)\-Attribut verwenden. \(Accessoren werden unter [Benutzerdatensätze](../../data/oledb/user-records.md) genauer beschrieben.\) Die Makros bzw. das Attribut legen fest, ob ein Accessor ein automatischer oder nicht automatischer Accessor ist:  
  
-   Bei einem automatischen Accessor rufen move\-Methoden wie **MoveFirst**, `MoveLast`, `MoveNext` und `MovePrev` Daten aus allen angegebenen Spalten automatisch ab.  Accessor 0 sollte der automatische Accessor sein.  
  
-   Bei einem nicht automatischen Accessor erfolgt der Abruf erst, wenn Sie explizit eine Methode wie **Update**, **Insert**, **Fetch** oder **Delete** aufrufen.  In den oben beschriebenen Szenarien möchten Sie u. U. nicht bei jedem Wechsel alle Spalten abrufen.  Sie haben die Möglichkeit, eine oder mehrere Spalten einem separaten Accessor hinzuzufügen und diesen als nicht automatischen Accessor zu definieren, wie nachfolgend aufgezeigt.  
  
 Im folgenden Beispiel werden mehrere Accessoren für Lese\- und Schreibvorgänge in der **Jobs**\-Tabelle der SQL Server\-Datenbank **Pubs** verwendet.  In einem solchen Zusammenhang kommen mehrere Accessoren am häufigsten zum Einsatz. Siehe dazu auch das Szenario "Rowsets mit mehrfachem Lese\-\/Schreibzugriff" weiter oben.  
  
 Die Benutzerdatensatz\-Klasse sieht aus wie folgt.  Es werden zwei Accessoren eingerichtet: Accessor 0 umfasst nur die Primärschlüsselspalte \(ID\), während Accessor 1 die übrigen Spalten enthält.  
  
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
  
 Der Hauptcode sieht wie folgt aus.  Durch Aufrufen von `MoveNext` werden automatisch Daten aus der Primärschlüsselspalte ID mit Accessor 0 abgerufen.  Beachten Sie, wie die **Insert**\-Methode gegen Ende Accessor 1 verwendet, um das Schreiben in die Primärschlüsselspalte zu vermeiden.  
  
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
            CTable<CAccessor<CJobs> > jobs;  
  
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
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)   
 [Benutzerdatensätze](../../data/oledb/user-records.md)