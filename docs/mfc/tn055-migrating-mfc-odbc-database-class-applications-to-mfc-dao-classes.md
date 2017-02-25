---
title: "TN055: Migrieren von MFC ODBC-Datenbankklassen-Anwendungen zu MFC DAO-Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], Migration"
  - "Migrieren von Datenbankanwendungen"
  - "Migrieren von ODBC-Datenbankanwendungen"
  - "Migration [C++], ODBC-Datenbankanwendungen"
  - "ODBC [C++], DAO"
  - "ODBC-Klassen [C++], DAO-Klassen"
  - "Portieren von Datenbankanwendungen nach DAO"
  - "Portieren von ODBC-Datenbankanwendungen nach DAO"
  - "TN055"
ms.assetid: 0f858bd1-e168-4e2e-bcd1-8debd82856e4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# TN055: Migrieren von MFC ODBC-Datenbankklassen-Anwendungen zu MFC DAO-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Ab Visual C\+\+ .NET wird DAO von der Visual C\+\+\-Umgebung und den Assistenten nicht mehr unterstützt. \(Die DAO\-Klassen sind allerdings weiterhin enthalten und können verwendet werden.\)  Microsoft empfiehlt, dass Sie [OLE DB\-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte verwenden.  DAO sollte lediglich zur Verwaltung bereits bestehender Anwendungen eingesetzt werden.  
  
 **Übersicht**  
  
 In vielen Fällen ist es möglicherweise wünschenswert, Anwendungen zu migrieren, die MFC DAO\-Datenbankklassen ODBC\-Datenbankklassen zu MFC verwenden.  Dieser technische Hinweis werden die meisten Unterschiede zwischen den MFC ODBC\- und DAO\-Klassen aufgeführt.  Mit den Unterschieden in des Verstandes, sollte sie nicht schwierig übermäßig sein, Anwendungen von den ODBC\-Klassen zu MFC\-Klassen zu migrieren, wenn dies erforderlich ist.  
  
 **Warum migrieren Sie von ODBC zu DAO?**  
  
 Es gibt mehrere Gründe, warum Sie den Anwendungen ODBC\-Datenbankklassen zu den DAO\-Datenbankklassen migrieren können, die Entscheidung ist nicht unbedingt einfach oder offensichtlich.  Eine Ursache ist zu beachten, dass das Microsoft Jet\-Datenbankmodul, das über DAO verwendet wird, jeder ODBC\-Datenquelle lesen kann, für die Sie einen ODBC\-Treiber besitzen.  Es ist effizienter, die ODBC\-Datenbankklassen zu verwenden oder ODBC sich direkt aufzurufen, das Microsoft Jet\-Datenbankmodul kann ODBC\-Daten lesen.  
  
 Einige einfache Fälle, die die ODBC\-\/DAOentscheidung einfach gelten.  Beispielsweise, wenn Sie nur Zugriff auf Daten in einem Format benötigen, das Microsoft Jet\-Modul direkt lesen kann \(Zugriffsformat, Excel\-Format, usw.\). der offensichtlichen Auswahl ist, die DAO\-Datenbankklassen zu verwenden.  
  
 Komplexere Fälle auftreten, wenn die Daten von einem Server oder einer Vielzahl der verschiedenen Server vorhanden sind.  In diesem Fall ist die Entscheidung, die ODBC\-Datenbankklassen oder der DAO\-Datenbankklassen verwenden immer ein wesentliches.  Wenn Sie alles wie heterogene Joins \(Joindaten von den Servern in mehreren Formaten wie SQL Server und Oracle\) ausführen, dann führt das Microsoft Jet\-Datenbankmodul den Join für Sie anstatt aus, sodass Sie, um die erforderliche Arbeit erledigt, wenn Sie die ODBC\-Datenbankklassen verwendet oder ODBC direkt aufgerufen haben.  Wenn Sie einen ODBC\-Treiber verwenden, der Treiber\-Cursor unterstützt, kann die beste Auswahl die ODBC\-Datenbankklassen.  
  
 Die Auswahl kann schwierig, sollten Sie einen Beispielcode schreiben, um die Ausführungsleistung von unterschiedlichen Methoden zu testen, die die speziellen Anforderungen zugewiesen werden.  Dieser technische Hinweis wird davon ausgegangen, dass Sie die Entscheidung getroffen haben, aus den ODBC\-Datenbankklassen zu den DAO\-Datenbankklassen zu migrieren.  
  
 **Ähnlichkeiten zwischen ODBC\-Datenbankklassen und MFC\-DAO\-Datenbankklassen**  
  
 Der ursprüngliche Entwurf der MFC\-ODBC\-Klassen war auf dem DAO\-Objektmodell, das in Microsoft Access und Microsoft Visual Basic verwendet war.  Dies bedeutet, dass viele allgemeine Funktionen der ODBC\- und DAO\-MFC\-Klassen gibt, die nicht alle in diesem Abschnitt aufgeführt werden.  Im Allgemeinen sind die Programmiermodelle identisch.  
  
 So einige Ähnlichkeiten markieren:  
  
-   haben das ODBC und die DAO\-Klassen Datenbankobjekte, die mithilfe des Verwaltungssystems der zugrunde liegenden Datenbank \(DBMS\) verwalten.  
  
-   Beide besitzen die Recordset\-Objekte, die einen Satz Ergebnisse darstellen, die von diesem DBMS zurückgegeben werden.  
  
-   Die DAO\-Datenbank und die Recordset\-Objekte haben die Member, die mit den ODBC\-Klassen fast identisch sind.  
  
