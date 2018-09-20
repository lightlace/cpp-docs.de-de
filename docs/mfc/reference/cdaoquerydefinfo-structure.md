---
title: CDaoQueryDefInfo-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoQueryDefInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 930626a2c28009f8f0174069a88a59a12c9059af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418540"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo-Struktur

Die `CDaoQueryDefInfo` Struktur enthält Informationen über ein Querydef-Objekt, das für Datenzugriffsobjekte (DAO) definiert.

## <a name="syntax"></a>Syntax

```
struct CDaoQueryDefInfo
{
    CString m_strName;               // Primary
    short m_nType;   // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    BOOL m_bUpdatable;               // Secondary
    BOOL m_bReturnsRecords;          // Secondary
    CString m_strSQL;                // All
    CString m_strConnect;            // All
    short m_nODBCTimeout;            // All
};
```

#### <a name="parameters"></a>Parameter

*m_strName*<br/>
Eindeutig benennt das Querydef-Objekt. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe. Rufen Sie [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) dieser Eigenschaft direkt abgerufen.

*m_nType*<br/>
Ein Wert, der die operative Typ eines Objekts Querydef angibt. Der Wert kann in folgenden Formen vorliegen:

- `dbQSelect` Select – die Abfrage wählt Datensätze.

- `dbQAction` Aktion – die Abfrage verschoben wird oder Daten ändert jedoch keine Datensätze zurückgibt.

- `dbQCrosstab` Kreuztabelle: die Abfrage gibt Daten in einem Tabellenformat an.

- `dbQDelete` Löschen – die Abfrage Löscht einen Satz von angegebenen Zeilen.

- `dbQUpdate` Update: die Abfrage ändert eine Gruppe von Datensätzen.

- `dbQAppend` Fügen Sie – die Abfrage fügt neue Datensätze am Ende einer Tabelle oder Abfrage.

- `dbQMakeTable` Make-Table – die Abfrage erstellt eine neue Tabelle aus einem Recordset.

- `dbQDDL` Daten-Definition, die Abfrage wirkt sich auf die Struktur der Tabellen oder deren Komponenten.

- `dbQSQLPassThrough` Pass-Through – die SQL-Anweisung wird direkt an die Datenbank-Back-End, ohne intermediate Verarbeitung übergeben.

- `dbQSetOperation` Union: die Abfrage erstellt eine Momentaufnahme-Type-Recordset-Objekt, das mit Daten aus allen angegebenen Datensätze in zwei oder mehr Tabellen, wobei doppelte Datensätze entfernt. Um die Duplikate einzuschließen, fügen Sie das Schlüsselwort **alle** Querydef des SQL-Anweisung.

- `dbQSPTBulk` Mit verwendet `dbQSQLPassThrough` zum Angeben einer Abfrage, die keine Datensätze zurückgibt.

> [!NOTE]
>  Um eine SQL-Pass-Through-Abfrage zu erstellen, legen Sie nicht die `dbQSQLPassThrough` Konstanten. Dies wird automatisch von der Microsoft Jet-Datenbank-Engine festgelegt, wenn Sie ein Querydef-Objekt erstellt, und legen Sie die Connect-Eigenschaft.

Weitere Informationen finden Sie im Thema "Type-Eigenschaft" in-DAO-Hilfe.

*m_dateCreated*<br/>
Das Datum und Uhrzeit der Erstellung die Querydef. Um direkt Abrufen des Datums die Querydef erstellt wurde, rufen Sie die [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) Memberfunktion die `CDaoTableDef` Objekt in der Tabelle zugeordnet. Weitere Informationen finden Sie in der Kommentare unten. Außerdem finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften", DAO-Hilfe zu erhalten.

*m_dateLastUpdated*<br/>
Das Datum und Uhrzeit der letzten Änderungen an der Querydef. Um direkt Abrufen des Datums in der Tabelle zuletzt aktualisiert wurde, rufen Sie die [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) Memberfunktion der Querydef. Weitere Informationen finden Sie in der Kommentare unten. Und finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.

*m_bUpdatable*<br/>
Gibt an, ob ein Querydef-Objekt geändert werden kann. Wenn diese Eigenschaft auf "true" ist, kann die Querydef aktualisiert; Andernfalls ist es nicht. Aktualisierbar bedeutet, dass es sich bei der Querydef Objektdefinition Abfrage geändert werden kann. Die aktualisierbaren-Eigenschaft eines Objekts Querydef ist auf TRUE festgelegt, wenn die Abfragedefinition aktualisiert werden kann, selbst wenn das resultierende Recordset nicht aktualisiert werden kann. Um diese Eigenschaft direkt zu abzurufen, rufen Sie die Querydef [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) Member-Funktion. Weitere Informationen finden Sie im Thema "Aktualisierbare Property" in-DAO-Hilfe.

