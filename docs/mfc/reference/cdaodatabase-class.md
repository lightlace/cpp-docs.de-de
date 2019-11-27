---
title: CDaoDatabase-Klasse
ms.date: 09/17/2019
f1_keywords:
- CDaoDatabase
- AFXDAO/CDaoDatabase
- AFXDAO/CDaoDatabase::CDaoDatabase
- AFXDAO/CDaoDatabase::CanTransact
- AFXDAO/CDaoDatabase::CanUpdate
- AFXDAO/CDaoDatabase::Close
- AFXDAO/CDaoDatabase::Create
- AFXDAO/CDaoDatabase::CreateRelation
- AFXDAO/CDaoDatabase::DeleteQueryDef
- AFXDAO/CDaoDatabase::DeleteRelation
- AFXDAO/CDaoDatabase::DeleteTableDef
- AFXDAO/CDaoDatabase::Execute
- AFXDAO/CDaoDatabase::GetConnect
- AFXDAO/CDaoDatabase::GetName
- AFXDAO/CDaoDatabase::GetQueryDefCount
- AFXDAO/CDaoDatabase::GetQueryDefInfo
- AFXDAO/CDaoDatabase::GetQueryTimeout
- AFXDAO/CDaoDatabase::GetRecordsAffected
- AFXDAO/CDaoDatabase::GetRelationCount
- AFXDAO/CDaoDatabase::GetRelationInfo
- AFXDAO/CDaoDatabase::GetTableDefCount
- AFXDAO/CDaoDatabase::GetTableDefInfo
- AFXDAO/CDaoDatabase::GetVersion
- AFXDAO/CDaoDatabase::IsOpen
- AFXDAO/CDaoDatabase::Open
- AFXDAO/CDaoDatabase::SetQueryTimeout
- AFXDAO/CDaoDatabase::m_pDAODatabase
- AFXDAO/CDaoDatabase::m_pWorkspace
helpviewer_keywords:
- CDaoDatabase [MFC], CDaoDatabase
- CDaoDatabase [MFC], CanTransact
- CDaoDatabase [MFC], CanUpdate
- CDaoDatabase [MFC], Close
- CDaoDatabase [MFC], Create
- CDaoDatabase [MFC], CreateRelation
- CDaoDatabase [MFC], DeleteQueryDef
- CDaoDatabase [MFC], DeleteRelation
- CDaoDatabase [MFC], DeleteTableDef
- CDaoDatabase [MFC], Execute
- CDaoDatabase [MFC], GetConnect
- CDaoDatabase [MFC], GetName
- CDaoDatabase [MFC], GetQueryDefCount
- CDaoDatabase [MFC], GetQueryDefInfo
- CDaoDatabase [MFC], GetQueryTimeout
- CDaoDatabase [MFC], GetRecordsAffected
- CDaoDatabase [MFC], GetRelationCount
- CDaoDatabase [MFC], GetRelationInfo
- CDaoDatabase [MFC], GetTableDefCount
- CDaoDatabase [MFC], GetTableDefInfo
- CDaoDatabase [MFC], GetVersion
- CDaoDatabase [MFC], IsOpen
- CDaoDatabase [MFC], Open
- CDaoDatabase [MFC], SetQueryTimeout
- CDaoDatabase [MFC], m_pDAODatabase
- CDaoDatabase [MFC], m_pWorkspace
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
ms.openlocfilehash: 4c594b1ddfc1464417506557bb8743c4979be677
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304292"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase-Klasse

Stellt eine Verbindung mit einer Access-Datenbank mithilfe von Data Access Objects (DAO) dar. DAO wird über Office 2013 unterstützt. DAO 3,6 ist die endgültige Version, die als veraltet eingestuft wird.