-   Bei beiden Sätzen von Klassen, ist der Code, um Daten abzurufen Ausnahme einiger Objekte und Membernamenänderungen identisch.  Änderungen sind erforderlich, aber normalerweise ist der Prozess eine einfache Namensänderung beim Wechsel vom den ODBC\-Klassen an den DAO\-Klassen.  
  
 Beispielsweise in beiden Modellen ist die Prozedur auf, um Daten abzurufen, ein Datenbankobjekt zu erstellen und öffnen, ein Recordset\-Objekt zu erstellen und zu öffnen und \(Verschiebung\) die Daten zwar zu navigieren, die einen Vorgang ausführen.  
  
 **Unterschiede zwischen ODBC\- und DAO\-MFC\-Klassen**  
  
 DAO\-Klassen enthalten weitere Objekte und einen umfangreicheren Satz von Methoden, wobei dieser Abschnitt wird nur die Unterschiede im ähnlichen Klassen und Funktionen aufgeführt.  
  
 Vermutlich sind die diese Unterschiede zwischen Klassen die Namensänderungen ähnlicher Klassen und globale Funktionen.  Die folgende Liste zeigt die der Namensänderungen Objekte, Methoden und der globale Funktionen an, die mit den Datenbankklassen zugeordnet werden:  
  
|Klasse oder Funktion|Entsprechung in den MFC\-DAO\-Klassen|  
|--------------------------|-------------------------------------------|  
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
|**RFX\_Date \***|**DFX\_Date** \(`COleDateTime`\-basiert\)|  
|`RFX_Text`|`DFX_Text`|  
|`RFX_Binary`|`DFX_Binary`|  
|`RFX_LongBinary`|`DFX_LongBinary`|  
  
 \* Die Funktion `RFX_Date` ist auf `CTime` und **TIMESTAMP\_STRUCT**.  
  
 Die wichtigsten Änderungen die Funktionen, die die Anwendung möglicherweise benötigen mehr und beeinflusst, Änderungen des als einfacher Name sind nachfolgend aufgeführt.  
  
-   Die Konstanten und Makros, die verwendet werden, Elemente wie Recordset anzugeben, öffnen Typ und offene Optionen des Recordsets wurden geändert.  
  
     Mit dem ODBC klassifiziert MFC, das erforderlich ist, um diese Optionen über Makros oder Enumerationstypen zu definieren.  
  
     Mit den DAO\-Klassen stellt DAO die Definition dieser Optionen in einer Headerdatei \(DBDAOINT.H\).  Daher ist der Recordsettyp aufgelisteter ein Member von `CRecordset`, aber mit DAO ist es eine Konstante.  Beispielsweise möchten Sie **Momentaufnahme** verwenden, als, den Typ von `CRecordset` in ODBC jedoch in **DB\_OPEN\_SNAPSHOT** angibt, als, den Typ von `CDaoRecordset` bereitstellt.  
  
-   Der Standardrecordsettyp für `CRecordset` ist **Momentaufnahme**, während der Standardrecordsettyp für `CDaoRecordset`**dynaset** ist \(siehe den Hinweis unten für ein zusätzliches Problem zu ODBC\-Klassenmomentaufnahmen\).  
  
-   Die Klasse ODBC `CRecordset` verfügt über eine Option, einen nur für Vorwärts\-Recordsets Recordsettyp zu erstellen.  In der `CDaoRecordset`\-Klasse nur für Vorwärts\-Recordsets ist ein nicht Recordsettyp, sondern eine Eigenschaft \(oder Option\) bestimmter Typen von Recordsets.  
  
-   Ein Nur erweiterbar Recordset, als, ein `CRecordset`\-Objekt zu öffnen bedeutete, dass die Daten des Recordsets gelesen und angefügt werden konnten.  Mit `CDaoRecordset`\-Objekt impliziert die Nur erweiterbar Option buchstäblich, dass die Daten des Recordsets nur angefügt werden können \(und nicht Lesen\).  
  
-   Die der ODBC\-Transaktionsmemberfunktionen Klassen sind Member von `CDatabase` und reagieren auf Datenbankebene.  In den DAO\-Klassen haben die Transaktionsmemberfunktionen sich die Mitglieder einer höheren Klasse \(`CDaoWorkspace`\) und somit `CDaoDatabase` mehrere Objekte demselben Arbeitsbereich \(aus Transaktionsleerzeichen\) freigegeben werden.  
  
-   Die Ausnahmeklasse wurde geändert.  **CDBExceptions** werden in den Klassen ODBC und **CDaoExceptions** in den DAO\-Klassen ausgelöst.  
  
-   `RFX_Date` verwendet `CTime` und **TIMESTAMP\_STRUCT**, während Objekte **DFX\_Date**`COleDateTime` verwendet.  `COleDateTime` ist `CTime` fast identisch, sondern auf einem 8\-Byte OLE  **DATUM** anstelle eines 4\-Byte\- `time_t`, sodass es einer viel größeren Bereich von Daten enthalten.  
  
    > [!NOTE]
    >  Momentaufnahmen DAO \(`CDaoRecordset`\) sind schreibgeschützt, während Momentaufnahmen ODBC \(`CRecordset`\) möglicherweise abhängig vom Treiber und Verwendungsmöglichkeiten der ODBC\-Cursorbibliothek aktualisierbar sind.  Wenn Sie die Cursorbibliothek verwenden, sind `CRecordset` Momentaufnahmen aktualisierbar.  Wenn Sie eines der Microsoft\-Treiber von Tischplattentreiber\-Pack 3.0 ohne die ODBC\-Cursorbibliothek verwenden, sind die `CRecordset` Momentaufnahmen schreibgeschützt.  Wenn Sie einen anderen Treiber verwendet, überprüfen Sie die Dokumentation des Treibers, um festzustellen, ob Momentaufnahmen \(**STATIC\_CURSORS**\) schreibgeschützt sind.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)