*m_bReturnsRecords*<br/>
Gibt an, ob eine SQL-Pass-Through-Abfrage einer externen Datenbank Datensätze zurückgibt. Wenn diese Eigenschaft auf "true" ist, gibt die Abfrage Datensätze zurück. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Nicht alle Pass-Through-SQL-Abfragen für externe Datenbanken Gibt Datensätze zurück. Z. B. eine SQL **UPDATE** -Anweisung aktualisiert die Datensätze ohne Datensätze zurückzugeben, während eine SQL **wählen** Anweisung gibt Datensätze zurück. Weitere Informationen finden Sie im Thema "ReturnsRecords-Eigenschaft" in-DAO-Hilfe.

*m_strSQL*<br/>
Die SQL-Anweisung, die die von einem Objekt Querydef ausgeführte Abfrage definiert. Die SQL-Eigenschaft enthält die SQL-Anweisung, die bestimmt, wie Datensätze ausgewählt, gruppiert und sortiert werden, wenn Sie die Abfrage ausführen. Sie können die Abfrage verwenden, zum Auswählen von Datensätzen in einem Recordset-Objekt vom Typ Dynaset oder Momentaufnahmen eingeschlossen werden sollen. Sie können auch die Bulk-Abfragen, um Daten zu ändern, ohne die Datensätze zurückgeben definieren. Sie können den Wert dieser Eigenschaft abrufen, direkt durch Aufrufen des Querydef [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) Member-Funktion.

*m_strConnect*<br/>
Enthält Informationen zur Quelle für eine Datenbank in einer Pass-Through-Abfrage verwendet. Diese Informationen hat das Format einer Verbindungszeichenfolge. Weitere Informationen, Informationen zu connect Zeichenfolgen, und Informationen direkt Abrufen des Werts dieser Eigenschaft finden Sie unter den [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) Member-Funktion.

*m_nODBCTimeout*<br/>
Die Anzahl der Sekunden, die die Microsoft Jet-Datenbank-Engine, bevor ein Timeout-Fehler wartet tritt auf, wenn eine Abfrage auf eine ODBC-Datenbank ausgeführt wird. Bei der Verwendung einer ODBC-Datenbank, z. B. Microsoft SQL Server möglicherweise Verzögerungen aufgrund der Netzwerk-Datenverkehr oder hohem Verwenden des ODBC-Servers. Anstatt abzuwarten, können Sie angeben, wie lange der Microsoft Jet-Engine wartet, bevor er einen Fehler erzeugt. Die Standard-Timeoutwert beträgt 60 Sekunden. Sie können den Wert dieser Eigenschaft abrufen, direkt durch Aufrufen des Querydef [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) Member-Funktion. Weitere Informationen finden Sie im Thema "Timeoutfehlers warten soll Property" in-DAO-Hilfe.

## <a name="remarks"></a>Hinweise

Die Querydef ist ein Objekt der Klasse [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Die Verweise auf die primäre, sekundäre und alle oben angegeben, wie die Informationen zurückgegeben werden, indem die [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) Memberfunktion in Klasse `CDaoDatabase`.

Informationen, die abgerufen, indem die [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) Member-Funktion befindet sich in einem `CDaoQueryDefInfo` Struktur. Rufen Sie `GetQueryDefInfo` für das Datenbankobjekt, das im Element, dessen QueryDefs-Auflistung der Querydef-Objekt gespeichert wird. `CDaoQueryDefInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoQueryDefInfo` Objekt. Klasse `CDaoDatabase` auch stellt Memberfunktionen zur direkten Zugriff auf alle Eigenschaften zurückgegeben, die einem `CDaoQueryDefInfo` Objekt, daher Sie wahrscheinlich nur selten aufgerufen müssen `GetQueryDefInfo`.

Wenn Sie ein neues Feld oder Parameter-Objekt an die Felder oder Parameter-Auflistung eines Objekts Querydef angefügt werden soll, wird eine Ausnahme ausgelöst, wenn die zugrunde liegenden Datenbank für das neue Objekt angegebenen Datentyp nicht unterstützt.

Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Querydef erstellt oder zuletzt aktualisiert wurde. In einer mehrbenutzerumgebung, sollten Benutzer diese Einstellungen erhalten, direkt aus dem Datei-Server mithilfe der **net Time** Befehl aus, um die Vermeidung von abweichungen in den Einstellungen des DateCreated und LastUpdated-Eigenschaft.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)