## <a name="syntax"></a>Syntax

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDaoDatabase:: CDaoDatabase](#cdaodatabase)|Erstellt ein `CDaoDatabase`-Objekt. Ruft `Open` auf, um das Objekt mit einer Datenbank zu verbinden.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDaoDatabase:: CanTransact](#cantransact)|Gibt, die ungleich NULL, wenn die Datenbank Transaktionen unterstützt.|
|[CDaoDatabase:: CanUpdate](#canupdate)|Gibt einen Wert ungleich 0 (null) zurück, wenn das `CDaoDatabase` Objekt aktualisierbar ist (nicht schreibgeschützt).|
|[CDaoDatabase:: Close](#close)|Beendet die datenbankverbindung an.|
|[CDaoDatabase:: Create](#create)|Erstellt das zugrunde liegende DAO-Datenbankobjekt und initialisiert das `CDaoDatabase`-Objekt.|
|[CDaoDatabase:: up](#createrelation)|Definiert eine neue Beziehung zwischen den Tabellen in der Datenbank an.|
|[CDaoDatabase::D eletequerydef](#deletequerydef)|Löscht ein Querydef-Objekt, das in der Datenbank QueryDefs-Auflistung gespeichert.|
|[CDaoDatabase::D eleterelierung](#deleterelation)|Löscht eine vorhandene Beziehung zwischen Tabellen in der Datenbank an.|
|[CDaoDatabase::D eletetabledef](#deletetabledef)|Löscht die Definition einer Tabelle in der Datenbank. Dadurch werden die tatsächliche Tabelle und alle zugehörigen Daten gelöscht.|
|[CDaoDatabase:: Execute](#execute)|Führt eine Abfrage an. Wenn Sie `Execute` für eine Abfrage aufrufen, die Ergebnisse zurückgibt, wird eine Ausnahme ausgelöst.|
|[CDaoDatabase:: GetConnect](#getconnect)|Gibt die Verbindungs Zeichenfolge zurück, mit der das `CDaoDatabase`-Objekt mit einer Datenbank verbunden wird. Für ODBC verwendet.|
|[CDaoDatabase:: GetName](#getname)|Gibt den Namen der Datenbank, die zurzeit verwendeten zurück.|
|[CDaoDatabase:: getquerydefcount](#getquerydefcount)|Gibt die Anzahl von Abfragen, die für die Datenbank definiert.|
|[CDaoDatabase:: GetQueryDefInfo](#getquerydefinfo)|Gibt Informationen zu einer angegebenen Abfrage, die in der Datenbank definiert.|
|[CDaoDatabase:: getquerytimeout](#getquerytimeout)|Gibt die Anzahl der Sekunden zurück, nach denen ein Timeout bei Datenbankabfrage Vorgängen auftritt. Wirkt sich auf alle nachfolgenden geöffneten, neuen, Aktualisierungs-und Bearbeitungsvorgänge und andere Vorgänge für ODBC-Datenquellen (nur) wie `Execute` Aufrufe aus.|
|[CDaoDatabase:: getrecordsafffiziert](#getrecordsaffected)|Gibt die Anzahl der Datensätze zurück, die vom letzten Update-, Bearbeitungs-oder Add-Vorgang oder durch einen `Execute`aufrufsvorgang betroffen sind.|
|[CDaoDatabase:: getrelationcount](#getrelationcount)|Gibt die Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.|
|[CDaoDatabase:: getrelationinfo](#getrelationinfo)|Gibt Informationen zu einer angegebenen Beziehung zwischen Tabellen in der Datenbank definiert.|
|[CDaoDatabase:: GetTableDefCount](#gettabledefcount)|Gibt die Anzahl der in der Datenbank definierten Tabellen zurück.|
|[CDaoDatabase:: GetTableDefInfo](#gettabledefinfo)|Informationen zu einer angegebenen Tabelle zurückgegeben in der Datenbank.|
|[CDaoDatabase:: GetVersion](#getversion)|Gibt die Version der Datenbank-Engine, die der Datenbank zugeordnet.|
|[CDaoDatabase:: IsOpen](#isopen)|Gibt einen Wert ungleich 0 (null) zurück, wenn das `CDaoDatabase` Objekt derzeit mit einer Datenbank verbunden ist|
|[CDaoDatabase:: Open](#open)|Herstellen einer Verbindung mit einer Datenbank.|
|[CDaoDatabase:: setQueryTimeout](#setquerytimeout)|Legt die Anzahl von Sekunden fest, nach denen bei Datenbankabfrage Vorgängen (nur für ODBC-Datenquellen) ein Timeout auftritt. Wirkt sich auf alle nachfolgenden geöffneten, neuen, Aktualisierungs-und Löschvorgänge aus.|

### <a name="public-data-members"></a>Öffentliche Datenelemente

|Name|Beschreibung|
|----------|-----------------|
|[CDaoDatabase:: m_pDAODatabase](#m_pdaodatabase)|Ein Zeiger auf das zugrunde liegende DAO-Datenbank-Objekt.|
|[CDaoDatabase:: m_pWorkspace](#m_pworkspace)|Ein Zeiger auf das [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) -Objekt, das die Datenbank enthält und den Transaktions Bereich definiert.|

## <a name="remarks"></a>Hinweise

Informationen zu den unterstützten Daten Bank Formaten finden Sie unter der [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) -Member-Funktion. Sie können ein oder mehrere `CDaoDatabase` Objekte gleichzeitig in einem gegebenen "Arbeitsbereich" aktivieren, der durch ein [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) -Objekt dargestellt wird. Der Arbeitsbereich verwaltet eine Auflistung von geöffneten Datenbankobjekten, die aus der datenbankauflistung aufgerufen.

## <a name="usage"></a>Verwendung

Sie können implizit Datenbankobjekte erstellen, bei der Erstellung des Recordset-Objekte. Aber Sie können auch Datenbankobjekte explizit erstellen. Führen Sie einen der folgenden Schritte aus, um eine vorhandene Datenbank explizit mit `CDaoDatabase`zu verwenden:

- Erstellen Sie ein `CDaoDatabase` Objekt, und übergeben Sie einen Zeiger auf ein offenes [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) -Objekt.

- Oder erstellen Sie ein `CDaoDatabase` Objekt, ohne den Arbeitsbereich anzugeben (MFC erstellt ein temporäres Arbeitsbereichs Objekt).

Zum Erstellen eines neuen Microsoft Jet (. MDB), erstellen Sie ein `CDaoDatabase` Objekt, und rufen Sie seine [Create](#create) Member-Funktion auf. Nach `Create``Open` *nicht* mehr aufgerufen werden.

Um eine vorhandene Datenbank zu öffnen, erstellen Sie ein `CDaoDatabase`-Objekt, und nennen Sie seine [Open](#open) -Member-Funktion.

Diese Techniken datenbankauflistung des Arbeitsbereichs das DAO-Datenbankobjekt, das hinzufügt und öffnet eine Verbindung mit den Daten. Wenn Sie anschließend [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)-, [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)-oder [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) -Objekte für die verbundene Datenbank erstellen, übergeben Sie die Konstruktoren für diese Objekte einem Zeiger auf das `CDaoDatabase` Objekt. Wenn Sie die Verbindung nicht mehr verwenden, können Sie die Funktion zum [Schließen](#close) des Members aufzurufen und das `CDaoDatabase` Objekt zerstören. `Close` schließt alle Recordsets, die Sie zuvor noch nicht geschlossen haben.

## <a name="transactions"></a>Transaktionen

Die Verarbeitung von Datenbanktransaktionen wird auf Arbeitsbereichs Ebene bereitgestellt – Weitere Informationen finden Sie in den Element Funktionen [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans)und [Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) der Klasse `CDaoWorkspace`.

## <a name="odbc-connections"></a>ODBC-Verbindungen

Anfügen von externen Tabellen an einen Microsoft Jet ist die empfohlene Methode zum Arbeiten mit ODBC-Datenquellen (. MDB)-Datenbank.

## <a name="collections"></a>Auflistungen

Jede Datenbank behält eine eigene Sammlungen von Tabledef "," Querydef "," Recordset "und" Beziehungsobjekte. Class `CDaoDatabase` stellt Element Funktionen zum Bearbeiten dieser Objekte bereit.

> [!NOTE]
>  Die Objekte werden nicht in der MFC-Datenbankobjekt, das in-DAO-, gespeichert. MFC stellt Klassen für Tabledef, Querydef und Recordset-Objekte jedoch nicht für die Beziehungsobjekte bereit.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>Voraussetzungen

**Header:** afxdao.h

##  <a name="cantransact"></a>CDaoDatabase:: CanTransact

Rufen Sie diese Memberfunktion, um festzustellen, ob der Datenbank Transaktionen zulässig ist.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Datenbank Transaktionen unterstützt wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Transaktionen werden in der Datenbank-Arbeitsbereich verwaltet.

##  <a name="canupdate"></a>CDaoDatabase:: CanUpdate

Mit dieser Member-Funktion können Sie ermitteln, ob das `CDaoDatabase` Objekt Updates zulässt.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das `CDaoDatabase` Objekt Updates zulässt. Andernfalls ist der Wert 0 (null), der angibt, dass Sie "true" in *bReadOnly* übertragen haben, als Sie das `CDaoDatabase` Objekt geöffnet haben oder die Datenbank selbst schreibgeschützt ist Siehe die [Open](#open) Member-Funktion.

### <a name="remarks"></a>Hinweise

Informationen zu Datenbank-aktualisierbarkeit finden Sie im Thema "Aktualisierbare Property" in-DAO-Hilfe.

##  <a name="cdaodatabase"></a>CDaoDatabase:: CDaoDatabase

Erstellt ein `CDaoDatabase`-Objekt.

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>Parameter

*pworkspace*<br/>
Ein Zeiger auf das `CDaoWorkspace` Objekt, das das neue Datenbankobjekt enthalten soll. Wenn Sie den Standardwert NULL akzeptieren, erstellt der Konstruktor ein temporäres `CDaoWorkspace` Objekt, das den DAO-Standard Arbeitsbereich verwendet. Sie können über das [m_pWorkspace](#m_pworkspace) Datenmember einen Zeiger auf das Arbeitsbereichs Objekt erhalten.

### <a name="remarks"></a>Hinweise

Wenn Sie ein neues Microsoft Jet erstellen (), nachdem Sie das Objekt erstellt haben. MDB), rufen Sie die [Create](#create) Member-Funktion des Objekts auf. Wenn Sie stattdessen eine vorhandene Datenbank öffnen, können Sie die [Open](#open) -Member-Funktion des-Objekts aufzurufen.

Wenn Sie mit dem-Objekt fertig sind, sollten Sie seine [Close](#close) -Member-Funktion und dann das `CDaoDatabase` Objekt zerstören.

Möglicherweise ist es praktisch, das `CDaoDatabase` Objekt in die Dokument Klasse einzubetten.

> [!NOTE]
>  Ein `CDaoDatabase`-Objekt wird auch implizit erstellt, wenn Sie ein [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) -Objekt öffnen, ohne einen Zeiger auf ein vorhandenes `CDaoDatabase` Objekt zu übergeben. Dieses Datenbankobjekt wird geschlossen, wenn Sie das Recordset-Objekt schließen.

##  <a name="close"></a>CDaoDatabase:: Close

Rufen Sie diese Memberfunktion zum Trennen einer Datenbank, und schließen Sie alle geöffneten Recordsets Tabledefs und Querydefs der Datenbank zugeordnet.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Es wird empfohlen, diese Objekte selbst schließen, bevor Sie diese Memberfunktion aufrufen. Durch das Schließen eines `CDaoDatabase` Objekts wird es aus der Auflistung der Datenbanken im zugeordneten [Arbeitsbereich](../../mfc/reference/cdaoworkspace-class.md)entfernt. Da `Close` das `CDaoDatabase`-Objekt nicht zerstört, können Sie das-Objekt wieder verwenden, indem Sie dieselbe Datenbank oder eine andere Datenbank öffnen.

> [!CAUTION]
>  Nennen Sie die Funktion [Update](../../mfc/reference/cdaorecordset-class.md#update) Member (Wenn ausstehende bearbeitvorgänge vorhanden sind) und die `Close` Member-Funktion für alle geöffneten Recordset-Objekte, bevor Sie eine Datenbank schließen. Wenn Sie eine Funktion beenden, die [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) oder `CDaoDatabase` Objekte auf dem Stapel deklariert, wird die Datenbank geschlossen. alle nicht gespeicherten Änderungen gehen verloren, alle ausstehenden Transaktionen werden zurückgesetzt, und alle ausstehenden Änderungen an den Daten gehen verloren.

> [!CAUTION]
>  Wenn Sie versuchen, ein Datenbankobjekt zu schließen, während alle Recordset-Objekte geöffnet sind oder wenn Sie versuchen, ein Workspace-Objekt schließen, während alle Datenbankobjekte, die mit diesem spezifischen Arbeitsbereich gehören geöffnet sind, wird die Recordset-Objekte werden geschlossen, und alle ausstehenden Updates oder Änderungen werden auf ein Rollback. Wenn Sie versuchen, ein Workspace-Objekt schließen, während alle Datenbankobjekte, die zu der sie gehören geöffnet sind, beendet den Vorgang alle Datenbankobjekte, die auf diesem spezifischen Arbeitsbereich-Objekt, das führt nicht geschlossene Recordset-Objekte, die geschlossen werden, gehören. Wenn Sie nicht Ihr Database-Objekt schließen, meldet MFC ein Assertionsfehler in Debugbuilds.

Wenn das Datenbankobjekt, das außerhalb des Bereichs einer Funktion definiert ist, und Sie die Funktion beenden, ohne ihn zu schließen, das Datenbankobjekt, das bleibt geöffnet, bis Sie explizit geschlossen oder das Modul, in dem sie definiert ist, außerhalb des gültigen Bereichs ist.

##  <a name="create"></a>CDaoDatabase:: Create

Zum Erstellen eines neuen Microsoft Jet (. MDB) die folgende Member-Funktion wird aufgerufen, nachdem Sie ein `CDaoDatabase`-Objekt erstellt haben.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>Parameter

*lpszname*<br/>
Ein Zeichenfolgenausdruck, der den Namen der Datenbankdatei ist, die Sie erstellen. Dies kann der vollständige Pfad und Dateiname sein, z. b. "C:\\\MyDB. MDB ". Sie müssen einen Namen angeben. Wenn Sie keine Dateierweiterung angeben. MDB wird angefügt. Wenn Ihr Netzwerk die Uniform Naming Convention (UNC) unterstützt, können Sie auch einen Netzwerkpfad angeben, z. b. "\\\\\\\meinserver\\\meinefreigabe\\\meindir\\\meinedb". Nur Microsoft Jet (. Verwenden diese Memberfunktion können die Datenbankdateien MDB) erstellt werden. (Doppelte umgekehrte Schrägstriche sind in Zeichenfolgenliteralen erforderlich, da " C++\\" das Escapezeichen ist.)

*lpszlocale*<br/>
Es wurde ein Zeichenfolgenausdruck verwendet, um die Sortierreihenfolge für das Erstellen der Datenbank anzugeben. Der Standardwert ist `dbLangGeneral`. Dabei sind folgende Werte möglich:

- `dbLangGeneral` Englisch, Deutsch, Französisch, Portugiesisch, Italienisch und modern Spanisch

- `dbLangArabic` Arabisch

- `dbLangCyrillic` Russisch

- `dbLangCzech` Tschechisch

- `dbLangDutch` Niederländisch

- `dbLangGreek` Griechisch

- `dbLangHebrew` Hebräisch

- `dbLangHungarian` Ungarisch

- `dbLangIcelandic` Isländisch

- `dbLangNordic` Nordische Sprachen (nur Microsoft Jet-Datenbank-Engine, Version 1,0)

- `dbLangNorwdan` Norwegisch und Dänisch

- `dbLangPolish` Polnisch

- traditionelles Spanisch `dbLangSpanish`

- `dbLangSwedfin` Swedish und Finnisch

- `dbLangTurkish` Türkisch

*dwOptions*<br/>
Eine ganze Zahl, die eine oder mehrere Optionen angibt. Dabei sind folgende Werte möglich:

- `dbEncrypt` eine verschlüsselte Datenbank erstellen.

- `dbVersion10` erstellen Sie eine Datenbank mit Microsoft Jet Database, Version 1,0.

- `dbVersion11` erstellen Sie eine Datenbank mit Microsoft Jet Database, Version 1,1.

- `dbVersion20` erstellen Sie eine Datenbank mit Microsoft Jet Database, Version 2,0.

- `dbVersion30` erstellen Sie eine Datenbank mit Microsoft Jet Database, Version 3,0.

Wenn Sie die Verschlüsselungskonstante weglassen, wird eine unverschlüsselte Datenbank erstellt. Sie können nur eine Versionskonstante angeben. Wenn Sie eine Versionskonstante weglassen, wird eine Datenbank, die Version 3.0 der Microsoft Jet-Datenbank verwendet, erstellt.

> [!CAUTION]
>  Wenn eine Datenbank nicht verschlüsselt ist, kann, auch wenn Sie Benutzername und Kennwort-Sicherheit implementieren, um direkt die binäre Datenträgerdatei lesen, aus der Datenbank besteht.

### <a name="remarks"></a>Hinweise

`Create` erstellt die Datenbankdatei und das zugrunde liegende DAO Database-Objekt und C++ initialisiert das-Objekt. Das Objekt wird an den zugehörigen Arbeitsbereich datenbankauflistung angefügt. Das Datenbankobjekt befindet sich in einem geöffneten Zustand. nach `Create``Open*` nicht mehr aufgerufen werden.

> [!NOTE]
>  Mit `Create`können Sie nur Microsoft Jet () erstellen. MDB). Sie können keine ISAM-Datenbanken oder ODBC-Datenbanken erstellen.

##  <a name="createrelation"></a>CDaoDatabase:: up

Rufen Sie diese Memberfunktion, um eine Beziehung zwischen einem oder mehreren Feldern in einer primären Tabelle in der Datenbank und ein oder mehrere Felder in einer Fremdschlüsseltabelle (einer anderen Tabelle in der Datenbank) herzustellen.

```
void CreateRelation(
    LPCTSTR lpszName,
    LPCTSTR lpszTable,
    LPCTSTR lpszForeignTable,
    long lAttributes,
    LPCTSTR lpszField,
    LPCTSTR lpszForeignField);

void CreateRelation(CDaoRelationInfo& relinfo);
```

### <a name="parameters"></a>Parameter

*lpszname*<br/>
Der eindeutige Name, der die Relation-Objekt. Der Name muss mit einem Buchstaben beginnen und darf maximal 40 Zeichen enthalten. Er kann Zahlen enthalten und Unterstrich-Zeichen, aber keine Interpunktionszeichen oder Leerzeichen enthalten.

*lpsztable*<br/>
Der Name der primären Tabelle in der Beziehung. Wenn die Tabelle nicht vorhanden ist, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md)aus.

*lpszfremdntabelle*<br/>
Der Name der foreign-Tabelle in der Beziehung. Wenn die Tabelle nicht vorhanden ist, löst MFC eine Ausnahme vom Typ `CDaoException`aus.

*lattributes*<br/>
Ein long-Wert, der Informationen über den Beziehungstyp enthält. Sie können diesen Wert verwenden, um unter anderem mit referenzieller Integrität zu erzwingen. Sie können den bitweisen OR-Operator ( **&#124;** ) verwenden, um einen der folgenden Werte zu kombinieren (sofern die Kombination sinnvoll ist):

- `dbRelationUnique` Beziehung ist eins zu eins.

- `dbRelationDontEnforce` Beziehung wird nicht erzwungen (keine referenzielle Integrität).

- `dbRelationInherited` Beziehung ist in einer nicht aktuellen Datenbank vorhanden, die die beiden angefügten Tabellen enthält.

- `dbRelationUpdateCascade` Updates werden kaskadiert (Weitere Informationen zu den kaskadierenden finden Sie unter Hinweise).

- `dbRelationDeleteCascade` Löschungen werden kaskadiert.

*lpszfield*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namen eines Felds in der primären Tabelle (benannt durch *lpsztable*) enthält.

*lpszfremdnfield*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namen eines Felds in der fremd Tabelle (benannt durch *lpszforeign ntable*) enthält.

*relinfo*<br/>
Ein Verweis auf ein [cdaorelationinfo](../../mfc/reference/cdaorelationinfo-structure.md) -Objekt, das Informationen über die Beziehung enthält, die Sie erstellen möchten.

### <a name="remarks"></a>Hinweise

Die Beziehung kann keiner Abfrage oder einer verknüpften Tabelle aus einer externen Datenbank umfassen.

Verwenden Sie die erste Version der Funktion, wenn die Beziehung ein Feld in jeder der beiden Tabellen einschließt. Verwenden Sie die zweite Version aus, wenn die Beziehung mehrere Felder umfasst. Die maximale Anzahl von Feldern in einer Beziehung ist 14.

Durch diese Aktion wird ein zugrunde liegendes DAO-Beziehungs Objekt erstellt, aber dies ist ein MFC-Implementierungsdetail, da die MFC-Kapselung von Beziehungs Objekten in Klassen `CDaoDatabase`enthalten ist. MFC stellt eine Klasse nicht für Beziehungen bereit.

Wenn Sie die Beziehung Attribute zum Aktivieren der Cascade-Vorgänge des Objekts festlegen, wird in die Datenbank-Engine automatisch aktualisiert oder löscht Datensätze in eine oder mehrere Tabellen aus, wenn Änderungen an verknüpfte primären Schlüssel Tabellen vorgenommen werden.

Nehmen wir beispielsweise an, dass Sie eine Cascade Delete-Beziehung zwischen einer Customers-Tabelle und eine Orders-Tabelle einrichten. Wenn Sie Datensätze aus der Customers-Tabelle löschen, werden die Datensätze in der Orders-Tabelle, die im Zusammenhang mit diesen Kunden ebenfalls gelöscht. Darüber hinaus, wenn Sie eine Cascade Delete-Beziehungen zwischen der Orders-Tabelle und anderen Tabellen erstellen, werden Datensätze aus diesen Tabellen automatisch gelöscht, wenn Sie Datensätze aus der Customers-Tabelle löschen.

Verwandte Informationen finden Sie im Thema "CreateRelation Method" in-DAO-Hilfe.

##  <a name="deletequerydef"></a>CDaoDatabase::D eletequerydef

Mit dieser Member-Funktion können Sie die angegebene QueryDef – gespeicherte Abfrage – aus der QueryDefs-Auflistung des `CDaoDatabase` Objekts löschen.

```
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*lpszname*<br/>
Der Name der gespeicherten Abfrage, um zu löschen.

### <a name="remarks"></a>Hinweise

Diese Abfrage ist anschließend nicht mehr in der Datenbank definiert.

Weitere Informationen zum Erstellen von Querydef-Objekten finden Sie unter Class [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Ein QueryDef-Objekt wird einem bestimmten `CDaoDatabase` Objekt zugeordnet, wenn Sie das `CDaoQueryDef`-Objekt erstellen und ihm einen Zeiger auf das Datenbankobjekt übergeben.

##  <a name="deleterelation"></a>CDaoDatabase::D eleterelierung

Rufen Sie diese Memberfunktion zum Löschen einer vorhandenen Beziehung aus das Datenbankobjekt, das die Relations-Auflistung.

```
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*lpszname*<br/>
Der Name des zu löschenden Beziehung.

### <a name="remarks"></a>Hinweise

Danach ist Sie die Beziehung nicht mehr vorhanden.

Verwandte Informationen finden Sie im Thema "-Methode Delete" in-DAO-Hilfe.

##  <a name="deletetabledef"></a>CDaoDatabase::D eletetabledef

Mit dieser Member-Funktion können Sie die angegebene Tabelle und alle zugehörigen Daten aus der TableDefs-Auflistung des `CDaoDatabase` Objekts löschen.

```
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*lpszname*<br/>
Der Name des Tabledef löschen.

### <a name="remarks"></a>Hinweise

Diese Tabelle wird anschließend nicht mehr in der Datenbank definiert.

> [!NOTE]
>  Seien Sie vorsichtig sein, nicht auf Systemtabellen zu löschen.

Weitere Informationen zum Erstellen von Tabledef-Objekten finden Sie unter Class [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Ein Tabledef-Objekt wird einem bestimmten `CDaoDatabase` Objekt zugeordnet, wenn Sie das `CDaoTableDef`-Objekt erstellen und ihm einen Zeiger auf das Datenbankobjekt übergeben.

Verwandte Informationen finden Sie im Thema "-Methode Delete" in-DAO-Hilfe.

##  <a name="execute"></a>CDaoDatabase:: Execute

Rufen Sie diese Memberfunktion zum Ausführen einer Aktionsabfrage aus, oder führen eine SQL-Anweisung für die Datenbank an.

```
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Parameter

*lpszSQL*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge, die mit einem gültigen SQL‑Befehl ausgeführt.

*noptions*<br/>
Eine ganze Zahl, die Optionen in Bezug auf die Integrität der Abfrage angibt. Sie können den bitweisen OR-Operator ( **&#124;** ) verwenden, um eine der folgenden Konstanten zu kombinieren (vorausgesetzt, die Kombination ist sinnvoll – beispielsweise würden Sie `dbInconsistent` nicht mit `dbConsistent`kombinieren):

- `dbDenyWrite` die Schreib Berechtigung für andere Benutzer zu verweigern.

- `dbInconsistent` (Standard) inkonsistente Updates.

- `dbConsistent` konsistente Updates.

- `dbSQLPassThrough` SQL-Pass-Through. Bewirkt, dass die SQL-Anweisung für die Verarbeitung einer ODBC-Datenquelle übergeben werden soll.

- Wenn ein Fehler auftritt, `dbFailOnError` Updates zurück.

- `dbSeeChanges` generieren Sie einen Laufzeitfehler, wenn ein anderer Benutzer die Daten ändert, die Sie bearbeiten.

> [!NOTE]
>  Wenn sowohl `dbInconsistent` als auch `dbConsistent` enthalten sind, oder wenn keines von beiden enthalten ist, ist das Ergebnis der Standardwert. Eine Erläuterung dieser Konstanten sind finden Sie im Thema "Execute-Methode" in-DAO-Hilfe.

### <a name="remarks"></a>Hinweise

`Execute` funktioniert nur für Aktions Abfragen oder SQL-Pass-Through-Abfragen, die keine Ergebnisse zurückgeben. Es funktioniert nicht für select-Abfragen, die Datensätze zurückgeben.

Eine Definition sowie die Informationen zur Aktionsabfragen finden Sie unter den Themen "Query-Aktion" und "Execute-Methode" in-DAO-Hilfe.

> [!TIP]
>  Wenn eine syntaktisch korrekte SQL-Anweisung und die richtigen Berechtigungen vorliegen, schlägt die `Execute` Member-Funktion auch dann fehl, wenn nicht eine einzelne Zeile geändert oder gelöscht werden kann. Verwenden Sie daher immer die Option `dbFailOnError`, wenn Sie die `Execute` Member-Funktion verwenden, um eine Update-oder DELETE-Abfrage auszuführen. Diese Option bewirkt, dass MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md) auslöst und einen Rollback für alle erfolgreichen Änderungen ausführt, wenn einer der betroffenen Datensätze gesperrt ist und nicht aktualisiert oder gelöscht werden kann. Beachten Sie, dass Sie immer `GetRecordsAffected` abrufen können, um zu sehen, wie viele Datensätze betroffen sind.

Aufrufen der [getrecordsaff-](#getrecordsaffected) Member-Funktion des Database-Objekts, um die Anzahl der Datensätze zu ermitteln, die vom letzten `Execute`-aufrufungs Fehler betroffen sind. `GetRecordsAffected` gibt z. b. Informationen über die Anzahl der Datensätze zurück, die beim Ausführen einer Aktions Abfrage gelöscht, aktualisiert oder eingefügt wurden. Die Anzahl die zurückgegebenen spiegeln sich nicht auf Änderungen in verknüpften Tabellen auf, wenn Cascade aktualisiert oder löscht wirksam sind.

`Execute` gibt kein Recordset zurück. Die Verwendung von `Execute` in einer Abfrage, die Datensätze auswählt, bewirkt, dass MFC eine Ausnahme vom Typ `CDaoException`auslöst. (Es gibt keine `ExecuteSQL` Member-Funktion analog zu `CDatabase::ExecuteSQL`.)

##  <a name="getconnect"></a>CDaoDatabase:: GetConnect

Rufen Sie diese Member-Funktion auf, um die Verbindungs Zeichenfolge abzurufen, mit der das `CDaoDatabase` Objekt mit einer ODBC-oder ISAM-Datenbank verbunden wird

```
CString GetConnect();
```

### <a name="return-value"></a>Rückgabewert

Die Verbindungs Zeichenfolge, wenn " [Open](#open) " in einer ODBC-Datenquelle erfolgreich aufgerufen wurde. andernfalls eine leere Zeichenfolge. Für ein Microsoft Jet (. MDB) die Zeichenfolge ist immer leer, es sei denn, Sie legen Sie für die Verwendung mit der `dbSQLPassThrough`-Option fest, die mit der [Execute](#execute) Member-Funktion verwendet wird oder beim Öffnen eines Recordsets verwendet wird.

### <a name="remarks"></a>Hinweise

Die Zeichenfolge enthält Informationen über die Quelle eine geöffnete Datenbank oder einer Datenbank in einer Pass-Through-Abfrage verwendet. Die Verbindungszeichenfolge besteht aus einer Datenbank-Typspezifizierer und NULL oder mehr Parameter, die durch Semikolons getrennt ein.

> [!NOTE]
>  Verwenden die MFC-DAO-Klassen zum Verbinden mit einer Datenquelle über ODBC ist weniger effizient als das Herstellen einer Verbindung über einer angefügten Tabelle.

> [!NOTE]
>  Die Verbindungszeichenfolge wird zum Übergeben zusätzlicher Informationen auf ODBC und nach Bedarf bestimmte ISAM-Treiber verwendet. Es ist nicht für verwendet werden. MDB-Datenbanken. Für Microsoft Jet-Datenbank-Basistabellen, die Verbindungszeichenfolge ist eine leere Zeichenfolge ("") mit Ausnahme von für eine SQL-Pass-Through-Abfrage Verwendung wie beschrieben unter den oben genannten zurückgegeben Wert.

Eine Beschreibung der Erstellung der Verbindungs Zeichenfolge finden Sie unter der [Open](#open) Member-Funktion. Nachdem die Verbindungs Zeichenfolge im `Open`-Befehl festgelegt wurde, können Sie Sie später verwenden, um die Einstellung zu überprüfen, um den Typ, den Pfad, die Benutzer-ID, das Kennwort oder die ODBC-Datenquelle der Datenbank zu bestimmen.

##  <a name="getname"></a>CDaoDatabase:: GetName

Rufen Sie diese Memberfunktion um den Namen der aktuell geöffneten Datenbank, die den Namen einer vorhandenen Datenbank-Datei ist oder der Name einer registrierten ODBC-Datenquelle abrufen.

```
CString GetName();
```

### <a name="return-value"></a>Rückgabewert

Der vollständige Pfad und der Dateiname der Datenbank, wenn der Vorgang erfolgreich war. andernfalls eine leere [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Hinweise

Wenn Ihr Netzwerk die Uniform Naming Convention (UNC) unterstützt, können Sie auch einen Netzwerkpfad angeben – z. b. "\\\\\\\meinserver\\\meinefreigabe\\\meinedir\\\MyDB. MDB ". (Doppelte umgekehrte Schrägstriche sind in Zeichenfolgenliteralen erforderlich, da " C++\\" das Escapezeichen ist.)

Sie könnten z. B. diesen Namen in einer Überschrift anzuzeigen. Wenn beim Abrufen des Namens ein Fehler auftritt, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md)aus.

> [!NOTE]
>  Für eine bessere Leistung, wenn externe Datenbanken zugegriffen wird, empfehlen wir, dass Sie externe Tabellen in einer Microsoft Jet-Datenbank anfügen (. MDB) anstatt eine direkte Verbindung mit der Datenquelle.

Der Typ wird durch die Datei oder das Verzeichnis, die der Pfad, wie folgt zeigt angegeben:

|PathName-verweist auf...|Datenbanktyp|
|--------------------------|-------------------|
|. MDB-Datei|Microsoft Jet-Datenbank (Microsoft Access)|
|Verzeichnis, enthält. DBF-Dateien|Access-Datenbank|
|Verzeichnis, enthält. XLS-Datei|Microsoft Excel-Datenbank|
|Verzeichnis, enthält. PDX-Dateien|Paradox-Datenbank|
|Verzeichnis mit der Datenbankdateien richtig formatierten text|Text-Format-Datenbank|

Für ODBC-Datenbanken wie SQL Server und Oracle identifiziert der Datenbank-Verbindungszeichenfolge einen Datenquellennamen (DSN), der von ODBC registriert ist.

##  <a name="getquerydefcount"></a>CDaoDatabase:: getquerydefcount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Abfragen, die in der Datenbank QueryDefs-Auflistung definiert.

```
short GetQueryDefCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Abfragen, die in der Datenbank definiert.

### <a name="remarks"></a>Hinweise

`GetQueryDefCount` ist nützlich, wenn Sie alle Querydefs in der QueryDefs-Auflistung durchlaufen müssen. Informationen zu einer bestimmten Abfrage in der Auflistung finden Sie unter [GetQueryDefInfo](#getquerydefinfo).

##  <a name="getquerydefinfo"></a>CDaoDatabase:: GetQueryDefInfo

Rufen Sie diese Memberfunktion, um verschiedene Arten von Informationen über eine Abfrage, die in der Datenbank definierten zu erhalten.

```
void GetQueryDefInfo(
    int nIndex,
    CDaoQueryDefInfo& querydefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetQueryDefInfo(
    LPCTSTR lpszName,
    CDaoQueryDefInfo& querydefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index der vordefinierten Abfrage in der Datenbank QueryDefs-Auflistung, für die Suche nach Index.

*querydefinfo*<br/>
Ein Verweis auf ein [cdaoquerydefinfo](../../mfc/reference/cdaoquerydefinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.

*dwinfooptions*<br/>
Optionen, die angeben, welche Informationen das Recordset abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit was sie die Funktion führen, die das Recordset zurückgegeben werden sollen:

- AFX_DAO_PRIMARY_INFO (Standard)-Namen, Typ

- Primäre AFX_DAO_SECONDARY_INFO Informationen plus: Erstellungsdatum, Datum der letzten Aktualisierung, gibt Datensätze zurück, aktualisierbar

- AFX_DAO_ALL_INFO primären und sekundären Informationen plus: SQL, Connect, Timeoutfehlers warten soll.

*lpszname*<br/>
Eine Zeichenfolge, die mit dem Namen einer Abfrage, die in der Datenbank, für die Suche nach dem Namen definiert.

### <a name="remarks"></a>Hinweise

Zwei Versionen der Funktion werden bereitgestellt, sodass Sie eine Abfrage nach Index in der Datenbank QueryDefs-Auflistung oder durch den Namen der Abfrage auswählen können.

Eine Beschreibung der Informationen, die in *querydefinfo*zurückgegeben werden, finden Sie in der [cdaoquerydefinfo](../../mfc/reference/cdaoquerydefinfo-structure.md) -Struktur. Diese Struktur enthält Member, die den in der Beschreibung von *dwinfooptions*aufgeführten Elementen der oben aufgeführten Informationen entsprechen. Wenn Sie eine Ebene Informationen anfordern, erhalten Sie alle vorherigen Ebenen sowie Informationen.

##  <a name="getquerytimeout"></a>CDaoDatabase:: getquerytimeout

Rufen Sie diese Memberfunktion zum Abrufen der aktuellen Anzahl der Sekunden, Anmeldefehler, bevor nachfolgende Vorgänge in der verbundenen Datenbank ein erfolgt Timeout.

```
short GetQueryTimeout();
```

### <a name="return-value"></a>Rückgabewert

Ein short Integer, der den Timeoutwert in Sekunden enthält.

### <a name="remarks"></a>Hinweise

Ein Vorgang kann aufgrund von Netzwerkproblemen für den Zugriff, übermäßige Abfrage Verarbeitungszeit und usw. Timeout. Obwohl die Einstellung wirksam ist, wirkt sie sich auf alle geöffneten, neuen, Aktualisierungs-und Löschvorgänge für alle Recordsets aus, die diesem `CDaoDatabase` Objekt zugeordnet sind. Sie können die aktuelle Timeout Einstellung durch Aufrufen von [setQueryTimeout](#setquerytimeout)ändern. Ändern den Timeoutwert für Abfragen für ein Recordset nach Öffnen ändert sich nicht auf den Wert für das Recordset aus. Bei [nachfolgenden](../../mfc/reference/cdaorecordset-class.md#move) Verschiebungs Vorgängen wird z. b. der neue Wert nicht verwendet. Standardmäßig ist der Wert wird anfangs festgelegt, wenn die Datenbank-Engine initialisiert wird.

Der Standardwert für die Abfragetimeouts stammt aus der Windows-Registrierung. Liegt keine registrierungseinstellung, ist der Standardwert 60 Sekunden. Nicht alle Datenbanken unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, erfolgt kein timeout und die Kommunikation mit der Datenbank möglicherweise nicht mehr reagiert. Dieses Verhalten kann während der Entwicklung nützlich sein. Wenn der-Befehl fehlschlägt, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md)aus.

Verwandte Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" in-DAO-Hilfe.

##  <a name="getrecordsaffected"></a>CDaoDatabase:: getrecordsafffiziert

Mit dieser Member-Funktion können Sie die Anzahl der Datensätze ermitteln, die durch den letzten-Rückruf der [Execute](#execute) Member-Funktion betroffen sind.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Rückgabewert

Eine lange ganze Zahl, die die Anzahl der betroffenen Datensätze enthält.

### <a name="remarks"></a>Hinweise

Der zurückgegebene Wert enthält die Anzahl der Datensätze, die durch eine mit `Execute`auszuführende Aktions Abfrage gelöscht, aktualisiert oder eingefügt wurden. Die Anzahl die zurückgegebenen spiegeln sich nicht auf Änderungen in verknüpften Tabellen auf, wenn Cascade aktualisiert oder löscht wirksam sind.

Verwandte Informationen finden Sie im Thema "RecordsAffected-Eigenschaft" in-DAO-Hilfe.

##  <a name="getrelationcount"></a>CDaoDatabase:: getrelationcount

Rufen Sie diese Memberfunktion, um die Anzahl der Beziehungen zwischen Tabellen in der Datenbank abzurufen.

```
short GetRelationCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.

### <a name="remarks"></a>Hinweise

`GetRelationCount` ist nützlich, wenn Sie alle definierten Beziehungen in der Beziehungs Sammlung der Datenbank durchlaufen müssen. Informationen zu einer bestimmten Beziehung in der Auflistung finden Sie unter [getrelationinfo](#getrelationinfo).

Um das Konzept der eine Beziehung zu veranschaulichen, sollten Sie in einer Lieferantentabelle und eine Produkttabelle, die eine 1: n Beziehung aufweisen kann. In dieser Beziehung kann ein Lieferant mehr als ein Produkt angeben. Andere Beziehungen sind 1: 1- und m: n.

##  <a name="getrelationinfo"></a>CDaoDatabase:: getrelationinfo

Rufen Sie diese Memberfunktion zum Abrufen von Informationen zu einer angegebenen Beziehung in der Datenbank Relations-Auflistung.

```
void GetRelationInfo(
    int nIndex,
    CDaoRelationInfo& relinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetRelationInfo(
    LPCTSTR lpszName,
    CDaoRelationInfo& relinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des in der Datenbank Relations-Auflistung, für die Suche anhand des Indexes die Relation-Objekt.

*relinfo*<br/>
Ein Verweis auf ein [cdaorelationinfo](../../mfc/reference/cdaorelationinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.

*dwinfooptions*<br/>
Optionen, die angeben, welche Informationen über die Beziehung abgerufen werden. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion, die über die Beziehung zurück verursachen:

- AFX_DAO_PRIMARY_INFO (Standard), Tabelle, Foreign Namenstabelle

- Feldinformationen AFX_DAO_SECONDARY_INFO Attribute

Die Feldinformationen sind ein [cdaorelationfieldinfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) -Objekt, das die Felder aus der primären Tabelle enthält, die an der Beziehung beteiligt ist.

*lpszname*<br/>
Eine Zeichenfolge, die mit dem Namen der Relation-Objekt, für die Suche anhand des Namens.

### <a name="remarks"></a>Hinweise

Zwei Versionen dieser Funktion ermöglichen den Zugriff entweder anhand des Indexes oder anhand des Namens. Eine Beschreibung der Informationen, die in *relinfo*zurückgegeben werden, finden Sie in der [cdaorelationinfo](../../mfc/reference/cdaorelationinfo-structure.md) -Struktur. Diese Struktur enthält Member, die den in der Beschreibung von *dwinfooptions*aufgeführten Elementen der oben aufgeführten Informationen entsprechen. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie auch Informationen an alle vorherigen Ebenen sowie an.

> [!NOTE]
>  Wenn Sie die Attribute des Beziehungs Objekts zum Aktivieren von kaskadierenden Vorgängen (`dbRelationUpdateCascades` oder `dbRelationDeleteCascades`) festgelegt haben, aktualisiert oder löscht die Microsoft Jet-Datenbank-Engine automatisch Datensätze in einer oder mehreren anderen Tabellen, wenn Änderungen an verknüpften Primärschlüssel Tabellen vorgenommen werden. Nehmen wir beispielsweise an, dass Sie eine Cascade Delete-Beziehung zwischen einer Customers-Tabelle und eine Orders-Tabelle einrichten. Wenn Sie Datensätze aus der Customers-Tabelle löschen, werden die Datensätze in der Orders-Tabelle, die im Zusammenhang mit diesen Kunden ebenfalls gelöscht. Darüber hinaus, wenn Sie eine Cascade Delete-Beziehungen zwischen der Orders-Tabelle und anderen Tabellen erstellen, werden Datensätze aus diesen Tabellen automatisch gelöscht, wenn Sie Datensätze aus der Customers-Tabelle löschen.

##  <a name="gettabledefcount"></a>CDaoDatabase:: GetTableDefCount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Tabellen in der Datenbank definiert.

```
short GetTableDefCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der in der Datenbank definierten Tabledefs.

### <a name="remarks"></a>Hinweise

`GetTableDefCount` ist nützlich, wenn Sie alle Tabledefs in der Tabledefs-Sammlung der Datenbank durchlaufen müssen. Informationen zu einer bestimmten Tabelle in der Sammlung finden Sie unter [GetTableDefInfo](#gettabledefinfo).

##  <a name="gettabledefinfo"></a>CDaoDatabase:: GetTableDefInfo

Rufen Sie diese Memberfunktion zum Abrufen von verschiedenen Arten von Informationen zu einer Tabelle in der Datenbank definiert.

```
void GetTableDefInfo(
    int nIndex,
    CDaoTableDefInfo& tabledefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetTableDefInfo(
    LPCTSTR lpszName,
    CDaoTableDefInfo& tabledefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Objekts Tabledef in der Datenbank TableDefs-Auflistung, für die Suche nach Index.

*tabledefinfo*<br/>
Ein Verweis auf ein [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.

*dwinfooptions*<br/>
Optionen, die angeben, welche Informationen in der Tabelle abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion, die über die Beziehung zurück verursachen:

- AFX_DAO_PRIMARY_INFO (Standard) ein, die aktualisiert werden kann, Attribute

- Primäre AFX_DAO_SECONDARY_INFO Informationen plus: Erstellungsdatum, letzte Aktualisierung, Name der Quelltabelle, verbinden

- AFX_DAO_ALL_INFO primären und sekundären Informationen plus: Anzahl der Datensätze Validierungsregel Validierung von Text,

*lpszname*<br/>
Der Name des Objekts Tabledef, für die Suche anhand des Namens.

### <a name="remarks"></a>Hinweise

Zwei Versionen der Funktion werden bereitgestellt, sodass Sie eine Tabelle nach Index in der Datenbank TableDefs-Auflistung oder durch den Namen der Tabelle auswählen können.

Eine Beschreibung der Informationen, die in *tabledefinfo*zurückgegeben werden, finden Sie in der [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) -Struktur. Diese Struktur enthält Member, die den in der Beschreibung von *dwinfooptions*aufgeführten Elementen der oben aufgeführten Informationen entsprechen. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.

> [!NOTE]
>  Die Option AFX_DAO_ALL_INFO bietet Informationen, die langsame abgerufen werden können. In diesem Fall die Datensätze in der Tabelle zählen möglicherweise sehr viel Zeit beanspruchen, wenn viele Datensätze vorhanden sind.

##  <a name="getversion"></a>CDaoDatabase:: GetVersion

Rufen Sie diese Memberfunktion zum Ermitteln der Version der Microsoft Jet-Datenbankdatei an.

```
CString GetVersion();
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Wert, der die Version der Datenbankdatei angibt, die dem-Objekt zugeordnet ist.

### <a name="remarks"></a>Hinweise

Der zurückgegebene Wert stellt die Versionsnummer im Format "Hauptversion.Nebenversion"; z. B. "3.0". Die Versionsnummer des Produkts (z. B. "3.0") besteht aus der Versionsnummer (3), einem Punkt und die Versionsnummer (0). Die Versionen bis Datum sind, 1.0, 1.1, 2.0 und 3.0.

Verwandte Informationen finden Sie im Thema "Version-Eigenschaft" in-DAO-Hilfe.

##  <a name="isopen"></a>CDaoDatabase:: IsOpen

Mit dieser Member-Funktion können Sie ermitteln, ob das `CDaoDatabase` Objekt derzeit in einer Datenbank geöffnet ist.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das `CDaoDatabase` Objekt derzeit geöffnet ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

##  <a name="m_pdaodatabase"></a>CDaoDatabase:: m_pDAODatabase

Enthält einen Zeiger auf die OLE-Schnittstelle für das DAO-Datenbankobjekt, das dem `CDaoDatabase` Objekt zugrunde liegt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Zeiger, wenn Sie die DAO-Schnittstelle direkt zugreifen möchten.

Weitere Informationen zum direkten Aufrufen von DAO finden [Sie im technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

##  <a name="m_pworkspace"></a>CDaoDatabase:: m_pWorkspace

Enthält einen Zeiger auf das [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) -Objekt, das das Datenbankobjekt enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Zeiger, wenn Sie direkt auf den Arbeitsbereich zugreifen müssen – beispielsweise, um Verweise auf andere Datenbankobjekte in der datenbankauflistung des Arbeitsbereichs zu erhalten.

##  <a name="open"></a>CDaoDatabase:: Open

Sie müssen diese Member-Funktion zum Initialisieren eines neu erstellten `CDaoDatabase`-Objekts, das eine vorhandene Datenbank darstellt, aufgerufen werden.

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>Parameter

*lpszname*<br/>
Ein Zeichenfolgenausdruck mit dem Namen einer vorhandenen Microsoft Jet (. MDB)-Datei. Wenn der Dateiname eine Erweiterung verfügt, ist jedoch erforderlich. Wenn Ihr Netzwerk die Uniform Naming Convention (UNC) unterstützt, können Sie auch einen Netzwerkpfad angeben, z. b. "\\\\\\\myserver\\\meinefreigabe\\\meindir\\\MyDB. MDB ". (Doppelte umgekehrte Schrägstriche sind in Zeichenfolgenliteralen erforderlich, da " C++\\" das Escapezeichen ist.)

Bei der Verwendung von *lpszname*sind einige Aspekte zu beachten. Wenn sie:

- Bezieht sich auf eine Datenbank, die bereits für den exklusiven Zugriff durch einen anderen Benutzer geöffnet ist. MFC löst eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md)aus. Abfangen von dieser Ausnahme aus, um Ihre Benutzer wissen, dass die Datenbank nicht verfügbar ist.

- Ist eine leere Zeichenfolge (""), und *lpszconnect* ist "ODBC;". es wird ein Dialogfeld angezeigt, in dem alle registrierten ODBC-Datenquellen Namen aufgeführt werden, damit der Benutzer eine Datenbank auswählen kann. Vermeiden Sie direkte Verbindungen mit ODBC-Datenquellen; Verwenden Sie stattdessen einer angefügten Tabelle.

- Andernfalls wird nicht auf eine vorhandene Datenbank oder einen gültigen ODBC-Datenquellen Namen verwiesen. MFC löst eine Ausnahme vom Typ `CDaoException`aus.

> [!NOTE]
>  Weitere Informationen über DAO-Fehlercodes finden Sie unter den DAOERR. H-Datei. Verwandte Informationen finden Sie im Thema "Abfangbarer Datenzugriffsfehlern" in-DAO-Hilfe.

*bExclusive*<br/>
Ein boolescher Wert, der TRUE ist, wenn die Datenbank ist für die exklusive (nicht freigegeben) und "false" geöffnet werden, wenn die Datenbank ist für den gemeinsamen Zugriff geöffnet werden. Wenn Sie dieses Argument weglassen, wird die Datenbank für den gemeinsamen Zugriff geöffnet.

*nur Bread*<br/>
Ein boolescher Wert, der TRUE ist, wenn die Datenbank ist für schreibgeschützten Zugriff und "false" geöffnet werden, wenn die Datenbank ist für Lese-/Schreibzugriff geöffnet werden. Wenn Sie dieses Argument weglassen, wird die Datenbank für Lese-/Schreibzugriff geöffnet. Alle abhängigen Recordsets erben dieses Attribut.

*lpszconnect*<br/>
Ein Zeichenfolgenausdruck, der zum Öffnen der Datenbank verwendet wird. Diese Zeichenfolge bildet die ODBC eine Verbindung herstellen Argumente. Sie müssen die exklusive und Read-only-Argumente zum Bereitstellen einer Quellzeichenfolge angeben. Wenn die Datenbank Microsoft Jet-Datenbank (. (MDB), die diese Zeichenfolge ist leer (""). Die Syntax für den Standardwert – **_T**("") – bietet Portabilität für Unicode und ANSI-Builds Ihrer Anwendung.

### <a name="remarks"></a>Hinweise

`Open` verknüpft die Datenbank mit dem zugrunde liegenden DAO-Objekt. Sie können das Datenbankobjekt, das keine Recordset, Tabledef oder Querydef-Objekte erstellen, bis sie initialisiert ist. `Open` fügt das Datenbankobjekt an die Datenbanksammlung des zugeordneten Arbeitsbereichs an.

Verwenden Sie die Parameter wie folgt:

- Wenn Sie ein Microsoft Jet öffnen (. MDB), verwenden Sie den *lpszname* -Parameter, und übergeben Sie eine leere Zeichenfolge für den *lpszconnect* -Parameter, oder übergeben Sie eine Kenn Wort Zeichenfolge im Format "; PWD = Password ", wenn die Datenbank durch ein Kennwort geschützt ist (. Nur MDB-Datenbanken).

- Wenn Sie eine ODBC-Datenquelle öffnen, übergeben Sie eine gültige ODBC-Verbindungs Zeichenfolge in *lpszconnect* und eine leere Zeichenfolge in *lpszname*.

Verwandte Informationen finden Sie im Thema "OpenDatabase Method" in-DAO-Hilfe.

> [!NOTE]
>  Für eine bessere Leistung beim Zugriff auf externe Datenbanken, einschließlich ISAM-Datenbanken und ODBC-Datenquellen, wird empfohlen, dass Sie externe Tabellen in einer Microsoft Jet-Engine-Datenbank anfügen (. MDB) anstatt eine direkte Verbindung mit der Datenquelle.

Es ist möglich, dass ein Verbindungsversuch zu einem Timeout, wenn Sie z. B. der DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch fehlschlägt, löst `Open` eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md)aus.

Die verbleibenden Hinweise gelten nur für die ODBC-Datenbank:

Wenn es sich bei der Datenbank um eine ODBC-Datenbank handelt und die Parameter in Ihrem `Open`-Befehl nicht genügend Informationen enthalten, um die Verbindung herzustellen, öffnet der ODBC-Treiber ein Dialogfeld, in dem die erforderlichen Informationen vom Benutzer abgerufen werden. Wenn Sie `Open`aufrufen, wird die Verbindungs Zeichenfolge *lpszconnect*privat gespeichert und steht durch Aufrufen der [GetConnect](#getconnect) -Member-Funktion zur Verfügung.

Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, bevor Sie `Open` zum Abrufen von Informationen vom Benutzer abrufen, z. b. ein Kennwort, und diese Informationen dann der Verbindungs Zeichenfolge hinzufügen, die Sie an `Open`übergeben. Sie können auch die Verbindungs Zeichenfolge speichern, die Sie übergeben (z. BGF. in der Windows-Registrierung), damit Sie Sie wieder verwenden können, wenn Ihre Anwendung das nächste Mal `Open` für ein `CDaoDatabase` Objekt aufruft.

Sie können auch die Verbindungs Zeichenfolge für mehrere Ebenen der Anmelde Autorisierung (jeweils für ein anderes `CDaoDatabase` Objekt) oder andere datenbankspezifische Informationen verwenden.

##  <a name="setquerytimeout"></a>CDaoDatabase:: setQueryTimeout

Rufen Sie diese Memberfunktion, um die Standardanzahl von Sekunden, bevor nachfolgende Vorgänge in der verbundenen Datenbank-Timeout Gerätedaten zu überschreiben.

```
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>Parameter

*nSekunden*<br/>
Die Anzahl der Sekunden, bevor der abfrageversuch einer ist ein Timeout aufgetreten.

### <a name="remarks"></a>Hinweise

Ein Vorgang kann aufgrund von Access-Netzwerkprobleme, Verarbeitungszeit übermäßig viele Abfragen usw. Timeout. Rufen Sie `SetQueryTimeout` vor dem Öffnen des Recordsets oder vor dem Aufrufen der [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew)-, [Update](../../mfc/reference/cdaorecordset-class.md#update)-oder [Delete](../../mfc/reference/cdaorecordset-class.md#delete) -Element Funktionen des Recordsets auf, wenn Sie den Wert für das Abfrage Timeout ändern möchten. Die-Einstellung wirkt sich auf alle nachfolgenden [geöffneten](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`-, `Update`-und `Delete` Aufrufe von Recordsets aus, die diesem `CDaoDatabase`-Objekt zugeordnet sind. Ändern den Timeoutwert für Abfragen für ein Recordset nach Öffnen ändert sich nicht auf den Wert für das Recordset aus. Bei [nachfolgenden](../../mfc/reference/cdaorecordset-class.md#move) Verschiebungs Vorgängen wird z. b. der neue Wert nicht verwendet.

Der Standardwert für die Abfragetimeouts beträgt 60 Sekunden. Nicht alle Datenbanken unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, erfolgt kein timeout die Kommunikation mit der Datenbank möglicherweise nicht mehr reagiert. Dieses Verhalten kann während der Entwicklung nützlich sein.

Verwandte Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" in-DAO-Hilfe.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)<br/>
[CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
