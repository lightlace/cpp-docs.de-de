---
title: DAO-Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 238aab0a1948f16a85b8ea16719b75b49f5e69c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241600"
---
# <a name="dao-classes"></a>DAO-Klassen

Diese Klassen funktionieren mit der anderen Anwendung Framework-Klassen zum einfachen Zugriff auf Datenbanken (Data Access Object, DAO) Geben Sie die gleiche Datenbank-Engine als Microsoft Visual Basic und Microsoft Access zu verwenden. Die DAO-Klassen können auch eine Vielzahl von Datenbanken zugreifen, für die Open Database Connectivity (ODBC)-Treiber zur Verfügung stehen.

Programme, die DAO-Datenbanken zugreifen müssen mindestens einen `CDaoDatabase` Objekt und ein `CDaoRecordset` Objekt.

> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten ohne mehr unterstützt (obwohl die DAO-Klassen enthalten sind, und Sie können diese weiterhin verwenden). Microsoft empfiehlt die Verwendung von ODBC für neue MFC-Projekte. Sie sollten nur DAO Verwaltung bereits vorhandener Anwendungen verwenden.

[CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
Verwaltet eine benannte, kennwortgeschützte datenbanksitzung von Anmeldung, um sich abzumelden. Die meisten Programme verwenden im Standardarbeitsbereich.

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
Eine Verbindung mit einer Datenbank, die über die die Daten bearbeitet werden können.

[CDaoRecordset](../mfc/reference/cdaorecordset-class.md)<br/>
Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.

[CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)<br/>
Stellt die Definition einer Abfrage, in der Regel eine in einer Datenbank gespeichert.

[CDaoTableDef](../mfc/reference/cdaotabledef-class.md)<br/>
Stellt die gespeicherte Definition einer Basistabelle oder einer angefügten Tabelle dar.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
Stellt eine Ausnahmebedingung, die von den DAO-Klassen dar.

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
Unterstützt die Routinen für den DAO-Datensatzfeldaustausch (DAO record field exchange, DFX), die von den DAO-Datenbankklassen verwendet werden. Diese Klasse wird normalerweise nicht direkt verwendet.

## <a name="related-classes"></a>Verwandte Klassen

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
Kapselt ein Handle für den Speicher für ein binary large Object (BLOB), z. B. eine Bitmap. `CLongBinary` Objekte werden verwendet, zum Verwalten von große Datenobjekte, die in Datenbanktabellen gespeichert.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Wrapper für den Typ der OLE-Automatisierung **Währung**, Festkomma-arithmetischen Typs, mit 15 Stellen vor dem Dezimaltrennzeichen und 4 Ziffern nach dem.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Wrapper für den Typ der OLE-Automatisierung **Datum**. Stellt Werte für Datum und Uhrzeit dar.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Wrapper für den Typ der OLE-Automatisierung **VARIANT**. Daten in **VARIANT**s kann in vielen Formaten gespeichert werden.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
