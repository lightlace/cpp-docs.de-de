---
title: CDaoWorkspace-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoWorkspace
- AFXDAO/CDaoWorkspace
- AFXDAO/CDaoWorkspace::CDaoWorkspace
- AFXDAO/CDaoWorkspace::Append
- AFXDAO/CDaoWorkspace::BeginTrans
- AFXDAO/CDaoWorkspace::Close
- AFXDAO/CDaoWorkspace::CommitTrans
- AFXDAO/CDaoWorkspace::CompactDatabase
- AFXDAO/CDaoWorkspace::Create
- AFXDAO/CDaoWorkspace::GetDatabaseCount
- AFXDAO/CDaoWorkspace::GetDatabaseInfo
- AFXDAO/CDaoWorkspace::GetIniPath
- AFXDAO/CDaoWorkspace::GetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::GetLoginTimeout
- AFXDAO/CDaoWorkspace::GetName
- AFXDAO/CDaoWorkspace::GetUserName
- AFXDAO/CDaoWorkspace::GetVersion
- AFXDAO/CDaoWorkspace::GetWorkspaceCount
- AFXDAO/CDaoWorkspace::GetWorkspaceInfo
- AFXDAO/CDaoWorkspace::Idle
- AFXDAO/CDaoWorkspace::IsOpen
- AFXDAO/CDaoWorkspace::Open
- AFXDAO/CDaoWorkspace::RepairDatabase
- AFXDAO/CDaoWorkspace::Rollback
- AFXDAO/CDaoWorkspace::SetDefaultPassword
- AFXDAO/CDaoWorkspace::SetDefaultUser
- AFXDAO/CDaoWorkspace::SetIniPath
- AFXDAO/CDaoWorkspace::SetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::SetLoginTimeout
- AFXDAO/CDaoWorkspace::m_pDAOWorkspace
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspace [MFC], CDaoWorkspace
- CDaoWorkspace [MFC], Append
- CDaoWorkspace [MFC], BeginTrans
- CDaoWorkspace [MFC], Close
- CDaoWorkspace [MFC], CommitTrans
- CDaoWorkspace [MFC], CompactDatabase
- CDaoWorkspace [MFC], Create
- CDaoWorkspace [MFC], GetDatabaseCount
- CDaoWorkspace [MFC], GetDatabaseInfo
- CDaoWorkspace [MFC], GetIniPath
- CDaoWorkspace [MFC], GetIsolateODBCTrans
- CDaoWorkspace [MFC], GetLoginTimeout
- CDaoWorkspace [MFC], GetName
- CDaoWorkspace [MFC], GetUserName
- CDaoWorkspace [MFC], GetVersion
- CDaoWorkspace [MFC], GetWorkspaceCount
- CDaoWorkspace [MFC], GetWorkspaceInfo
- CDaoWorkspace [MFC], Idle
- CDaoWorkspace [MFC], IsOpen
- CDaoWorkspace [MFC], Open
- CDaoWorkspace [MFC], RepairDatabase
- CDaoWorkspace [MFC], Rollback
- CDaoWorkspace [MFC], SetDefaultPassword
- CDaoWorkspace [MFC], SetDefaultUser
- CDaoWorkspace [MFC], SetIniPath
- CDaoWorkspace [MFC], SetIsolateODBCTrans
- CDaoWorkspace [MFC], SetLoginTimeout
- CDaoWorkspace [MFC], m_pDAOWorkspace
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 964fab6030e0a89ef69730fd4867973e402db614
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442018"
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace-Klasse

Verwaltet eine benannte, kennwortgeschützte Datenbanksitzung eines einzelnen Benutzers von der Anmeldung bis zu Abmeldung.

## <a name="syntax"></a>Syntax

