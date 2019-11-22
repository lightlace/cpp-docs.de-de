---
title: CDaoDatabaseInfo-Struktur
ms.date: 09/17/2019
f1_keywords:
- CDaoDatabaseInfo
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
ms.openlocfilehash: 60972aa3ecaef4d38c9a0d0ecc70477796aa37aa
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304251"
---
# <a name="cdaodatabaseinfo-structure"></a>CDaoDatabaseInfo-Struktur

Die `CDaoDatabaseInfo`-Struktur enthält Informationen zu einem Datenbankobjekt, das für Data Access Objects (DAO) definiert ist. DAO 3,6 ist die endgültige Version, die als veraltet eingestuft wird.

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
Benennt das Datenbankobjekt eindeutig. Rufen Sie zum direkten Abrufen dieser Eigenschaft [CDaoDatabase:: GetName](../../mfc/reference/cdaodatabase-class.md#getname)auf. Weitere Informationen finden Sie im Thema "Name Property" in der DAO-Hilfe.

*m_bUpdatable*<br/>
Gibt an, ob Änderungen an der Datenbank vorgenommen werden können. Rufen Sie zum direkten Abrufen dieser Eigenschaft [CDaoDatabase:: CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate)auf. Weitere Informationen finden Sie im Thema "aktualisierbare Eigenschaft" in der DAO-Hilfe.

*m_bTransactions*<br/>
Gibt an, ob eine Datenquelle Transaktionen unterstützt – die Aufzeichnung einer Reihe von Änderungen, für die später ein Rollback (abgebrochen) oder ein Commit (gespeichert) ausgeführt werden kann. Wenn eine Datenbank auf der Microsoft Jet-Datenbank-Engine basiert, ist die Transactions-Eigenschaft nicht NULL, und Sie können Transaktionen verwenden. Andere Datenbank-Engines unterstützen Transaktionen möglicherweise nicht. Rufen Sie zum direkten Abrufen dieser Eigenschaft [CDaoDatabase:: CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact)auf. Weitere Informationen finden Sie im Thema "Transactions-Eigenschaft" in der DAO-Hilfe.

*m_strVersion*<br/>
Gibt die Version der Microsoft Jet-Datenbank-Engine an. Um den Wert dieser Eigenschaft direkt abzurufen, rufen Sie die [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) -Member-Funktion des Datenbankobjekts auf. Weitere Informationen finden Sie im Thema "Versions Eigenschaft" in der DAO-Hilfe.

*m_lCollatingOrder*<br/>
Gibt die Reihenfolge der Sortierreihenfolge im Text für den Zeichen folgen Vergleich oder die Sortierung an. Mögliche Werte:

- `dbSortGeneral` die Sortierreihenfolge Allgemein (Englisch, Französisch, Deutsch, Portugiesisch, Italienisch und modern Spanisch) verwenden.

- `dbSortArabic` die arabische Sortierreihenfolge verwenden.

- `dbSortCyrillic` die russische Sortierreihenfolge verwenden.

- `dbSortCzech` die Tschechische Sortierreihenfolge verwenden.

- `dbSortDutch` die niederländische Sortierreihenfolge verwenden.

- `dbSortGreek` die griechische Sortierreihenfolge verwenden.

- `dbSortHebrew` die hebräische Sortierreihenfolge verwenden.

- `dbSortHungarian` die ungarische Sortierreihenfolge verwenden.

- `dbSortIcelandic` die in der isländischen Sortierreihenfolge verwenden.

- `dbSortNorwdan` die norwegische oder dänische Sortierreihenfolge verwenden.

- `dbSortPDXIntl` die internationale in der-Sortierreihenfolge verwenden.

- `dbSortPDXNor` die "Paradox Norwegian" oder "Danish"-Sortierreihenfolge

- `dbSortPDXSwe` die "Paradox Swedish or Finnish"-Sortierreihenfolge verwenden.

- `dbSortPolish` die polnische Sortierreihenfolge verwenden.

- `dbSortSpanish` die spanische Sortierreihenfolge verwenden.

- `dbSortSwedFin` die schwedische oder finnische Sortierreihenfolge verwenden.

- `dbSortTurkish` die Reihenfolge der türkischen Sortierreihenfolge verwenden.

- `dbSortUndefined` die Sortierreihenfolge ist nicht definiert oder unbekannt.

Weitere Informationen finden Sie im Thema zum Anpassen der Windows-Registrierungs Einstellungen für den Datenzugriff in der DAO-Hilfe.

*m_nQueryTimeout*<br/>
Die Anzahl der Sekunden, die die Microsoft Jet-Datenbank-Engine wartet, bevor ein Timeout Fehler auftritt, wenn eine Abfrage in einer ODBC-Datenbank ausgeführt wird. Der Standardwert für das Timeout beträgt 60 Sekunden. Wenn QueryTimeout auf 0 festgelegt ist, tritt kein Timeout auf. Dies kann dazu führen, dass das Programm nicht mehr reagiert. Um den Wert dieser Eigenschaft direkt abzurufen, rufen Sie die [getquerytimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) -Member-Funktion des Datenbankobjekts auf. Weitere Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" in der DAO-Hilfe.

*m_strConnect*<br/>
Stellt Informationen zur Quelle einer geöffneten Datenbank bereit. Weitere Informationen zu Verbindungs Zeichenfolgen und Informationen zum direkten Abrufen des Werts dieser Eigenschaft finden Sie unter der [CDaoDatabase:: GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) -Member-Funktion. Weitere Informationen finden Sie im Thema "Connect Property" in der DAO-Hilfe.

## <a name="remarks"></a>Hinweise

Die Datenbank ist ein DAO-Objekt, das einem MFC-Objekt der Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)zugrunde liegt. Die Verweise auf Primär, Sekundär und alle oben aufgeführten Informationen geben an, wie die Informationen von der [CDaoWorkspace:: getDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) -Member-Funktion zurückgegeben werden.

Informationen, die von der [CDaoWorkspace:: getDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) -Member-Funktion abgerufen werden, werden in einer `CDaoDatabaseInfo` Struktur gespeichert. Ruft `GetDatabaseInfo` für das `CDaoWorkspace` Objekt in auf, dessen Daten Bank Auflistung das Datenbankobjekt gespeichert wird. `CDaoDatabaseInfo` definiert auch eine `Dump` Member-Funktion in Debugbuilds. Sie können `Dump` verwenden, um den Inhalt eines `CDaoDatabaseInfo` Objekts zu speichern.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)
