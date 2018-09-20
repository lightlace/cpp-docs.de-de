---
title: 'TN055: Migrieren von MFC-ODBC-Datenbankklassen-Anwendungen zu MFC DAO-Klassen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/20/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 808f0f470e99b95502891552ade7b8c677dfdf17
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396830"
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>TN055: Migrieren von MFC ODBC-Datenbankklassen-Anwendungen zu MFC DAO-Klassen

> [!NOTE]
> Die Visual C++-Umgebung und den Assistenten unterstützen DAO keine (obwohl die DAO-Klassen enthalten sind, und Sie können diese weiterhin verwenden). Microsoft empfiehlt die Verwendung von [OLE DB-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte. Sie sollten nur DAO Verwaltung bereits vorhandener Anwendungen verwenden.

## <a name="overview"></a>Übersicht

In vielen Situationen kann es wünschenswert sein, Anwendungen zu migrieren, die MFC ODBC-Datenbankklassen auf MFC DAO-Datenbankklassen verwendet werden. Diese technische Hinweis wird die meisten Unterschiede zwischen den MFC-ODBC und DAO-Klassen ausführlich beschrieben. Mit den unterschieden, denken Sie daran sollte sie nicht übermäßig schwierig, Anwendungen über die ODBC-Klassen, die MFC-Klassen zu migrieren, bei Bedarf.

## <a name="why-migrate-from-odbc-to-dao"></a>Warum migrieren von ODBC, DAO

Es gibt zahlreiche Gründe, warum Sie Anwendungen aus der ODBC-Datenbankklassen zu den DAO-Datenbankklassen migrieren möchten, aber es geht also nicht unbedingt einfach oder offensichtlich. Dabei ist zu bedenken ist, können die Microsoft Jet-Datenbank-Engine, mit dem DAO eine ODBC-Datenquelle lesen für die ein ODBC-Treiber installiert. Es ist möglicherweise effizienter, verwenden Sie den ODBC-Datenbankklassen oder Aufrufen von ODBC direkt selbst, aber die Datenbank-Engine von Microsoft Jet ODBC-Daten lesen kann.

Einige einfache Fälle, die die ODBC/DAO-Entscheidung zu erleichtern. Z. B. wenn benötigen Sie nur den Zugriff auf Daten in einem Format, das vom Microsoft Jet-Modul lesen kann, direkt (Access-Format, Excel-Format, usw.) die offensichtliche Wahl zum DAO-Datenbankklassen verwendet werden ist.

Komplexere Fällen auftreten, wenn Ihre Daten auf einem Server oder auf einer Vielzahl von verschiedenen Servern vorhanden ist. In diesem Fall ist die Entscheidung für die ODBC-Datenbankklassen oder DAO-Datenbankklassen schwer. Wenn Sie möchten beispielsweise heterogene Joins (Join-Daten von Servern in verschiedenen Formaten wie SQL Server und Oracle), und die Microsoft Jet-Datenbank-Engine führt den Join für Sie, anstatt Sie mussten die erforderlichen Schritte zu tun, wenn Sie die ODBC-Datenbank verwendet Klassen oder ODBC direkt-Namens. Wenn Sie einen ODBC-Treiber, der Treiber-Cursorn unterstützt verwenden, kann die beste Wahl, die ODBC-Datenbankklassen sein.

Die Auswahl kann kompliziert sein kann, kann einen Beispielcode zum Testen der Leistung der verschiedenen Methoden, die Ihre speziellen Anforderungen angegeben geschrieben werden soll. Diese technische Hinweis wird davon ausgegangen, dass Sie die Entscheidung zur Migration von der ODBC-Datenbankklassen zu den DAO-Datenbankklassen vorgenommen haben.

## <a name="similarities-between-odbc-database-classes-and-mfc-dao-database-classes"></a>Ähnlichkeiten zwischen den ODBC-Datenbankklassen und MFC-DAO-Datenbankklassen

Der ursprüngliche Entwurf von den MFC-ODBC-Klassen basiert auf den DAO-Objektmodell, die in Microsoft Access und Microsoft Visual Basic verwendet wurde. Dies bedeutet, dass es viele allgemeine Funktionen der ODBC und DAO-MFC-Klassen, die nicht alle in diesem Abschnitt aufgeführt sind. Im Allgemeinen entsprechen die Programmiermodelle.

Einige ähnlichkeiten zu markieren:

- Sowohl die ODBC und DAO-Klassen müssen Datenbankobjekte, die mithilfe der zugrunde liegenden Datenbank-Managementsystem (DBMS) verwalten.

- Beide verfügen über Recordset-Objekte, die einen Satz von von diesem DBMS zurückgegebenen Ergebnisse darstellt.

- Die DAO-Datenbank und Recordset-Objekte haben Mitglieder, die nahezu identisch mit der ODBC-Klassen.

- Mit beiden Sätzen von Klassen entspricht der Code zum Abrufen von Daten mit Ausnahme einiger Änderungen Objekt und Member. Änderungen werden erforderlich sein, aber der Prozess ist eine einfache Änderung in der Regel beim Wechseln von der ODBC-Klassen zu DAO-Klassen.

Beispielsweise ist das Verfahren zum Abrufen von Daten in beiden Modellen zum Erstellen und Öffnen eines Datenbankobjekts, erstellen und öffnen Sie ein Recordset-Objekt, und navigieren (verschieben) jedoch die Daten, die einen Vorgang ausführen.

## <a name="differences-between-odbc-and-dao-mfc-classes"></a>Unterschieden zwischen ODBC und DAO-MFC-Klassen

Die DAO-Klassen enthalten, weitere Objekte und einen umfangreicheren Satz von Methoden, aber in diesem Abschnitt wird nur die Unterschiede in den ähnliche Klassen und Funktionen beschrieben.

Die offensichtliche Unterschiede zwischen den Klassen sind wahrscheinlich die Änderungen des Computernamens für ähnliche Klassen und globale Funktionen. Die folgende Liste zeigt die Änderungen der Objekte, Methoden und globale Funktionen, die den Datenbankklassen zugeordnet:

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
|`RFX_Date`<sup>1</sup>|`DFX_Date` (`COleDateTime`-basiert)|
|`RFX_Text`|`DFX_Text`|
|`RFX_Binary`|`DFX_Binary`|
|`RFX_LongBinary`|`DFX_LongBinary`|

<sup>1</sup> der `RFX_Date` Funktion basiert auf `CTime` und `TIMESTAMP_STRUCT`.

Die wichtigsten Änderungen an Funktionen, die möglicherweise Auswirkungen auf Ihre Anwendung und mehr als nur einfache Änderungen erfordern, sind unten aufgeführt.

- Die Konstanten und Makros verwendet, um anzugeben, z.B. Recordset öffnen, Typ und Optionen beim Öffnen des Recordsets wurden geändert.

   Die ODBC-Klassen MFC erforderlich, um diese Optionen über Makros definieren oder Enumerationstypen.

   Mit den DAO-Klassen bietet DAO die Definition der folgenden Optionen in einer Headerdatei (DBDAOINT. H). Daher ist der Typ der Datensatzgruppe aufgelisteten Mitglied `CRecordset`, aber mit DAO Dies ist eine Konstante stattdessen. Verwenden Sie z. B. **Momentaufnahme** beim Angeben des Typs des `CRecordset` in ODBC aber **DB_OPEN_SNAPSHOT** beim Angeben des Typs des `CDaoRecordset`.

- Das Recordset-Standardtyp für `CRecordset` ist **Momentaufnahme** zwar den Recordset-Standardtyp für `CDaoRecordset` ist **Dynaset** (Siehe den Hinweis unterhalb Fehler zusätzliche Informationen zu Momentaufnahmen von ODBC-Klasse).

- Die ODBC `CRecordset` -Klasse verfügt über eine Option zum Erstellen eines Forward-only-Recordset-Typs. In der `CDaoRecordset` vorwärts-Klasse ist kein Recordsettyp, aber stattdessen eine Eigenschaft (oder Option) eines bestimmten Typs von Recordsets.

- Eine Append-only-Recordset, beim Öffnen einer `CRecordset` Objekt bedeutete, dass das Recordset die Daten lesen und angefügt werden konnte. Mit `CDaoRecordset` Objekts, die nur-anfügen-Option bedeutet in der Tat, dass das Recordset die Daten nur können angefügt (und nicht gelesen werden).

- Die ODBC-Klassen Transaktion Memberfunktionen sind Mitglieder der `CDatabase` und reagieren auf Datenbankebene. In den DAO-Klassen, die Transaktion-Memberfunktionen sind Member einer Klasse mit höherer Ebene (`CDaoWorkspace`) und daher möglicherweise mehrere `CDaoDatabase` Objekte, die den gleichen Arbeitsbereich (Transaktionsbereich) freigeben.

- Die Exception-Klasse wurde geändert. `CDBExceptions` in den ODBC-Klassen ausgelöst werden und `CDaoExceptions` in den DAO-Klassen.

- `RFX_Date` verwendet `CTime` und `TIMESTAMP_STRUCT` Objekte beim `DFX_Date` verwendet `COleDateTime`. Die `COleDateTime` ist nahezu identisch mit `CTime`, aber basierend auf einer 8-Byte-OLE **Datum** statt einen 4-Byte- **Time_t** , damit sie einen viel größeren Bereich an Daten enthalten kann.

   > [!NOTE]
   > DAO (`CDaoRecordset`) Momentaufnahmen sind schreibgeschützt, während ODBC (`CRecordset`) Momentaufnahmen können je nach dem Treiber und die Verwendung der ODBC-Cursorbibliothek aktualisierbar sein. Bei Verwendung von der Cursorbibliothek `CRecordset` Momentaufnahmen können aktualisiert werden. Wenn Sie eines der Microsoft-Treiber von Desktop-Treiber Pack 3.0 ohne die ODBC-Cursorbibliothek verwenden die `CRecordset` Momentaufnahmen sind schreibgeschützt. Wenn Sie einem anderen Treiber verwenden, überprüfen Sie die Dokumentation des Treibers, um festzustellen, ob Momentaufnahmen (`STATIC_CURSORS`) sind schreibgeschützt.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