```
class CDaoWorkspace : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|Erstellt ein Workspace-Objekt. Rufen Sie anschließend `Create` oder `Open`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDaoWorkspace::Append](#append)|Fügt einen neu erstellten Arbeitsbereich für die Datenbank-Engine-Arbeitsbereiche Sammlung an.|
|[CDaoWorkspace::BeginTrans](#begintrans)|Beginnt eine neue Transaktion, die auf alle Datenbanken, die im Arbeitsbereich geöffnet wird.|
|[CDaoWorkspace::Close](#close)|Schließt den Arbeitsbereich und alle darin enthaltenen Objekte. Ausstehende Transaktionen ein Rollback ausgeführt.|
|[CDaoWorkspace::](#committrans)|Schließt die aktuelle Transaktion ab und speichert die Änderungen.|
|[CDaoWorkspace:: CompactDatabase](#compactdatabase)|Eine Datenbank komprimiert (oder dupliziert).|
|[CDaoWorkspace:: Create](#create)|Erstellt ein neues Objekt des DAO-Arbeitsbereich.|
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|Gibt die Anzahl der DAO-Datenbankobjekte in der arbeitsbereichssammlung Datenbanken zurück.|
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|Gibt Informationen zu einer angegebenen DAO-Datenbank, die in der datenbankauflistung des Arbeitsbereichs definiert.|
|[CDaoWorkspace::GetIniPath](#getinipath)|Gibt den Speicherort der Microsoft Jet-Datenbank-Engine-initialisierungseinstellungen in der Windows-Registrierung zurück.|
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|Gibt einen Wert, der angibt, ob mehrere Transaktionen, bei denen die ODBC-Datenquelle über isoliert sind, mehrere Verbindungen mit der Datenquelle erzwungen.|
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|Gibt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn der Benutzer versucht, eine ODBC-Datenbank anmelden.|
|[CDaoWorkspace::GetName](#getname)|Der benutzerdefinierte Name für die Workspace-Objekt zurückgegeben.|
|[CDaoWorkspace::GetUserName](#getusername)|Gibt zurück, der Benutzername angegeben, wenn der Arbeitsbereich erstellt wurde. Dies ist der Name der Besitzer des Arbeitsbereichs.|
|[CDaoWorkspace::GetVersion](#getversion)|Gibt eine Zeichenfolge mit der Version der Datenbank-Engine, die mit dem Arbeitsbereich verknüpft ist.|
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|Gibt die Anzahl der Objekte für DAO-Arbeitsbereich in der Datenbank-Engine-arbeitsbereicheauflistung zurück.|
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|Gibt Informationen zu einem angegebenen DAO-Arbeitsbereich in der Datenbank-Engine-arbeitsbereicheauflistung definiert.|
|[CDaoWorkspace::Idle](#idle)|Können die Datenbank-Engine zum Ausführen von Hintergrundaufgaben.|
|[CDaoWorkspace::IsOpen](#isopen)|Gibt zurück, die ungleich NULL, wenn der Arbeitsbereich öffnen.|
|[CDaoWorkspace::Open](#open)|Explizit öffnet ein Workspace-Objekt, das mit DAO Standard-Arbeitsbereich verknüpft ist.|
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|Versucht, eine beschädigte Datenbank zu reparieren.|
|[CDaoWorkspace::Rollback](#rollback)|Beendet die aktuelle Transaktion aus, und die Änderungen nicht gespeichert.|
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|Legt das Kennwort, das die Datenbank-Engine verwendet wird, wenn eine Arbeitsbereichsobjekt ohne ein bestimmtes Kennwort erstellt wird.|
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|Legt fest, den Benutzernamen ein, dem die Datenbank-Engine verwendet wird, wenn eine Arbeitsbereichsobjekt ohne einen bestimmten Benutzernamen erstellt wird.|
|[CDaoWorkspace::SetIniPath](#setinipath)|Legt den Speicherort der Microsoft Jet-Datenbank-Engine-initialisierungseinstellungen in der Windows-Registrierung fest.|
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|Gibt an, ob mehrere Transaktionen, bei denen die ODBC-Datenquelle isoliert werden, indem Sie mehrere Verbindungen mit der Datenquelle zu erzwingen.|
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|Legt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn der Benutzer versucht, eine ODBC-Datenquelle anmelden.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|Verweist auf das zugrunde liegende DAO-Workspace-Objekt.|

## <a name="remarks"></a>Hinweise

In den meisten Fällen benötigen Sie nicht mehrere Arbeitsbereiche, und Sie müssen keine explizite Workspace-Objekte zu erstellen; Wenn Sie die Datenbank und Recordset-Objekte öffnen, verwenden sie die DAO Standard-Arbeitsbereich. Allerdings können Sie mehrere Sitzungen zu einem Zeitpunkt führen Sie bei Bedarf zusätzliche Workspace-Objekte erstellen. Jedes Arbeitsbereichsobjekt kann mehrere geöffneten Datenbankobjekten in seine eigene Sammlung von Datenbanken enthalten. In MFC ist ein Arbeitsbereich in erster Linie eine Transaktions-Manager, eine Reihe von open Datenbanken angeben, alle in der "Transaktionsprotokoll-Speicherplatz."

> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von der MFC-Datenbankklassen in Bezug auf Open Database Connectivity (ODBC). Allen Klassennamen der DAO-Datenbank haben ein Präfix "CDao". Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC. Die DAO-basierten Klassen greifen auf Daten über das Microsoft Jet-Datenbankmodul, einschließlich der ODBC-Treiber. Außerdem unterstützen (Data Definition Language, Datendefinitionssprache)-Vorgänge, z. B. das Erstellen von Datenbanken und Tabellen und Felder, die über die Klassen, ohne direkt aufrufen von DAO hinzufügen.

## <a name="capabilities"></a>Funktionen

Klasse `CDaoWorkspace` ermöglicht Folgendes:

- Explizite Zugriff, falls erforderlich, um eine Standard-Arbeitsbereich, und initialisieren Sie die Datenbank-Engine erstellt. In der Regel verwenden Sie DAOs-Standard-Arbeitsbereich implizit durch das Erstellen der Datenbank und Recordset-Objekte.

- Öffnen Sie ein Transaktionsprotokoll-Speicherplatz in dem Transaktionen gilt für alle Datenbanken im Arbeitsbereich. Sie können zusätzliche Arbeitsbereiche zum Verwalten von separaten Transaktion Speicherplätze erstellen.

- Eine Schnittstelle für viele Eigenschaften der zugrunde liegenden Microsoft Jet-Datenbank-Engine (siehe die statische Memberfunktionen). Öffnen oder Erstellen eines Arbeitsbereichs oder Aufrufen einer statischen Memberfunktion vor dem Öffnen oder erstellen, und initialisiert die Datenbank-Engine.

- Zugriff auf die Datenbank-Engine-Arbeitsbereiche-Auflistung, der alle aktiven Arbeitsbereiche gespeichert, die es angefügt wurden. Sie können auch erstellen und Verwenden von Arbeitsbereichen, ohne auf die Auflistung anfügen.

## <a name="security"></a>Sicherheit

MFC implementiert nicht die Sammlungen für Benutzer und Gruppen über DAO, die für die sicherheitssteuerung verwendet werden. Wenn Sie die Aspekte des DAO benötigen, müssen Sie sie selbst über direkte Aufrufe von DAO-Schnittstellen programmieren. Weitere Informationen finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

## <a name="usage"></a>Verwendung

Sie können die Klasse `CDaoWorkspace` auf:

- Öffnen Sie explizit die Standard-Arbeitsbereich.

     In der Regel die Verwendung des Standard-Arbeitsbereich ist implizit, wenn Sie neue öffnen [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte. Sie müssen jedoch möglicherweise für den Zugriff explizit – z. B. zum Zugriff auf Datenbank-Engine-Eigenschaften oder die Arbeitsbereiche-Auflistung. Nachfolgend finden Sie in der "Impliziten Verwendung der Standard-Arbeitsbereich".

- Neue Arbeitsbereiche zu erstellen. Rufen Sie [Append](#append) , wenn Sie sie auf die Auflistung der Arbeitsbereiche hinzufügen möchten.

- Öffnen Sie einen vorhandenen Arbeitsbereich, in der Auflistung der Arbeitsbereiche.

Erstellen einen neuen Arbeitsbereich ein, die noch nicht vorhanden in den Arbeitsbereichen der Auflistung beschrieben, unter wird dem [erstellen](#create) Member-Funktion. Workspace-Objekte beibehalten in keiner Weise zwischen Beispieldatenbank-Engine-Sitzungen nicht. Wenn Ihre Anwendung statisch MFC verknüpft ist, wird beim Beenden der Anwendung die Datenbank-Engine deinitialisiert. Wenn Ihre Anwendung dynamisch mit MFC verknüpft wird, ist die Datenbank-Engine nicht initialisiert, wenn die MFC-DLL entladen wird.

Explizit öffnen die Standard-Arbeitsbereich, oder öffnen einen vorhandenen Arbeitsbereich, in der Auflistung Arbeitsbereiche finden Sie unter den [öffnen](#open) Member-Funktion.

Eine Arbeitsbereich-Sitzung beenden durch Schließen des Arbeitsbereichs mit der [schließen](#close) Member-Funktion. `Close` Schließt alle Datenbanken, die Sie nicht zuvor geschlossen haben Rollback für Transaktionen ohne Commit ausgeführt.

## <a name="transactions"></a>Transaktionen

DAO verwaltet Transaktionen auf der arbeitsbereichsebene. Transaktionen in einem Arbeitsbereich mit mehreren open-Datenbanken, daher gelten für alle Datenbanken. Z. B. wenn zwei Datenbanken haben ohne ausgeführten Commit Updates, und Sie rufen [CommitTrans](#committrans), alle Updates wird ein Commit ausgeführt. Wenn Sie Transaktionen auf eine einzelne Datenbank beschränken möchten, benötigen Sie ein eigenes Workspace-Objekt für sie.

## <a name="implicit-use-of-the-default-workspace"></a>Implizite Verwendung von Standard-Arbeitsbereich

Verwendet MFC-DAO Standard-Arbeitsbereich implizit in den folgenden Situationen:

- Wenn Sie ein neues erstellen `CDaoDatabase` Objekt jedoch nicht über einen vorhandenen aus `CDaoWorkspace` -Objekt MFC erstellt ein Objekt der temporäre Arbeitsbereich für Sie die DAO Standard-Arbeitsbereich entspricht. Wenn Sie für mehrere Datenbanken dazu sind alle Datenbankobjekte mit Standard-Arbeitsbereich verknüpft. Sie können einer Datenbank mit dem Arbeitsbereich über den Zugriff eine `CDaoDatabase` -Datenmember.

- Auf ähnliche Weise bei der Erstellung einer `CDaoRecordset` Objekt ohne einen Zeiger auf eine `CDaoDatabase` -Objekt MFC wird ein temporäres Objekt erstellt und durch Erweiterung, ein temporärer Arbeitsbereich-Objekt. Sie erreichen ein Recordset Datenbank und den Arbeitsbereich, indirekt über eine `CDaoRecordset` -Datenmember.

## <a name="other-operations"></a>Andere Vorgänge

Andere Datenbankoperationen werden ebenfalls bereitgestellt, z. B. eine beschädigte Datenbank zu reparieren oder Komprimieren einer Datenbank.

Weitere Informationen zum Aufrufen von DAO direkt und DAO-Sicherheit, finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CDaoWorkspace`

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

##  <a name="append"></a>  CDaoWorkspace::Append

