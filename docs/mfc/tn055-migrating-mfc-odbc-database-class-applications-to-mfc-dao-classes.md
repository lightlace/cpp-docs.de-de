---
title: 'TN055: Migrieren von MFC ODBC-Datenbankklassen-Anwendungen zu MFC DAO-Klassen'
ms.date: 09/17/2019
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
ms.openlocfilehash: 744e1c71476ccfbe6ea8f8359dcdb9a29efc995e
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305368"
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>TN055: Migrieren von MFC ODBC-Datenbankklassen-Anwendungen zu MFC DAO-Klassen

> [!NOTE]
> DAO wird für Access-Datenbanken verwendet und wird von Office 2013 unterstützt. DAO 3,6 ist die endgültige Version, die als veraltet eingestuft wird. Die visuelle C++ Umgebung und die Assistenten unterstützen DAO nicht (obwohl die DAO-Klassen eingeschlossen sind und Sie Sie weiterhin verwenden können). Microsoft empfiehlt, [OLE DB Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte zu verwenden. Sie sollten DAO nur für die Wartung vorhandener Anwendungen verwenden.

## <a name="overview"></a>Übersicht

In vielen Situationen kann es wünschenswert sein, Anwendungen zu migrieren, die die ODBC-Datenbankklassen von MFC zu den DAO-Datenbankklassen von MFC verwenden In diesem technischen Hinweis werden die meisten Unterschiede zwischen den MFC-ODBC-und DAO-Klassen ausführlich erläutert. Aufgrund der Unterschiede sollte es nicht übermäßig schwierig sein, Anwendungen von den ODBC-Klassen zu den MFC-Klassen zu migrieren, wenn dies gewünscht wird.

## <a name="why-migrate-from-odbc-to-dao"></a>Gründe für die Migration von ODBC zu DAO

Es gibt zahlreiche Gründe, warum Sie Anwendungen aus den ODBC-Datenbankklassen zu den DAO-Datenbankklassen migrieren möchten, aber die Entscheidung ist nicht notwendigerweise einfach oder offensichtlich. Beachten Sie, dass die von DAO verwendete Microsoft Jet-Datenbank-Engine jede ODBC-Datenquelle, für die Sie über einen ODBC-Treiber verfügen, lesen kann. Es kann effizienter sein, die ODBC-Datenbankklassen zu verwenden oder ODBC direkt aufzurufen, aber die Microsoft Jet-Datenbank-Engine kann ODBC-Daten lesen.

Einige einfache Fälle, die die ODBC/DAO-Entscheidung erleichtern. Wenn Sie beispielsweise nur den Zugriff auf Daten in einem Format benötigen, das von der Microsoft Jet-Engine direkt gelesen werden kann (Zugriffs Format, Excel-Format usw.), ist die Verwendung der DAO-Datenbankklassen die offensichtlichste Wahl.

Komplexere Fälle treten auf, wenn Ihre Daten auf einem Server oder auf einer Vielzahl von verschiedenen Servern vorhanden sind. In diesem Fall ist die Entscheidung für die Verwendung der ODBC-Datenbankklassen oder der DAO-Datenbankklassen schwierig. Wenn Sie z. b. heterogene Joins (Daten von Servern in mehreren Formaten wie SQL Server und Oracle) durchführen möchten, führt die Microsoft Jet-Datenbank-Engine den Join für Sie aus, anstatt Sie zu zwingen, die erforderlichen Schritte auszuführen, wenn Sie die ODBC-Datenbank verwendet haben. Klassen oder ODBC werden direkt aufgerufen. Wenn Sie einen ODBC-Treiber verwenden, der treibercursorn unterstützt, können Sie die ODBC-Datenbankklassen am besten verwenden.

Die Auswahl kann kompliziert sein. Daher sollten Sie einen Beispielcode schreiben, um die Leistung verschiedener Methoden anhand ihrer speziellen Anforderungen zu testen. Dieser Technische Hinweis setzt voraus, dass Sie die Entscheidung getroffen haben, von den ODBC-Datenbankklassen zu den DAO-Datenbankklassen zu migrieren.

## <a name="similarities-between-odbc-database-classes-and-mfc-dao-database-classes"></a>Ähnlichkeiten zwischen ODBC-Datenbankklassen und MFC-DAO-Datenbankklassen

Das ursprüngliche Design der MFC-ODBC-klassenbasiert auf dem DAO-Objektmodell, das in Microsoft Access und Microsoft Visual Basic verwendet wurde. Dies bedeutet, dass es viele gängige Features der ODBC-und DAO-MFC-Klassen gibt, die nicht alle in diesem Abschnitt aufgeführt werden. Im Allgemeinen sind die Programmier Modelle identisch.

Um einige Ähnlichkeiten hervorzuheben:

- Die ODBC-und DAO-Klassen verfügen über Datenbankobjekte, die mit dem zugrunde liegenden Datenbank-Management System (DBMS) verwalten.

- Beide haben Recordset-Objekte, die eine Reihe von Ergebnissen darstellen, die von diesem DBMS zurückgegeben werden.

- Die DAO-Datenbank und Recordset-Objekte haben Elemente, die fast identisch mit den ODBC-Klassen sind.

- Bei beiden Gruppen von Klassen ist der Code zum Abrufen von Daten mit Ausnahme von Änderungen an Objekt-und Elementnamen identisch. Änderungen sind erforderlich, aber in der Regel handelt es sich bei dem Prozess um eine einfache Namensänderung beim Wechsel von den ODBC-Klassen zu DAO-Klassen.

Beispielsweise besteht in beiden Modellen die Prozedur zum Abrufen von Daten darin, ein Datenbankobjekt zu erstellen und zu öffnen, ein Recordset-Objekt zu erstellen und zu öffnen und zu navigieren (verschieben), obwohl die Daten einen Vorgang ausführen.

## <a name="differences-between-odbc-and-dao-mfc-classes"></a>Unterschiede zwischen ODBC-und DAO-MFC-Klassen

Die DAO-Klassen enthalten mehr Objekte und einen umfassenderen Satz von Methoden, aber in diesem Abschnitt werden nur die Unterschiede in ähnlichen Klassen und Funktionen ausführlich erläutert.

Die offensichtlichsten Unterschiede zwischen den Klassen sind wahrscheinlich die Namensänderungen für ähnliche Klassen und globale Funktionen. Die folgende Liste zeigt die Namensänderungen der-Objekte,-Methoden und globalen Funktionen, die den-Datenbankklassen zugeordnet sind:

|Klasse oder Funktion|Äquivalent in MFC DAO-Klassen|
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

<sup>1</sup> die `RFX_Date`-Funktion basiert auf `CTime` und `TIMESTAMP_STRUCT`.

Die wichtigsten Änderungen an den Funktionen, die sich auf Ihre Anwendung auswirken können und mehr als einfache Namensänderungen erfordern, sind unten aufgeführt.

- Die Konstanten und Makros, die zum Angeben von Elementen wie Recordset-Open-Type-und Recordset-Öffnungs Optionen verwendet werden, wurden geändert.

   Mit den ODBC-Klassen, die MFC benötigt, um diese Optionen über Makros oder Enumerationstypen zu definieren.

   Mit den DAO-Klassen stellt DAO die Definition dieser Optionen in einer Header Datei (dbdaoint) bereit. H). Daher ist der Recordsettyp ein enumerierter Member von `CRecordset`, aber mit DAO ist es stattdessen eine Konstante. Beispielsweise verwenden Sie **Snapshot** , wenn Sie den Typ der `CRecordset` in ODBC angeben, aber **DB_OPEN_SNAPSHOT** beim Angeben des `CDaoRecordset`Typs.

