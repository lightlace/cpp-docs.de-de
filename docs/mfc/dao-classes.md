---
title: DAO-Klassen
ms.date: 09/17/2019
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: febd20971fd85275bd7ded0d2216fab0e05adbd1
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095610"
---
# <a name="dao-classes"></a>DAO-Klassen

DAO wird für Access-Datenbanken verwendet und wird von Office 2013 unterstützt. 3,6 ist die endgültige Version und wird als veraltet eingestuft.

Diese Klassen funktionieren mit den anderen Application Framework-Klassen, um einfachen Zugriff auf Datenzugriffs Objekt-Datenbanken (Data Access Object, DAO) zu erhalten, die dieselbe Datenbank-Engine wie Microsoft Visual Basic und Microsoft Access verwenden. Die DAO-Klassen können auch auf eine Vielzahl von Datenbanken zugreifen, für die Open Database Connectivity (ODBC)-Treiber verfügbar sind.

Programme, die DAO-Datenbanken verwenden, verfügen `CDaoDatabase` über mindestens ein `CDaoRecordset` -Objekt und ein-Objekt.

> [!NOTE]
>  Die visuelle C++ Umgebung und die Assistenten unterstützen DAO nicht mehr (obwohl die DAO-Klassen eingeschlossen sind und Sie Sie weiterhin verwenden können). Microsoft empfiehlt die Verwendung von ODBC für neue MFC-Projekte. Sie sollten DAO nur für die Wartung vorhandener Anwendungen verwenden.

[CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
Verwaltet eine benannte, Kenn Wort geschützte Daten banksitzung von der Anmeldung bis zum Abmelden. Die meisten Programme verwenden den Standard Arbeitsbereich.

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
Eine Verbindung mit einer Datenbank, über die Sie mit den Daten arbeiten können.

[CDaoRecordset](../mfc/reference/cdaorecordset-class.md)<br/>
Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.

[CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)<br/>
Stellt eine Abfrage Definition dar, die in der Regel in einer Datenbank gespeichert ist.

[CDaoTableDef](../mfc/reference/cdaotabledef-class.md)<br/>
Stellt die gespeicherte Definition einer Basistabelle oder einer angefügten Tabelle dar.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
Stellt eine Ausnahme Bedingung dar, die sich aus den DAO-Klassen ergibt.

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
Unterstützt die Routinen für den DAO-Datensatzfeldaustausch (DAO record field exchange, DFX), die von den DAO-Datenbankklassen verwendet werden. Diese Klasse wird normalerweise nicht direkt verwendet.

## <a name="related-classes"></a>Verwandte Klassen

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
Kapselt ein Handle für den Speicher für einen Binary Large Object (BLOB), z. b. eine Bitmap. `CLongBinary`Objekte werden verwendet, um große Datenobjekte zu verwalten, die in Datenbanktabellen gespeichert werden.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Wrapper für die OLE-Automatisierungs **typwährung**, einen arithmetischen Typ mit festem Punkt, mit 15 Ziffern vor dem Dezimaltrennzeichen und vier Ziffern nach.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Wrapper für das **Datum**des OLE-Automatisierungs Typs. Stellt Datums-und Uhrzeitwerte dar.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Wrapper für den OLE-Automatisierungstyp **Variant**. Daten in **Variant**s können in vielen Formaten gespeichert werden.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../mfc/class-library-overview.md)
