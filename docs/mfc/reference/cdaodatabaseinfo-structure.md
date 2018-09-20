---
title: CDaoDatabaseInfo-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoDatabaseInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2c70e903e66a34bcb05302ac3732850f9dbb8fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380788"
---
# <a name="cdaodatabaseinfo-structure"></a>CDaoDatabaseInfo-Struktur

Die `CDaoDatabaseInfo` Struktur enthält Informationen zu einem Datenbankobjekt für Datenzugriffsobjekte (DAO) definiert.

## <a name="syntax"></a>Syntax

```
struct CDaoDatabaseInfo
{
    CString m_strName;       // Primary
    BOOL m_bUpdatable;       // Primary
    BOOL m_bTransactions;    // Primary
    CString m_strVersion;    // Secondary
    long m_lCollatingOrder;  // Secondary
    short m_nQueryTimeout;   // Secondary
    CString m_strConnect;    // All
};
```

#### <a name="parameters"></a>Parameter

*m_strName*<br/>
Das Datenbankobjekt, das eindeutig den Namen. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

*m_bUpdatable*<br/>
Gibt an, ob Änderungen an der Datenbank vorgenommen werden können. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Informationen finden Sie im Thema "Aktualisierbare Property" in-DAO-Hilfe.

*m_bTransactions*<br/>
Gibt an, ob eine Datenquelle Transaktionen unterstützt, die Aufzeichnung einer Reihe von Änderungen, die später ein Rollback ausgeführt werden können (abgebrochen) oder ein Commit ausgeführt (gespeichert). Wenn eine Datenbank auf der Microsoft Jet-Datenbank-Engine basiert, wird die Transactions-Eigenschaft ungleich NULL ist, und Transaktionen können verwendet werden. Andere Datenbank-Engines unterstützen möglicherweise keine Transaktionen. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Informationen finden Sie im Thema "Transaktionen Property" in-DAO-Hilfe.

*m_strVersion*<br/>
Gibt die Version der Microsoft Jet-Datenbank-Engine. Um den Wert dieser Eigenschaft direkt zu abzurufen, rufen Sie des Datenbankobjekt, das die [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) Member-Funktion. Informationen finden Sie im Thema "Version-Eigenschaft" in-DAO-Hilfe.

*m_lCollatingOrder*<br/>
Gibt die Sequenz der Sortierreihenfolge im Text für den Zeichenfolgenvergleich oder sortieren. Mögliche Werte:

- `dbSortGeneral` Verwenden Sie die allgemeine Sortierreihenfolge (Englisch, Französisch, Deutsch, Portugiesisch, Italienisch und moderne Spanisch).

- `dbSortArabic` Verwenden Sie die arabische Sortierreihenfolge.

- `dbSortCyrillic` Verwenden Sie die Sortierreihenfolge für Russisch.

- `dbSortCzech` Verwenden Sie die Tschechische Sortierreihenfolge.

- `dbSortDutch` Verwenden Sie die niederländische Sortierreihenfolge.

- `dbSortGreek` Verwenden Sie die Sortierreihenfolge für die griechische Sprache an.

- `dbSortHebrew` Verwenden Sie die hebräische Sortierreihenfolge.

- `dbSortHungarian` Verwenden Sie die Ungarisch Sortierreihenfolge.

- `dbSortIcelandic` Verwenden Sie die Icelandic Sortierreihenfolge.

- `dbSortNorwdan` Verwenden Sie die Norwegische oder dänische Sortierreihenfolge.

- `dbSortPDXIntl` Verwenden Sie die Sortierreihenfolge für die Paradox-International.

- `dbSortPDXNor` Verwenden Sie die Paradox Norwegische oder dänische Sortierreihenfolge.

- `dbSortPDXSwe` Mithilfe der Schwedischen Paradox oder Finnisch Sortierreihenfolge.

- `dbSortPolish` Verwenden Sie die Sortierreihenfolge für Polnisch.

- `dbSortSpanish` Verwenden Sie die spanische Sortierreihenfolge.

- `dbSortSwedFin` Verwenden Sie die Schwedischen oder Finnisch Sortierreihenfolge.

- `dbSortTurkish` Verwenden Sie die Sortierreihenfolge für die türkische Sprache an.

- `dbSortUndefined` Die Sortierreihenfolge ist nicht definiert oder unbekannt.

Weitere Informationen finden Sie im Thema "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" in-DAO-Hilfe.

*m_nQueryTimeout*<br/>
Die Anzahl der Sekunden, die die Microsoft Jet-Datenbank-Engine, bevor ein Timeout-Fehler wartet tritt auf, wenn eine Abfrage auf eine ODBC-Datenbank ausgeführt wird. Die Standard-Timeoutwert beträgt 60 Sekunden. Wenn QueryTimeout auf 0 festgelegt ist, erfolgt kein timeout Dadurch kann das Programm nicht mehr reagiert. Um den Wert dieser Eigenschaft direkt zu abzurufen, rufen Sie des Datenbankobjekt, das die [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) Member-Funktion. Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" in-DAO-Hilfe.

*m_strConnect*<br/>
Enthält Informationen zur Quelle für eine geöffnete Datenbank. Informationen zu connect Zeichenfolgen Informationen und Informationen direkt Abrufen des Werts dieser Eigenschaft finden Sie unter den [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) Member-Funktion. Weitere Informationen finden Sie im Thema "Verbinden der Eigenschaft" in-DAO-Hilfe.

## <a name="remarks"></a>Hinweise

Die Datenbank ist ein DAO-Objekt, das zugrunde liegende ein MFC-Objekt der Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Die Verweise auf die primäre, sekundäre und alle oben angegeben, wie die Informationen zurückgegeben werden, indem die [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) Member-Funktion.

Informationen, die abgerufen, indem die [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) Member-Funktion befindet sich in einem `CDaoDatabaseInfo` Struktur. Rufen Sie `GetDatabaseInfo` für die `CDaoWorkspace` -Objekt in die Auflistung, deren Datenbanken das Datenbankobjekt, das gespeichert wird. `CDaoDatabaseInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoDatabaseInfo` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)