- Der standardrecordsettyp für `CRecordset` ist **Snapshot** , während der standardrecordsettyp für `CDaoRecordset` **Dynaset** ist (Weitere Informationen zu ODBC-Klassen Momentaufnahmen finden Sie im Hinweis unten).

- Die ODBC-`CRecordset`-Klasse verfügt über eine Option zum Erstellen eines voreingestellten Recordsettyps. In der `CDaoRecordset`-Klasse ist Forward-Only kein Recordsettyp, sondern eine Eigenschaft (oder Option) bestimmter Typen von Recordsets.

- Ein nur anfügende Recordset beim Öffnen eines `CRecordset` Objekts bedeutete, dass die Daten des Recordsets gelesen und angefügt werden konnten. Mit `CDaoRecordset`-Objekt bedeutet die Option nur anhängen, dass die Daten des Recordsets nur angehängt (und nicht gelesen) werden können.

- Die Transaktions Element Funktionen der ODBC-Klassen sind Mitglieder von `CDatabase` und agieren auf Datenbankebene. In den DAO-Klassen sind die transaktionsmember-Funktionen Member einer Klasse höherer Ebene (`CDaoWorkspace`) und können sich daher auf mehrere `CDaoDatabase` Objekte auswirken, die denselben Arbeitsbereich (Transaktions Bereich) gemeinsam nutzen.

- Die Ausnahme Klasse wurde geändert. `CDBExceptions` werden in den ODBC-Klassen und in den DAO-Klassen `CDaoExceptions` ausgelöst.

- `RFX_Date` verwendet `CTime` und `TIMESTAMP_STRUCT`-Objekte, während `DFX_Date` `COleDateTime`verwendet. Der `COleDateTime` ist nahezu identisch mit `CTime`, basiert aber auf einem 8-Byte-OLE- **Datum** und nicht auf einem 4-Byte- **time_t** , sodass es einen viel größeren Datenbereich enthalten kann.

   > [!NOTE]
   > DAO (`CDaoRecordset`)-Momentaufnahmen sind schreibgeschützt, während ODBC-Momentaufnahmen (`CRecordset`) je nach Treiber und Verwendung der ODBC-Cursor Bibliothek aktualisierbar sind. Wenn Sie die Cursor Bibliothek verwenden, sind `CRecordset` Momentaufnahmen aktualisierbar. Wenn Sie einen der Microsoft-Treiber aus Desktop Driver Pack 3,0 ohne die ODBC-Cursor Bibliothek verwenden, sind die `CRecordset`-Momentaufnahmen schreibgeschützt. Wenn Sie einen anderen Treiber verwenden, überprüfen Sie in der Dokumentation des Treibers, ob Momentaufnahmen (`STATIC_CURSORS`) schreibgeschützt sind.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