Rufen Sie diese Memberfunktion auf, nach dem Aufruf von [erstellen](#create).

```
virtual void Append();
```

### <a name="remarks"></a>Hinweise

`Append` Fügt ein Arbeitsbereichsobjekt für die neu erstellte des Datenbank-Engine-arbeitsbereicheauflistung an. Arbeitsbereiche beibehalten zwischen Datenbank-Engine-Sitzungen nicht; Sie werden nur im Arbeitsspeicher, nicht auf dem Datenträger gespeichert. Sie müssen keine fügen Sie einen Arbeitsbereich; Wenn Sie nicht, können Sie weiterhin verwenden.

Ein angefügten Arbeitsbereich bleibt in der Auflistung Arbeitsbereiche in einem aktiven Zustand "geöffnet", bis zum Aufruf der [schließen](#close) Member-Funktion.

Weitere Informationen finden Sie unter dem Thema "Fügen Sie der Methode" in-DAO-Hilfe.

##  <a name="begintrans"></a>  CDaoWorkspace::BeginTrans

Rufen Sie diese Memberfunktion zum Initiieren einer Transaktion.

```
void BeginTrans();
```

### <a name="remarks"></a>Hinweise

Nach dem Aufruf von `BeginTrans`, Updates, die Sie, um die Struktur der Daten oder Datenbankobjekte vornehmen werden wirksam, wenn Sie die Transaktion einen Commit ausführen. Da der Arbeitsbereich einen einzelnen Transaktionsbereich definiert, gilt die Transaktion alle geöffneten Datenbanken in den Arbeitsbereich ab. Es gibt zwei Möglichkeiten, um die Transaktion abzuschließen:

- Rufen Sie die [CommitTrans](#committrans) Memberfunktion, um die Transaktion ein Commit ausgeführt, und speichern Sie Änderungen an der Datenquelle.

- Oder rufen Sie die [Rollback](#rollback) Memberfunktion, die Transaktion abzubrechen.

Die Workspace-Objekt oder ein Datenbankobjekt schließen, während eine Transaktion ausstehende wird ein Rollback aller anstehende Transaktionen.

Wenn Sie Transaktionen auf eine ODBC-Datenquelle, von denen für eine andere ODBC-Datenquelle zu isolieren möchten, finden Sie unter den [SetIsolateODBCTrans](#setisolateodbctrans) Member-Funktion.

##  <a name="cdaoworkspace"></a>  CDaoWorkspace::CDaoWorkspace

Erstellt ein `CDaoWorkspace`-Objekt.

```
CDaoWorkspace();
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen der C++-Objekt, haben Sie zwei Möglichkeiten:

- Aufrufen des Objekts [öffnen](#open) Memberfunktion Standard-Arbeitsbereich zu öffnen oder ein vorhandenes Objekt in der Auflistung der Arbeitsbereiche geöffnet.

- Aufrufen des Objekts [erstellen](#create) Memberfunktion versucht, ein neues Objekt des DAO-Arbeitsbereich erstellen. Dies startet explizit eine neue Workspace-Sitzung, die Sie über verweisen können die `CDaoWorkspace` Objekt. Nach dem Aufruf `Create`, rufen Sie [Append](#append) , wenn Sie den Arbeitsbereich für die Datenbank-Engine-Arbeitsbereiche Sammlung hinzufügen möchten.

Finden Sie unter der Übersicht zur Klasse [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Informationen, wenn Sie explizit erstellen, müssen eine `CDaoWorkspace` Objekt. In der Regel verwenden Sie Arbeitsbereiche, die implizit erstellt, wenn Sie öffnen ein [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt ohne Angabe eines Arbeitsbereichs oder beim Öffnen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt ohne Angabe eines Datenbankobjekts. MFC-DAO-Objekte, die auf diese Weise erstellter verwenden DAO Standard-Arbeitsbereich, das einmal erstellt und wiederverwendet wird.

Um einen Arbeitsbereich und die darin enthaltenen Objekte freizugeben, rufen Sie des Arbeitsbereichsobjekts [schließen](#close) Member-Funktion.

##  <a name="close"></a>  CDaoWorkspace::Close

Rufen Sie diese Memberfunktion, um die Workspace-Objekt zu schließen.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Schließen ein Objekt Öffnen des Arbeitsbereichs gibt das zugrunde liegende DAO-Objekt und der Arbeitsbereich ist ein Member der Auflistung Arbeitsbereiche aus der Auflistung entfernt. Aufrufen von `Close` guter Programmierung gilt.

> [!CAUTION]
>  Ein Workspace-Objekt schließen Schließt alle geöffneten Datenbanken im Arbeitsbereich. Dies führt alle geöffneten Recordsets in den Datenbanken, die ebenfalls geschlossen wird, und alle ausstehenden Änderungen oder Updates ein Rollback. Weitere Informationen finden Sie unter den [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close), [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close), und [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) Memberfunktionen.

Workspace-Objekte sind nicht dauerhaft; Sie sind nur vorhanden, während Verweise auf diese vorhanden sind. Dies bedeutet, dass wenn die Datenbank-Engine-Sitzung beendet wird, den Arbeitsbereich und der datenbankauflistung nicht beibehalten werden. Sie müssen sie erneut auf die nächste Sitzung erstellen, indem Sie Ihren Arbeitsbereich und die Datenbanken erneut zu öffnen.

Verwandte Informationen finden Sie im Thema "Close-Methode" in-DAO-Hilfe.

##  <a name="committrans"></a>  CDaoWorkspace::

Rufen Sie diese Memberfunktion zum commit einer Transaktion – eine Gruppe von Änderungen und Aktualisierungen auf eine oder mehrere Datenbanken in den Arbeitsbereich zu speichern.

```
void CommitTrans();
```

### <a name="remarks"></a>Hinweise

Eine Transaktion besteht aus einer Reihe von Änderungen an der Datenbank Daten oder der Struktur ab, die mit einem Aufruf von [BeginTrans](#begintrans). Nach Abschluss die Transaktion entweder commit noch Rollback (die Änderungen Abbrechen) mit [Rollback](#rollback). In der Standardeinstellung ohne Transaktionen sind Updates für Datensätze sofort ein Commit ausgeführt. Aufrufen von `BeginTrans` Engagement von Updates für die verzögert werden, bis der Aufruf führt dazu, dass `CommitTrans`.

> [!CAUTION]
>  In einem Arbeitsbereich Transaktionen sind immer global für den Arbeitsbereich und sind nicht nur eine Datenbank oder ein Recordset auf. Wenn Sie Vorgänge mit mehr als eine Datenbank oder ein Recordset in einer Arbeitsbereichstransaktion ausführen `CommitTrans` Commits alle ausstehenden Updates und `Rollback` stellt alle Vorgänge für diese Datenbanken und Recordsets.

Wenn Sie eine Datenbank oder ein Arbeitsbereichs mit ausstehenden Transaktionen schließen, werden die Transaktionen alle ein Rollback ausgeführt.

> [!NOTE]
>  Dies ist kein Zweiphasen-Commit-Mechanismus. Wenn ein Update ein Fehler auftritt, Commit, führt andere weiterhin einen commit.

##  <a name="compactdatabase"></a>  CDaoWorkspace:: CompactDatabase

Rufen Sie diese Memberfunktion zum Komprimieren einer angegebenen Microsoft Jet (. MDB)-Datenbank.

```
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,
    LPCTSTR lpszDestName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int nOptions = 0);


static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,
    LPCTSTR lpszDestName,
    LPCTSTR lpszLocale,
    int nOptions,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parameter

*lpszSrcName*<br/>
Der Name eines vorhandenen geschlossen Datenbank. Es kann sein ein vollständiger Pfad und Dateiname, z. B. "C:\\\MYDB. MDB". Wenn der Dateiname eine Erweiterung verfügt, müssen Sie es angeben. Wenn Ihr Netzwerk die einheitliche Benennungskonvention (UNC) unterstützt, können Sie auch angeben einen Netzwerkpfad wie z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelter umgekehrter Schrägstriche sind in den Pfadzeichenfolgen erforderlich, da "\\" ist der C++-Escape-Zeichen.)

*lpszDestName*<br/>
Der vollständige Pfad der komprimierten Datenbank, die Sie erstellen. Sie können auch angeben, einen Netzwerkpfad als mit *LpszSrcName*. Sie können keine der *LpszDestName* Argument an die gleiche Datenbankdatei als *LpszSrcName*.

*lpszPassword*<br/>
Ein Kennwort verwendet, wenn Sie eine kennwortgeschützte Datenbank komprimiert werden sollen. Beachten Sie, dass bei Verwendung die Version von `CompactDatabase` , ein Kennwort akzeptiert, müssen Sie alle Parameter angeben. Da dies eine Connect-Parameter ist, es erfordert auch spezielle Formatierung, wie folgt:; PWD = *LpszPassword*. Zum Beispiel:; PWD = "Zufrieden". (Das vorangestellte Semikolon ist erforderlich.)

*lpszLocale*<br/>
Ein Zeichenfolgenausdruck verwendet, um die Sortierreihenfolge für die Erstellung geben *LpszDestName*. Wenn Sie dieses Argument weglassen, durch das Akzeptieren des Standardwerts von `dbLangGeneral` (siehe unten), das Gebietsschema der neuen Datenbank wird mit der alten Datenbank identisch. Dabei sind folgende Werte möglich:

- `dbLangGeneral` Englisch, Deutsch, Französisch, Portugiesisch, Italienisch und moderne Spanisch

- `dbLangArabic` Arabisch

- `dbLangCyrillic` Russisch

- `dbLangCzech` Tschechisch

- `dbLangDutch` Holländisch

- `dbLangGreek` Griechisch

- `dbLangHebrew` Hebräisch

- `dbLangHungarian` Ungarisch

- `dbLangIcelandic` Isländisch

- `dbLangNordic` Nordeuropäische Sprachen (Microsoft Jet-Datenbank-Engine nur Version 1.0)

- `dbLangNorwdan` Norwegisch und Dänisch

- `dbLangPolish` Polnisch

- `dbLangSpanish` Spanisch (traditionell)

- `dbLangSwedfin` Tschechisch und Finnisch

- `dbLangTurkish` Türkisch

*nOptions*<br/>
Gibt eine oder mehrere Optionen für die Zieldatenbank *LpszDestName*. Wenn Sie dieses Argument weglassen, durch das Akzeptieren des Standardwert der *LpszDestName* hat dieselbe Verschlüsselung und die gleiche Version wie *LpszSrcName*. Sie können Kombinieren der `dbEncrypt` oder `dbDecrypt` Option mit einer der Version mit dem bitweisen OR-Operator. Mögliche Werte, die angeben, einem Datenbankformat, nicht in einer Datenbank-Engine-Version, sind:

- `dbEncrypt` Verschlüsseln Sie die Datenbank beim Komprimieren.

- `dbDecrypt` Entschlüsseln Sie die Datenbank beim Komprimieren.

- `dbVersion10` Erstellen Sie eine Datenbank, die beim Komprimieren das Microsoft Jet-Datenbank-Engine-Version 1.0 verwendet.

- `dbVersion11` Erstellen Sie eine Datenbank, die beim Komprimieren das Microsoft Jet-Datenbank-Engine-Version 1.1 verwendet.

- `dbVersion20` Erstellen Sie eine Datenbank, die beim Komprimieren das Microsoft Jet-Datenbank-Engine-Version 2.0 verwendet.

- `dbVersion30` Erstellen Sie eine Datenbank, die beim Komprimieren das Microsoft Jet-Datenbank-Engine-Version 3.0 verwendet.

Sie können `dbEncrypt` oder `dbDecrypt` im Optionsargument angeben, ob zum Verschlüsseln oder die Datenbank zu entschlüsseln, da diese komprimiert wird. Wenn Sie eine Verschlüsselungskonstante nicht angeben, oder wenn Sie beide Nummern aufnehmen `dbDecrypt` und `dbEncrypt`, *LpszDestName* müssen dieselbe Verschlüsselung wie *LpszSrcName*. Sie können eine der Konstanten Version im Optionsargument verwenden, um die Version des Datenformats für die komprimierte Datenbank anzugeben. Diese Konstante wirkt sich auf nur die Version des Datenformats der *LpszDestName*. Sie können nur eine Versionskonstante angeben. Wenn Sie eine Versionskonstante, weglassen *LpszDestName* müssen die gleiche Version wie *LpszSrcName*. Sie können komprimieren *LpszDestName* nur auf eine Version, die entspricht, oder höher als der *LpszSrcName*.

> [!CAUTION]
>  Wenn eine Datenbank nicht verschlüsselt ist, kann, auch wenn Sie Benutzername und Kennwort-Sicherheit implementieren, um direkt die binäre Datenträgerdatei lesen, aus der Datenbank besteht.

### <a name="remarks"></a>Hinweise

Wenn Sie Daten in einer Datenbank ändern, wird die Datenbankdatei kann fragmentiert werden, und verwenden mehr Speicherplatz als nötig. In regelmäßigen Abständen, sollten Sie Ihre Datenbank defragmentieren Sie die Datenbankdatei komprimieren. Die komprimierte Datenbank ist in der Regel kleiner. Sie können auch auswählen, um die Sortierreihenfolge, die Verschlüsselung oder die Version des Datenformats zu ändern, während Sie kopieren und komprimieren Sie die Datenbank.

> [!CAUTION]
>  Die `CompactDatabase` Memberfunktion wird nicht ordnungsgemäß konvertiert eine vollständige Microsoft Access-Datenbank von einer Version in einen anderen. Es wird nur das Datenformat konvertiert. Microsoft Access-Objekte, wie Formulare und Berichte, werden nicht konvertiert. Allerdings werden die Daten ordnungsgemäß konvertiert.

> [!TIP]
>  Sie können auch `CompactDatabase` zum Kopieren einer Datenbankdatei.

Weitere Informationen zum Komprimieren von Datenbanken finden Sie im Thema "CompactDatabase Method" in-DAO-Hilfe.

##  <a name="create"></a>  CDaoWorkspace:: Create

Rufen Sie diese Memberfunktion zum Erstellen eines neuen Objekts des DAO-Arbeitsbereich, und ordnen sie die MFC-Bibliothek `CDaoWorkspace` Objekt.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszUserName,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Eine Zeichenfolge mit bis zu 14 Zeichen, die der neue Arbeitsbereich-Objekt eindeutig bezeichnet. Sie müssen einen Namen angeben. Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

*lpszUserName*<br/>
Der Benutzername des Besitzers des Arbeitsbereichs. Voraussetzungen, finden Sie unter den *LpszDefaultUser* Parameter, um die [SetDefaultUser](#setdefaultuser) Member-Funktion. Weitere Informationen finden Sie unter dem Thema "UserName-Eigenschaft" in-DAO-Hilfe.

*lpszPassword*<br/>
Das Kennwort für das neue Workspace-Objekt. Ein Kennwort kann bis zu 14 Zeichen lang sein und darf Zeichen mit Ausnahme von ASCII 0 (null). Groß-und Kleinschreibung. Verwandte Informationen finden Sie im Thema "Password-Eigenschaft" in-DAO-Hilfe.

### <a name="remarks"></a>Hinweise

Der gesamte Erstellungsvorgang ist:

1. Erstellen einer [CDaoWorkspace](#cdaoworkspace) Objekt.

1. Aufrufen des Objekts `Create` Member-Funktion, um den zugrunde liegenden DAO-Arbeitsbereich zu erstellen. Geben Sie einen Arbeitsbereichsnamen ein.

1. Rufen Sie optional [Append](#append) , wenn Sie den Arbeitsbereich für die Datenbank-Engine-Arbeitsbereiche Sammlung hinzufügen möchten. Sie können mit dem Arbeitsbereich arbeiten, ohne es anzuhängen.

Nach der `Create` -Aufruf im Workspace-Objekt wird in einem geöffneten Zustand, der zur Verwendung bereit. Sie rufen nicht `Open` nach `Create`. Sie rufen nicht `Create` , wenn der Arbeitsbereich in der Auflistung der Arbeitsbereiche ist bereits vorhanden. `Create` Initialisiert die Datenbank-Engine an, wenn er noch nicht für Ihre Anwendung initialisiert wurde.

##  <a name="getdatabasecount"></a>  CDaoWorkspace::GetDatabaseCount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der DAO-Datenbankobjekte in der datenbankauflistung des Arbeitsbereichs – die Anzahl der geöffneten Datenbanken im Arbeitsbereich.

```
short GetDatabaseCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der geöffneten Datenbanken im Arbeitsbereich.

### <a name="remarks"></a>Hinweise

`GetDatabaseCount` ist nützlich, wenn Sie alle definierten Datenbanken in der datenbankauflistung des Arbeitsbereichs durchlaufen müssen. Um Informationen zu einer bestimmten Datenbank in der Auflistung zu erhalten, finden Sie unter [GetDatabaseInfo](#getdatabaseinfo). Typische Verwendung besteht darin, rufen Sie `GetDatabaseCount` für die Anzahl der geöffneten Datenbanken, klicken Sie dann verwenden Sie diese Zahl als eine Schleifenindex für wiederholte Aufrufe von `GetDatabaseInfo`.

##  <a name="getdatabaseinfo"></a>  CDaoWorkspace::GetDatabaseInfo

Rufen Sie diese Memberfunktion, um verschiedene Arten von Informationen über eine Datenbank geöffnet, in dem Arbeitsbereich zu erhalten.

```
void GetDatabaseInfo(
    int nIndex,
    CDaoDatabaseInfo& dbinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);


void GetDatabaseInfo(
    LPCTSTR lpszName,
    CDaoDatabaseInfo& dbinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der nullbasierte Index des Datenbankobjekts in der datenbankauflistung des Arbeitsbereichs, für die Suche nach Index.

*dbinfo*<br/>
Ein Verweis auf eine [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.

*dwInfoOptions*<br/>
Optionen, die angeben, welche Informationen über die Datenbank abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:

- AFX_DAO_PRIMARY_INFO (Standard) Namen aktualisiert werden kann, Transaktionen

- Primäre AFX_DAO_SECONDARY_INFO Informationen plus: Abfragetimeout Version Reihenfolge sortieren

- AFX_DAO_ALL_INFO primären und sekundären Informationen plus: Verbinden

*Wert*<br/>
Der Name des Datenbankobjekts, für die Suche anhand des Namens. Der Name ist eine Zeichenfolge mit bis zu 14 Zeichen, die der neue Arbeitsbereich-Objekt eindeutig bezeichnet.

### <a name="remarks"></a>Hinweise

Eine Version der Funktion können Sie eine Datenbank über einen Index zu suchen. Die andere Version können Sie eine Datenbank anhand des Namens zu suchen.

Eine Beschreibung der Informationen in zurückgegebenen *Dbinfo*, finden Sie unter den [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.

##  <a name="getinipath"></a>  CDaoWorkspace::GetIniPath

Rufen Sie diese Memberfunktion um den Speicherort der Microsoft Jet-Datenbank-Engine-Initialisierung-Einstellungen in der Windows-Registrierung abzurufen.

```
static CString PASCAL GetIniPath();
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der am Registrierungsspeicherort enthält.

### <a name="remarks"></a>Hinweise

Sie können den Speicherort zum Abrufen von Informationen zu Einstellungen für die Datenbank-Engine verwenden. Die zurückgegebenen Informationen ist tatsächlich auf den Namen der Unterschlüssel der Registrierung.

Weitere Informationen finden Sie unter den Themen "IniPath Property" und "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" in-DAO-Hilfe.

##  <a name="getisolateodbctrans"></a>  CDaoWorkspace::GetIsolateODBCTrans

Rufen Sie diese Memberfunktion um den aktuellen Wert der Eigenschaft DAO IsolateODBCTrans für den Arbeitsbereich zu erhalten.

```
BOOL GetIsolateODBCTrans();
```

### <a name="return-value"></a>Rückgabewert

Legen Sie ungleich NULL, wenn es sich bei ODBC-Transaktionen isoliert sind; andernfalls 0.

### <a name="remarks"></a>Hinweise

In einigen Situationen müssen Sie mehrere gleichzeitige Transaktionen mit ausstehender für eine ODBC-Datenbank haben. Zu diesem Zweck müssen Sie einen separaten Arbeitsbereich für jede Transaktion zu öffnen. Bedenken Sie, dass zwar jeden Arbeitsbereich eine eigene ODBC-Verbindung mit der Datenbank verfügen kann, dies die Systemleistung verlangsamt. Da der Transaktionsisolation nicht normal erforderlich ist, werden die ODBC-Verbindungen von mehreren Workspace-Objekte, die vom gleichen Benutzer geöffnet standardmäßig freigegeben.

Einige ODBC-Server, z. B. Microsoft SQL Server zulassen nicht gleichzeitige Transaktionen auf eine einzelne Verbindung. Wenn Sie mehr als eine Transaktion zu einem Zeitpunkt steht aus für eine Datenbank verfügen müssen, legen Sie die IsolateODBCTrans-Eigenschaft auf "true" für jeden Arbeitsbereich, sobald Sie es öffnen. Dies erzwingt, dass eine separate ODBC-Verbindung für jeden Arbeitsbereich.

Verwandte Informationen finden Sie im Thema "IsolateODBCTrans-Eigenschaft" in-DAO-Hilfe.

##  <a name="getlogintimeout"></a>  CDaoWorkspace::GetLoginTimeout

Rufen Sie diese Memberfunktion um den aktuellen Wert der DAO-LoginTimeout-Eigenschaft für den Arbeitsbereich zu erhalten.

```
static short PASCAL GetLoginTimeout();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, eine ODBC-Datenbank anmelden.

### <a name="remarks"></a>Hinweise

Dieser Wert stellt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, eine ODBC-Datenbank anmelden. Die Standardeinstellung für das Anmeldungstimeout beträgt 20 Sekunden. Beim Anmeldungstimeout auf 0 festgelegt ist, wird kein Timeout erfolgt, und die Kommunikation mit der Datenquelle reagiert möglicherweise nicht.

Wenn Sie versuchen, die mit einer ODBC-Datenbank, z. B. Microsoft SQL Server, melden Sie sich möglicherweise die Verbindung aufgrund von Netzwerkfehlern oder weil der Server nicht ausgeführt wird. Anstatt zu warten, der Standardwert 20 Sekunden eine Verbindung herstellen, können Sie angeben, wie lange die Datenbank-Engine wartet, bevor er einen Fehler erzeugt. Anmeldung mit dem Server wird implizit als Teil einer Reihe verschiedener Ereignisse, wie z. B. das Ausführen einer Abfrage in einer externen Server-Datenbank.

Verwandte Informationen finden Sie im Thema "LoginTimeout-Eigenschaft" in-DAO-Hilfe.

##  <a name="getname"></a>  CDaoWorkspace::GetName

Rufen Sie diese Memberfunktion zum Abrufen des benutzerdefinierten Namens der DAO-Workspace-Objekt zugrunde liegenden der `CDaoWorkspace` Objekt.

```
CString GetName();
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) mit dem benutzerdefinierten Namen des DAO-Workspace-Objekts.

### <a name="remarks"></a>Hinweise

Der Name ist nützlich für den Zugriff auf die DAO-Workspace-Objekt in der Datenbank-Engine-arbeitsbereicheauflistung nach Namen.

Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

##  <a name="getusername"></a>  CDaoWorkspace::GetUserName

Rufen Sie diese Memberfunktion zum Abrufen des Namens des Besitzers des Arbeitsbereichs.

```
CString GetUserName();
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , das den Besitzer des Workspace-Objekts darstellt.

### <a name="remarks"></a>Hinweise

Rufen Sie zum Abrufen oder Festlegen der Berechtigungen für Besitzer des Arbeitsbereichs, DAO direkt, um die Einstellung der Eigenschaft Berechtigungen zu überprüfen. Dadurch wird bestimmt, welche Berechtigungen dieser Benutzer besitzt. Um mit den Berechtigungen zu arbeiten, benötigen Sie ein SYSTEM aus. MDA-Datei.

Informationen zum Aufrufen von DAO direkt finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md). Weitere Informationen finden Sie unter dem Thema "UserName-Eigenschaft" in-DAO-Hilfe.

##  <a name="getversion"></a>  CDaoWorkspace::GetVersion

Rufen Sie diese Memberfunktion zum Ermitteln der Version von Microsoft Jet-Datenbank-Engine verwendet.

```
static CString PASCAL GetVersion();
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der die Version der Datenbank-Engine, die mit dem Objekt verbundenen angibt.

### <a name="remarks"></a>Hinweise

Der zurückgegebene Wert stellt die Versionsnummer im Format "Hauptversion.Nebenversion"; z. B. "3.0". Die Versionsnummer des Produkts (z. B. "3.0") besteht aus der Versionsnummer (3), einem Punkt und die Versionsnummer (0).

Verwandte Informationen finden Sie im Thema "Version-Eigenschaft" in-DAO-Hilfe.

##  <a name="getworkspacecount"></a>  CDaoWorkspace::GetWorkspaceCount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der DAO-Workspace-Objekte in der Datenbank-Engine-Arbeitsbereiche-Auflistung.

```
short GetWorkspaceCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der geöffneten Arbeitsbereiche in der Auflistung der Arbeitsbereiche.

### <a name="remarks"></a>Hinweise

Diese Zahl umfasst keine öffnen Arbeitsbereiche nicht auf die Auflistung angefügt. `GetWorkspaceCount` ist nützlich, wenn Sie alle definierten Arbeitsbereiche in der Auflistung der Arbeitsbereiche durchlaufen müssen. Um Informationen zu einem bestimmten Arbeitsbereich in der Auflistung zu erhalten, finden Sie unter [GetWorkspaceInfo](#getworkspaceinfo). Typische Verwendung besteht darin, rufen Sie `GetWorkspaceCount` für die Anzahl der geöffneten Arbeitsbereiche, klicken Sie dann verwenden Sie diese Zahl als eine Schleifenindex für wiederholte Aufrufe von `GetWorkspaceInfo`.

##  <a name="getworkspaceinfo"></a>  CDaoWorkspace::GetWorkspaceInfo

Rufen Sie diese Memberfunktion, um verschiedene Arten von Informationen über einen Arbeitsbereich öffnen, in der Sitzung zu erhalten.

```
void GetWorkspaceInfo(
    int nIndex,
    CDaoWorkspaceInfo& wkspcinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);


void GetWorkspaceInfo(
    LPCTSTR lpszName,
    CDaoWorkspaceInfo& wkspcinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der nullbasierte Index des Datenbankobjekts in der Auflistung Arbeitsbereiche für die Suche nach Index.

*wkspcinfo*<br/>
Ein Verweis auf eine [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.

*dwInfoOptions*<br/>
Optionen, die angeben, welche Informationen über den Arbeitsbereich abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:

- Name der AFX_DAO_PRIMARY_INFO (Standard)

- Primäre AFX_DAO_SECONDARY_INFO Informationen plus: Benutzername

- AFX_DAO_ALL_INFO primären und sekundären Informationen plus: ODBCTrans zu isolieren

*Wert*<br/>
Der Name des Workspace-Objekts, für die Suche anhand des Namens. Der Name ist eine Zeichenfolge mit bis zu 14 Zeichen, die der neue Arbeitsbereich-Objekt eindeutig bezeichnet.

### <a name="remarks"></a>Hinweise

Eine Beschreibung der Informationen in zurückgegebenen *Wkspcinfo*, finden Sie unter den [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen zu vorherigen Ebenen sowie an.

##  <a name="idle"></a>  CDaoWorkspace::Idle

Rufen Sie `Idle` bereitstellen, die Datenbank-Engine die Möglichkeit zum Ausführen von Hintergrundaufgaben, die aufgrund von intensiver Datenverarbeitung möglicherweise nicht auf dem neuesten Stand.

```
static void PASCAL Idle(int nAction = dbFreeLocks);
```

### <a name="parameters"></a>Parameter

*nDie Aktion wurde*<br/>
Aktion bei der Verarbeitung im Leerlauf ausgeführt werden soll. Derzeit die einzige gültige Aktion ist `dbFreeLocks`.

### <a name="remarks"></a>Hinweise

Dies ist häufig in mehreren Benutzern, Multitasking-Umgebungen, in dem ist nicht genügend Hintergrundverarbeitungszeit, um alle Datensätze in einem Recordset aktuell zu halten.

> [!NOTE]
>  Aufrufen von `Idle` muss nicht mit Datenbanken, die in Version 3.0 der Microsoft Jet-Datenbank-Engine erstellt wurden. Verwendung `Idle` nur für Datenbanken, die mit früheren Versionen erstellt wurden.

In der Regel wird lesen, Sperren entfernt werden, und Daten im lokalen Dynaset eines assistentartigen Recordset-Objekte nur aktualisiert, wenn keine anderen Aktionen (einschließlich mausbewegungen) auftreten. Wenn Sie in regelmäßigen Abständen Aufrufen `Idle`, Sie geben Sie die Datenbank-Engine, mit der Zeit auf Verarbeitungsaufgaben durch die Freigabe von Hintergrund aufholen nicht benötigte Sperren zu lesen. Angeben der `dbFreeLocks` Konstante als Argument verzögert verarbeitet werden, bevor alle Lesesperren freigegeben werden.

Diese Memberfunktion ist in Umgebungen mit nur einem Benutzer nicht erforderlich, es sei denn, die mehrere Instanzen einer Anwendung ausgeführt werden. Die `Idle` Memberfunktion kann Leistung in einer mehrbenutzerumgebung erhöhen, da die Datenbank-Engine beim Leeren von Daten auf den Datenträger, die Freigabe von Sperren für den Arbeitsspeicher wird erzwungen. Sie können auch Lesesperren freigeben, dazu die Vorgängen Teil einer Transaktion.

Verwandte Informationen finden Sie im Thema "Im Leerlauf Method" in-DAO-Hilfe.

##  <a name="isopen"></a>  CDaoWorkspace::IsOpen

Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoWorkspace` -Objekts geöffnet ist, d. h., ob das MFC-Objekt durch einen Aufruf initialisiert wurde [öffnen](#open) oder einen Aufruf von [erstellen](#create).

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Workspace-Objekt geöffnet ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie können keine der Memberfunktionen Funktionen eines Arbeitsbereichs aufrufen, die im geöffneten Zustand ist.

##  <a name="m_pdaoworkspace"></a>  CDaoWorkspace::m_pDAOWorkspace

Ein Zeiger auf das zugrunde liegende DAO-Workspace-Objekt.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Datenelement aus, wenn Sie den Zugriff auf das zugrunde liegende DAO-Objekt weiterleiten müssen. Sie können die DAO-Schnittstellen des Objekts über diesen Zeiger aufrufen.

Weitere Informationen zu den direkten Zugriff auf DAO-Objekte, finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

##  <a name="open"></a>  CDaoWorkspace::Open

Explizit öffnet ein Workspace-Objekt, das mit DAO Standard-Arbeitsbereich verknüpft ist.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Der Name des Objekts die DAO-Arbeitsbereich zu öffnen, eine Zeichenfolge mit bis zu 14 Zeichen, die den Arbeitsbereich eindeutig bezeichnet. Akzeptieren Sie den Standardwert NULL, um die Standard-Arbeitsbereich explizit zu öffnen. Für die Benennung von Anforderungen, finden Sie unter den *Wert* -Parameter für [erstellen](#create). Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

### <a name="remarks"></a>Hinweise

Nach dem Erstellen einer `CDaoWorkspace` Objekt, das mit dieser Memberfunktion können Sie eine der folgenden Aktionen ausführen:

- Öffnen Sie explizit die Standard-Arbeitsbereich. Übergeben Sie NULL für *Wert*.

- Öffnen Sie eine vorhandene `CDaoWorkspace` -Objekt, das ein Mitglied der Auflistung Arbeitsbereiche nach Namen. Übergeben Sie einen gültigen Namen für ein vorhandenes Workspace-Objekt.

`Open` die Workspace-Objekt in einem geöffneten Zustand versetzt, und auch die Datenbank-Engine initialisiert, wenn er noch nicht für Ihre Anwendung initialisiert wurde.

Obwohl viele `CDaoWorkspace` Member Funktionen können nur aufgerufen werden, nachdem der Arbeitsbereich geöffnet wurde, die folgenden Memberfunktionen, die auf die Datenbank-Engine angewendet werden, stehen nach der Erstellung der C++-Objekt, aber vor einem Aufruf von `Open`:

||||
|-|-|-|
|[Erstellen](#create)|["GetVersion"](#getversion)|[SetDefaultUser](#setdefaultuser)|
|[GetIniPath](#getinipath)|[Im Leerlauf](#idle)|[SetIniPath](#setinipath)|
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|

##  <a name="repairdatabase"></a>  CDaoWorkspace::RepairDatabase

Rufen Sie diese Memberfunktion auf, wenn Sie versuchen, eine beschädigte Datenbank zu reparieren, die auf die Microsoft Jet-Datenbank-Engine zugreift müssen.

```
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Der Pfad und Dateiname für eine vorhandene Microsoft Jet-Engine Datenbankdatei. Wenn Sie den Pfad weglassen, wird nur das aktuelle Verzeichnis durchsucht. Wenn Ihr System die einheitliche Benennungskonvention (UNC) unterstützt, können Sie auch angeben einen Netzwerkpfad wie z. B.: "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelter umgekehrter Schrägstriche sind in der Path-Zeichenfolge erforderlich, da "\\" ist der C++-Escape-Zeichen.)

### <a name="remarks"></a>Hinweise

Sie müssen durch den angegebenen Datenbank schließen *Wert* vor einer Reparatur. In einer mehrbenutzerumgebung, anderen Benutzern keine *Wert* öffnen, während Sie sie reparieren. Wenn *Wert* ist nicht geschlossen oder ist nicht verfügbar für die ausschließliche Verwendung ein Fehler auftritt.

Diese Memberfunktion versucht, eine Datenbank zu reparieren, die von einer unvollständigen Schreibvorgang als möglicherweise fehlerhaft gekennzeichnet wurde. Dies kann auftreten, wenn eine Anwendung mithilfe der Microsoft Jet-Datenbank-Engine aufgrund eines Problems Power Netzwerkausfall oder einem Hardware unerwartet geschlossen ist. Wenn Sie den Vorgang und der Aufruf abgeschlossen. die [schließen](../../mfc/reference/cdaodatabase-class.md#close) Memberfunktion oder beenden Sie die Anwendung auf eine übliche Weise, die Datenbank wird nicht als möglicherweise fehlerhaft gekennzeichnet werden.

> [!NOTE]
>  Reparieren Sie eine Datenbank, und es ist auch eine gute Idee, komprimieren Sie sie mithilfe der [CompactDatabase](#compactdatabase) Member-Funktion, um die Datei zu defragmentieren und Speicherplatz zu gewinnen.

Weitere Informationen zum Reparieren von Datenbanken finden Sie im Thema "RepairDatabase Method" in-DAO-Hilfe.

##  <a name="rollback"></a>  CDaoWorkspace::Rollback

Rufen Sie diese Memberfunktion, um die aktuelle Transaktion zu beenden und alle Datenbanken in den Arbeitsbereich in ihren Zustand wiederherstellen, bevor die Transaktion gestartet wurde.

```
void Rollback();
```

### <a name="remarks"></a>Hinweise

> [!CAUTION]
>  In einem Arbeitsbereichsobjekt Transaktionen sind immer global für den Arbeitsbereich und sind nicht nur eine Datenbank oder ein Recordset auf. Wenn Sie Vorgänge mit mehr als eine Datenbank oder ein Recordset in einer Arbeitsbereichstransaktion ausführen `Rollback` stellt alle Vorgänge für alle diese Datenbanken und Recordsets.

Wenn Sie ein Workspace-Objekt schließen, ohne zu speichern oder ein Rollback aller anstehenden Transaktionen, werden die Transaktionen automatisch zurückgesetzt. Wenn Sie aufrufen [CommitTrans](#committrans) oder `Rollback` erst nach Aufrufen von [BeginTrans](#begintrans), ein Fehler auftritt.

> [!NOTE]
>  Wenn Sie eine Transaktion starten, zeichnet die Datenbank-Engine die Vorgänge in einer Datei, in dem durch die Umgebungsvariable "TEMP" auf der Arbeitsstation angegebenen Verzeichnis gespeichert. Wenn die Transaktionsprotokolldatei auf Ihrem TEMPORÄREN Laufwerk den verfügbaren Speicher ausgeschöpft hat, die Datenbank-Engine wird dazu führen, dass MFC Auslösen einer `CDaoException` (DAO-Fehler, 2004). An diesem Punkt, wenn Sie aufrufen `CommitTrans`, eine unbestimmte Anzahl von Vorgängen werden jedoch die verbleibenden nicht abgeschlossenen Vorgänge verloren, und der Vorgang muss neu gestartet werden. Aufrufen von `Rollback` gibt das Transaktionsprotokoll und ein Rollback für alle Vorgänge aus, in der Transaktion.

##  <a name="setdefaultpassword"></a>  CDaoWorkspace::SetDefaultPassword

Rufen Sie diese Memberfunktion, um das Standardkennwort festzulegen, das die Datenbank-Engine verwendet wird, wenn ein Workspace-Objekt ohne ein bestimmtes Kennwort erstellt wird.

```
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parameter

*lpszPassword*<br/>
Das Standardkennwort. Ein Kennwort kann bis zu 14 Zeichen lang sein und darf Zeichen mit Ausnahme von ASCII 0 (null). Groß-und Kleinschreibung.

### <a name="remarks"></a>Hinweise

Das Standardkennwort, das Sie festlegen, gilt für neue Arbeitsbereiche, die Sie nach dem Aufruf zu erstellen. Wenn Sie die nachfolgenden Arbeitsbereiche erstellen, müssen Sie nicht angeben ein Kennworts in der [erstellen](#create) aufrufen.

So verwenden Sie diese Memberfunktion auf:

1. Erstellen einer `CDaoWorkspace` Objekt rufen Sie jedoch nicht `Create`.

1. Rufen Sie `SetDefaultPassword` und, falls gewünscht, [SetDefaultUser](#setdefaultuser).

1. Rufen Sie `Create` für dieses Arbeitsbereichsobjekt oder alle weiteren, ohne Angabe eines Kennworts.

In der Standardeinstellung die DefaultUser-Eigenschaft auf "Admin" festgelegt ist und die Eigenschaft "DefaultPassword" auf eine leere Zeichenfolge festgelegt ist ("").

Weitere Informationen zur Sicherheit finden Sie im Thema "Berechtigungen Property" in-DAO-Hilfe. Weitere Informationen finden Sie unter den Themen "DefaultPassword Property" und "DefaultUser-Eigenschaft" in-DAO-Hilfe.

##  <a name="setdefaultuser"></a>  CDaoWorkspace::SetDefaultUser

Rufen Sie diese Memberfunktion um den Standardnamen für den Benutzer festzulegen, den die Datenbank-Engine verwendet wird, wenn ein Workspace-Objekt ohne einen bestimmten Benutzernamen erstellt wird.

```
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```

### <a name="parameters"></a>Parameter

*lpszDefaultUser*<br/>
Der Standardbenutzername. Ein Benutzernamen kann 1 bis 20 Zeichen lang sein und sind Buchstaben, Sonderzeichen, Zahlen, Leerzeichen und Symbole mit Ausnahme von: "(Anführungszeichen) / (Schrägstrich), \ (umgekehrter Schrägstrich), \[ \] (Klammern): (Doppelpunkt), &#124; () senkrechter Strich), \< (kleiner-als-Zeichen), > (größer-als-Zeichen), + (Pluszeichen), = (Gleichheitszeichen), Semikolon (;), (Komma), (Fragezeichen), \* (Sternchen), führende Leerzeichen und Steuerzeichen (ASCII 00 und ASCII-31). Weitere Informationen finden Sie unter dem Thema "UserName-Eigenschaft" in-DAO-Hilfe.

### <a name="remarks"></a>Hinweise

Der Standardname für den Benutzer, die Sie festlegen, gilt für neue Arbeitsbereiche, die Sie nach dem Aufruf zu erstellen. Wenn Sie die nachfolgenden Arbeitsbereiche erstellen, müssen Sie keinen Benutzernamen im Angeben der [erstellen](#create) aufrufen.

So verwenden Sie diese Memberfunktion auf:

1. Erstellen einer `CDaoWorkspace` Objekt rufen Sie jedoch nicht `Create`.

1. Rufen Sie `SetDefaultUser` und, falls gewünscht, [SetDefaultPassword](#setdefaultpassword).

1. Rufen Sie `Create` für dieses Arbeitsbereichsobjekt oder alle weiteren, ohne einen Benutzernamen anzugeben.

In der Standardeinstellung die DefaultUser-Eigenschaft auf "Admin" festgelegt ist und die Eigenschaft "DefaultPassword" auf eine leere Zeichenfolge festgelegt ist ("").

Weitere Informationen finden Sie unter den Themen "DefaultUser Property" und "DefaultPassword-Eigenschaft" in-DAO-Hilfe.

##  <a name="setinipath"></a>  CDaoWorkspace::SetIniPath

Rufen Sie diese Memberfunktion zum Angeben des Speicherorts der Windows-registrierungseinstellungen für das Microsoft Jet-Datenbankmodul.

```
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```

### <a name="parameters"></a>Parameter

*lpszRegistrySubkey*<br/>
Eine Zeichenfolge, die mit dem Namen der einen Windows-Registrierungsunterschlüssel für den Speicherort der Einstellungen für Microsoft Jet-Datenbank-Engine oder für installierbare ISAM-Datenbanken erforderlichen Parameter.

### <a name="remarks"></a>Hinweise

Rufen Sie `SetIniPath` nur, wenn Sie spezielle Einstellungen angeben möchten. Weitere Informationen finden Sie im Thema "IniPath-Eigenschaft" in-DAO-Hilfe.

> [!NOTE]
>  Rufen Sie `SetIniPath` während der Anwendungsinstallation, nicht wenn die Anwendung ausgeführt wird. `SetIniPath` muss aufgerufen werden, bevor Sie alle Arbeitsbereiche, Datenbanken oder Recordsets öffnen. Andernfalls löst MFC eine Ausnahme aus.

Sie können diesen Mechanismus verwenden, auf die Datenbank-Engine mit vom Benutzer bereitgestellte registrierungseinstellungen konfigurieren zu können. Der Gültigkeitsbereich dieses Attributs ist Ihre Anwendung auf und kann nicht geändert werden, ohne Ihre Anwendung neu zu starten.

##  <a name="setisolateodbctrans"></a>  CDaoWorkspace::SetIsolateODBCTrans

Rufen Sie diese Memberfunktion um den Wert der Eigenschaft DAO IsolateODBCTrans für den Arbeitsbereich festzulegen.

```
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```

### <a name="parameters"></a>Parameter

*bIsolateODBCTrans*<br/>
Übergeben Sie "true", sollten Sie beginnen, Isolieren von ODBC-Transaktionen. Übergeben Sie "false", sollten Sie isolieren ODBC-Transaktionen zu beenden.

### <a name="remarks"></a>Hinweise

In einigen Situationen müssen Sie mehrere gleichzeitige Transaktionen mit ausstehender für eine ODBC-Datenbank haben. Zu diesem Zweck müssen Sie einen separaten Arbeitsbereich für jede Transaktion zu öffnen. Obwohl jeder Arbeitsbereich eine eigene ODBC-Verbindung mit der Datenbank verfügen kann, wird dadurch die Leistung des Systems. Da der Transaktionsisolation nicht normal erforderlich ist, werden die ODBC-Verbindungen von mehreren Workspace-Objekte, die vom gleichen Benutzer geöffnet standardmäßig freigegeben.

Einige ODBC-Server, z. B. Microsoft SQL Server zulassen nicht gleichzeitige Transaktionen auf eine einzelne Verbindung. Wenn Sie mehr als eine Transaktion zu einem Zeitpunkt steht aus für eine Datenbank verfügen müssen, legen Sie die IsolateODBCTrans-Eigenschaft auf "true" für jeden Arbeitsbereich, sobald Sie es öffnen. Dies erzwingt, dass eine separate ODBC-Verbindung für jeden Arbeitsbereich.

##  <a name="setlogintimeout"></a>  CDaoWorkspace::SetLoginTimeout

Rufen Sie diese Memberfunktion um den Wert der DAO-LoginTimeout-Eigenschaft für den Arbeitsbereich festzulegen.

```
static void PASCAL SetLoginTimeout(short nSeconds);
```

### <a name="parameters"></a>Parameter

*nSeconds*<br/>
Die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, eine ODBC-Datenbank anmelden.

### <a name="remarks"></a>Hinweise

Dieser Wert stellt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, eine ODBC-Datenbank anmelden. Die Standardeinstellung für das Anmeldungstimeout beträgt 20 Sekunden. Beim Anmeldungstimeout auf 0 festgelegt ist, wird kein Timeout erfolgt, und die Kommunikation mit der Datenquelle reagiert möglicherweise nicht.

Wenn Sie versuchen, die mit einer ODBC-Datenbank, z. B. Microsoft SQL Server, melden Sie sich möglicherweise die Verbindung aufgrund von Netzwerkfehlern oder weil der Server nicht ausgeführt wird. Anstatt zu warten, der Standardwert 20 Sekunden eine Verbindung herstellen, können Sie angeben, wie lange die Datenbank-Engine wartet, bevor er einen Fehler erzeugt. Anmelden an den Server wird implizit als Teil einer Reihe verschiedener Ereignisse, wie z. B. das Ausführen einer Abfrage in einer externen Server-Datenbank. Der Timeoutwert wird durch die aktuelle Einstellung der LoginTimeout-Eigenschaft bestimmt.

Verwandte Informationen finden Sie im Thema "LoginTimeout-Eigenschaft" in-DAO-Hilfe.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
