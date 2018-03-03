---
title: 'TN055: Migrieren von MFC-ODBC-Datenbankklassen-Anwendungen zu MFC DAO-Klassen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.odbc
dev_langs:
- C++
helpviewer_keywords:
- DAO [MFC], migration
- TN055
- migration [MFC], ODBC database applications
- ODBC classes [MFC], DAO classes
- migrating ODBC database applications [MFC]
- porting database applications to DAO
- ODBC [MFC], DAO
- porting ODBC database applications to DAO
- migrating database applications [MFC]
ms.assetid: 0f858bd1-e168-4e2e-bcd1-8debd82856e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8da778dbadf312a6fef18ec8fa0b62a1c7aa6030
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>TN055: Migrieren von MFC ODBC-Datenbankklassen-Anwendungen zu MFC DAO-Klassen
> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten unterstützt nicht DAO (obwohl die DAO-Klassen enthalten sind, und Sie weiterhin verwenden können,). Microsoft empfiehlt die Verwendung von [OLE DB-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte. Sie sollten nur DAO verwenden, in die Verwaltung bereits vorhandener Anwendungen.  
  
 **Übersicht**  
  
 In vielen Situationen kann es wünschenswert sein, Anwendungen zu migrieren, die MFC ODBC-Datenbankklassen auf MFC DAO-Datenbankklassen verwendet werden. In diesem technischen Hinweis enthält ausführliche Informationen zum Großteil der Unterschiede zwischen den MFC-ODBC und DAO-Klassen. Mit Ausnahme der Unterschiede beachten Sie sollte es nicht übermäßig kompliziert Anwendungen von den ODBC-Klassen auf die MFC-Klassen zu migrieren, falls gewünscht sein.  
  
 **Warum migrieren von ODBC nach DAO**  
  
 Es gibt eine Reihe von Gründen, warum empfiehlt es sich um den DAO-Datenbankklassen aus den ODBC-Datenbankklassen migrieren, aber die Entscheidung ist nicht notwendigerweise einfach oder offensichtlich. Aufpassen zu bedenken ist, dass das Microsoft Jet-Datenbankmodul, das von DAO verwendet wird, kann eine ODBC-Datenquelle lesen für die Sie einen ODBC-Treiber haben. Es ist möglicherweise effizienter, verwenden den ODBC-Datenbankklassen oder ODBC direkt ODBC-Daten, selbst, aber das Microsoft Jet-Datenbankmodul lesen kann aufrufen.  
  
 Einige einfache Fälle, die die ODBC/DAO Entscheidung zu erleichtern. Für die Instanz, wenn Sie nur Zugriff auf Daten in einem Format benötigen, die das Microsoft Jet-Datenbankmodul lesen kann, direkt (Access-Format, Excel-Format und So weiter) naheliegend entspricht den DAO-Datenbankklassen verwendet werden.  
  
 Komplexere Fällen auftreten, wenn Ihre Daten auf einem Server oder auf einer Vielzahl von verschiedenen Servern vorhanden ist. In diesem Fall ist die Entscheidung für den ODBC-Datenbankklassen oder DAO-Datenbankklassen eine schwierig. Wenn Sie möchten gefällt Dinge heterogene Verknüpfungen (Join-Daten von Servern in verschiedenen Formaten wie SQL Server und Oracle) führen Sie anschließend den Microsoft Jet-Datenbankmodul wird den Join für Sie anstatt erzwingen Sie die notwendigen Aufgaben zu tun, wenn Sie die ODBC-Datenbank verwendet Klassen oder -ODBC direkt aufgerufen. Wenn Sie einen ODBC-Treiber, der Treiber-Cursorn unterstützt verwenden, kann am besten den ODBC-Datenbankklassen sein.  
  
 Die Wahl kann kompliziert sein kann, schreiben einen Beispielcode zum Testen der Leistung der verschiedenen Methoden, die Ihre speziellen Anforderungen zugewiesen werden sollen. In diesem technischen Hinweis wird davon ausgegangen, dass Sie die Entscheidung zur Migration von den ODBC-Datenbankklassen zu den DAO-Datenbankklassen vorgenommen haben.  
  
 **Ähnlichkeiten zwischen ODBC-Datenbankklassen und MFC-DAO-Datenbankklassen**  
  
 Des ursprünglichen Entwurfs der MFC-ODBC-Klassen wurde basierend auf den DAO-Objektmodell, die in Microsoft Access und Microsoft Visual Basic verwendet wurde. Dies bedeutet, dass es gibt viele allgemeine Funktionen von ODBC und DAO-MFC-Klassen, die nicht alle in diesem Abschnitt aufgeführt werden. Im Allgemeinen sind die Programmiermodelle identisch.  
  
 Einige ähnlichkeiten zu markieren:  
  
-   Sowohl die ODBC und DAO-Klassen sind Datenbankobjekte, die mithilfe der zugrunde liegenden Datenbank-Managementsystem (DBMS) verwalten.  
  
-   Beide verfügen über Recordset-Objekte, die einen Satz von aus dieser DBMS zurückgegebenen Ergebnisse darstellt.  
  
-   Die DAO-Datenbank und Recordset-Objekte haben Mitglieder, die nahezu identisch mit der ODBC-Klassen.  
  
-   Mit beiden Sätzen von Klassen ist der Code zum Abrufen von Daten mit Ausnahme einiger Namensänderungen Objekt und das Element identisch. Änderungen werden benötigt, aber der Prozess ist eine einfache Änderung in der Regel beim Wechseln von der ODBC-Klassen zu DAO-Klassen.  
  
 In beiden Modellen wird das Verfahren zum Abrufen von Daten erstellen und öffnen Sie ein Datenbankobjekt, erstellen und öffnen Sie ein Recordset-Objekt und Datennavigation (verschieben) über das Ausführen eines Vorgangs.  
  
 **Unterschiede zwischen ODBC und MFC-DAO-Klassen**  
  
 DAO-Klassen enthalten, weitere Objekte und ein umfassenderer Satz an Methoden, aber in diesem Abschnitt werden nur die Unterschiede in den ähnliche Klassen und Funktionen.  
  
 Die offensichtliche Unterschiede zwischen den Klassen sind wahrscheinlich die Änderungen des Computernamens für ähnliche Klassen und globale Funktionen. Die folgende Liste enthält die Namensänderungen Objekte, Methoden und globale Funktionen, die die Datenbankklassen zugeordnet:  
  
|Klasse oder Funktion|Entsprechung in MFC-DAO-Klassen|  
|-----------------------|-----------------------------------|  
|`CDatabase`|`CDaoDatabase`|  
|`CDatabase::ExecuteSQL`|`CDaoDatabase::Execute`|  
|`CRecordset`|`CDaoRecordset`|  
|`CRecordset::GetDefaultConnect`|`CDaoRecordset::GetDefaultDBName`|  
|`CFieldExchange`|`CDaoFieldExchange`|  
|`RFX_Bool`|`DFX_Bool`|  
|`RFX_Byte`|`DFX_Byte`|  
|`RFX_Int`|`DFX_Short`|  
|`RFX_Long`|`DFX_Long`|  
||`DFX_Currency`|  
|`RFX_Single`|`DFX_Single`|  
|`RFX_Double`|`DFX_Double`|  
|**RFX_Date\***|**DFX_Date** (`COleDateTime`-Basis)|  
|`RFX_Text`|`DFX_Text`|  
|`RFX_Binary`|`DFX_Binary`|  
|`RFX_LongBinary`|`DFX_LongBinary`|  
  
 \*Die `RFX_Date` Funktion basiert auf `CTime` und **TIMESTAMP_STRUCT**.  
  
 Die wichtigsten Änderungen an Funktionen, die möglicherweise Auswirkungen auf Ihre Anwendung und erfordert mehr als einfacher Namensänderungen sind unten aufgeführt.  
  
-   Die Konstanten und Makros verwendet, um anzugeben, z. B. Recordset öffnen Sie Typ und Recordset Optionen wurden geändert.  
  
     Mit dem ODBC-Klassen MFC erforderlich, um diese Optionen über Makros definieren oder Enumerationstypen.  
  
     Mit den DAO-Klassen stellt DAO die Definition dieser Optionen in einer Headerdatei (DBDAOINT. H). Daher ist der Recordsettyp ein enumerierter Element `CRecordset`, jedoch mit DAO Dies ist eine Konstante stattdessen. Verwenden Sie z. B. **Momentaufnahme** beim Angeben des Typs des `CRecordset` in ODBC jedoch **DB_OPEN_SNAPSHOT** beim Angeben des Typs des `CDaoRecordset`.  
  
-   Der Recordset-Standardtyp für `CRecordset` ist **Momentaufnahme** while Recordset Standardtyp für `CDaoRecordset` ist **Dynaset** (siehe Hinweis unten für ein weiteres Problem zu Snapshots der ODBC-Klasse).  
  
-   Die ODBC `CRecordset` -Klasse verfügt über eine Option zum Erstellen eines Forward-only-Recordset-Typs. In der `CDaoRecordset` Vorwärtscursor-Klasse ist kein ein Recordset aber stattdessen-Eigenschaft (oder -Option) bestimmter Typen von Recordsets.  
  
-   Eine Append-only-Recordset, beim Öffnen einer `CRecordset` Objekt vorgesehen, dass das Recordset-Daten gelesen und angefügt werden konnte. Mit `CDaoRecordset` -Objekt, die nur Anhängen-Option bedeutet, dass tatsächlich, dass das Recordset Daten nur können angefügt (und nicht gelesen werden).  
  
-   Die ODBC-Klassen Transaktion Memberfunktionen sind Mitglieder der `CDatabase` und reagieren auf Datenbankebene. In den DAO-Klassen werden die Memberfunktionen Transaktion Member einer Klasse mit höherer Ebene (`CDaoWorkspace`) und daher möglicherweise mehrere beeinträchtigen `CDaoDatabase` Objekte, die Freigabe im selben Arbeitsbereichs (Transaktionsprotokoll-Speicherplatz).  
  
-   Exception-Klasse wurde geändert. **CDBExceptions** in die ODBC-Klassen ausgelöst werden und **CDaoExceptions** in den DAO-Klassen.  
  
-   `RFX_Date`verwendet `CTime` und **TIMESTAMP_STRUCT** Objekte beim **DFX_Date** verwendet `COleDateTime`. Die `COleDateTime` ist nahezu identisch mit `CTime`, aber basierend auf einer 8-Byte-OLE **Datum** anstatt ein 4-Byte- `time_t` , sodass er einen viel größeren Bereich der Daten aufnehmen kann.  
  
    > [!NOTE]
    >  DAO (`CDaoRecordset`) Momentaufnahmen sind schreibgeschützt, während ODBC (`CRecordset`) Momentaufnahmen können abhängig von der Treiber und die Verwendung von ODBC-Cursorbibliothek aktualisiert werden. Bei Verwendung die Cursorbibliothek `CRecordset` Momentaufnahmen aktualisierbar sind. Wenn Sie keines der Microsoft-Treiber von Desktop Driver Pack 3.0 ohne die ODBC-Cursorbibliothek verwenden die `CRecordset` Momentaufnahmen sind schreibgeschützt. Wenn Sie einen anderen Treiber verwenden, Überprüfen der Treiber-Dokumentation, um festzustellen, ob Momentaufnahmen (**STATIC_CURSORS**) sind schreibgeschützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

