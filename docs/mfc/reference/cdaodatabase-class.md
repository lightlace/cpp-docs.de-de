---
title: CDaoDatabase-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04e9cd105fd682c1754f4837671151c4b5814326
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339266"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase-Klasse
Stellt eine Verbindung zu einer Datenbank dar, über welche die Daten bearbeitet werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoDatabase : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|Erstellt ein `CDaoDatabase`-Objekt. Rufen Sie `Open` auf das Objekt mit einer Datenbank herzustellen.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](#cantransact)|Gibt, die ungleich NULL, wenn die Datenbank Transaktionen unterstützt.|  
|[CDaoDatabase::CanUpdate](#canupdate)|Ungleich NULL zurück, wenn die `CDaoDatabase` Objekt kann aktualisiert werden (nicht schreibgeschützt).|  
|[CDaoDatabase::Close](#close)|Beendet die datenbankverbindung an.|  
|[CDaoDatabase::Create](#create)|Das zugrunde liegende DAO-Datenbank-Objekt erstellt und initialisiert die `CDaoDatabase` Objekt.|  
|[CDaoDatabase::CreateRelation](#createrelation)|Definiert eine neue Beziehung zwischen den Tabellen in der Datenbank an.|  
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|Löscht ein Querydef-Objekt, das in der Datenbank QueryDefs-Auflistung gespeichert.|  
|[CDaoDatabase::DeleteRelation](#deleterelation)|Löscht eine vorhandene Beziehung zwischen Tabellen in der Datenbank an.|  
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|Löscht die Definition einer Tabelle in der Datenbank. Dadurch werden die tatsächliche Tabelle und alle zugehörigen Daten gelöscht.|  
|[CDaoDatabase::Execute](#execute)|Führt eine Abfrage an. Aufrufen von `Execute` für eine Abfrage, die Ergebnisse zurückgibt, eine Ausnahme auslöst.|  
|[CDaoDatabase::GetConnect](#getconnect)|Gibt die Verbindungszeichenfolge zur Verbindung der `CDaoDatabase` Objekt in einer Datenbank. Für ODBC verwendet.|  
|[CDaoDatabase::GetName](#getname)|Gibt den Namen der Datenbank, die zurzeit verwendeten zurück.|  
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|Gibt die Anzahl von Abfragen, die für die Datenbank definiert.|  
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|Gibt Informationen zu einer angegebenen Abfrage, die in der Datenbank definiert.|  
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|Gibt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge Abfragen tritt ein Timeout. Wirkt sich auf alle nachfolgenden öffnen, neue hinzufügen, aktualisieren und zu bearbeiten Vorgänge und andere Vorgänge auf ODBC-Datenquellen (nur) wie z. B. `Execute` aufrufen.|  
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|Gibt die Anzahl der Datensätze, die von der letzten Aktualisierung betroffenen bearbeiten oder das Hinzufügen oder durch einen Aufruf von `Execute`.|  
|[CDaoDatabase::GetRelationCount](#getrelationcount)|Gibt die Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.|  
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|Gibt Informationen zu einer angegebenen Beziehung zwischen Tabellen in der Datenbank definiert.|  
|[CDaoDatabase:: GetTableDefCount](#gettabledefcount)|Gibt die Anzahl der in der Datenbank definierten Tabellen zurück.|  
|[CDaoDatabase:: GetTableDefInfo](#gettabledefinfo)|Informationen zu einer angegebenen Tabelle zurückgegeben in der Datenbank.|  
|[CDaoDatabase::GetVersion](#getversion)|Gibt die Version der Datenbank-Engine, die der Datenbank zugeordnet.|  
|[CDaoDatabase::IsOpen](#isopen)|Ungleich NULL zurück, wenn die `CDaoDatabase` -Objekt aktuell mit einer Datenbank verbunden ist.|  
|[CDaoDatabase::Open](#open)|Herstellen einer Verbindung mit einer Datenbank.|  
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|Legt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge (für nur ODBC-Datenquellen) Abfragen tritt ein Timeout. Wirkt sich auf alle nachfolgenden öffnen, Hinzufügen neuer, update und delete-Operationen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|Ein Zeiger auf das zugrunde liegende DAO-Datenbank-Objekt.|  
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|Ein Zeiger auf die [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt, das die Datenbank enthält, und definiert die Transaktionsprotokoll-Speicherplatz.|  
  
## <a name="remarks"></a>Hinweise  
 Informationen zu den Datenbankformaten unterstützt, finden Sie unter den [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) Member-Funktion. Sie haben eine oder mehrere `CDaoDatabase` Objekte, die Sie in einem bestimmten "Arbeitsbereich" durch dargestellt aktiv eine [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt. Der Arbeitsbereich verwaltet eine Auflistung von geöffneten Datenbankobjekten, die aus der datenbankauflistung aufgerufen.  
  
> [!NOTE]
>  Die MFC-DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen-ODBC-basierten. Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Klasse `CDaoDatabase` stellt eine Schnittstelle, die der ODBC-Klasse ähnelt [CDatabase](../../mfc/reference/cdatabase-class.md). Der Hauptunterschied besteht darin, die `CDatabase` greift auf das DBMS über Open Database Connectivity (ODBC) und einem ODBC-Treiber für dieses DBMS verwaltet. `CDaoDatabase` greift auf Daten über ein Data Access Object (DAO) basierend auf der Microsoft Jet-Datenbank-Engine. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC; die DAO-basierten Klassen können Daten, einschließlich über ODBC-Treiber, über eigene Datenbank-Engine zugreifen. Die DAO-basierten Klassen unterstützen auch Vorgänge wie das Hinzufügen von Tabellen über die Klassen, ohne direkt aufrufen von DAO (Data Definition Language, Datendefinitionssprache).  
  
## <a name="usage"></a>Verwendung  
 Sie können implizit Datenbankobjekte erstellen, bei der Erstellung des Recordset-Objekte. Aber Sie können auch Datenbankobjekte explizit erstellen. Verwenden eine vorhandene Datenbank explizit mit `CDaoDatabase`, führen Sie einen der folgenden:  
  
-   Erstellen einer `CDaoDatabase` Objekt, das die Übergabe eines Zeigers auf ein offenes [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt.  
  
-   Oder erstellen Sie eine `CDaoDatabase` Objekt ohne Angabe des Arbeitsbereichs (MFC-erstellt ein Objekt der temporäre Arbeitsbereich).  
  
 Erstellen Sie eine neue Microsoft Jet (. MDB)-Datenbank, erstellen eine `CDaoDatabase` Objekt, und rufen die [erstellen](#create) Member-Funktion. Führen Sie *nicht* Aufrufen `Open` nach `Create`.  
  
 Erstellen Sie zum Öffnen einer vorhandenen Datenbank eine `CDaoDatabase` Objekt, und rufen die [öffnen](#open) Member-Funktion.  
  
 Diese Techniken datenbankauflistung des Arbeitsbereichs das DAO-Datenbankobjekt, das hinzufügt und öffnet eine Verbindung mit den Daten. Wenn Sie sich dann erstellen [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), oder [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekte für den Betrieb in der verbundenen Datenbank übergeben, die Konstruktoren für diese Objekte ein Zeiger auf Ihre `CDaoDatabase` Objekt. Wenn Sie fertig sind, verwenden die Verbindung, rufen Sie die [schließen](#close) Member funktioniert und zerstört der `CDaoDatabase` Objekt. `Close` Schließt alle Recordsets, die Sie nicht bereits geschlossen haben.  
  
## <a name="transactions"></a>Transaktionen  
 Verarbeitung von Transaktionen auf der arbeitsbereichsebene angegeben wird, finden Sie unter den [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), und [Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) Memberfunktionen der Klasse `CDaoWorkspace` .  
  
## <a name="odbc-connections"></a>ODBC-Verbindungen  
 Anfügen von externen Tabellen an einen Microsoft Jet ist die empfohlene Methode zum Arbeiten mit ODBC-Datenquellen (. MDB)-Datenbank.  
  
## <a name="collections"></a>Auflistungen  
 Jede Datenbank behält eine eigene Sammlungen von Tabledef "," Querydef "," Recordset "und" Beziehungsobjekte. Klasse `CDaoDatabase` stellt Memberfunktionen zum Bearbeiten dieser Objekte bereit.  
  
> [!NOTE]
>  Die Objekte werden nicht in der MFC-Datenbankobjekt, das in-DAO-, gespeichert. MFC stellt Klassen für Tabledef, Querydef und Recordset-Objekte jedoch nicht für die Beziehungsobjekte bereit.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="cantransact"></a>  CDaoDatabase::CanTransact  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der Datenbank Transaktionen zulässig ist.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Datenbank Transaktionen unterstützt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Transaktionen werden in der Datenbank-Arbeitsbereich verwaltet.  
  
##  <a name="canupdate"></a>  CDaoDatabase::CanUpdate  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoDatabase` Objekt lässt Updates zu.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoDatabase` Objekt lässt Updates; andernfalls 0, der angibt, entweder, die Sie übergeben "true" *bReadOnly* beim Öffnen Sie die `CDaoDatabase` Objekt oder die Datenbank selbst schreibgeschützt ist. Finden Sie unter den [öffnen](#open) Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu Datenbank-aktualisierbarkeit finden Sie im Thema "Aktualisierbare Property" in-DAO-Hilfe.  
  
##  <a name="cdaodatabase"></a>  CDaoDatabase::CDaoDatabase  
 Erstellt ein `CDaoDatabase`-Objekt.  
  
```  
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pWorkspace*  
 Ein Zeiger auf die `CDaoWorkspace` Objekt, das neue Datenbankobjekt enthält. Wenn Sie den Standardwert NULL annehmen, wird der Konstruktor erstellt eine temporäre `CDaoWorkspace` Objekt, das die Standard-DAO-Arbeitsbereich verwendet. Rufen Sie einen Zeiger auf die Arbeitsbereichsobjekt über die [M_pWorkspace](#m_pworkspace) -Datenmember.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem das Objekt erstellen, bei der Erstellung einer neuen Microsoft Jet (. MDB) Datenbank, des Objekts aufrufen [erstellen](#create) Member-Funktion. Wenn Sie hingegen sind eine vorhandene Datenbank Öffnen des Objekts aufrufen [öffnen](#open) Member-Funktion.  
  
 Wenn Sie mit dem Objekt fertig sind, sollten Sie Aufrufen seiner [schließen](#close) Member funktionieren, und entfernen Sie dann die `CDaoDatabase` Objekt.  
  
 Es können bequem zum Einbetten der `CDaoDatabase` Objekt in der Dokumentklasse.  
  
> [!NOTE]
>  Ein `CDaoDatabase` Objekt wird auch implizit erstellt, wenn Sie öffnen ein [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt ohne die Übergabe eines Zeigers auf eine vorhandene `CDaoDatabase` Objekt. Dieses Datenbankobjekt wird geschlossen, wenn Sie das Recordset-Objekt schließen.  
  
##  <a name="close"></a>  CDaoDatabase::Close  
 Rufen Sie diese Memberfunktion zum Trennen einer Datenbank, und schließen Sie alle geöffneten Recordsets Tabledefs und Querydefs der Datenbank zugeordnet.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, diese Objekte selbst schließen, bevor Sie diese Memberfunktion aufrufen. Schließen einer `CDaoDatabase` Objekt entfernt es aus der datenbankauflistung in der zugeordneten [Arbeitsbereich](../../mfc/reference/cdaoworkspace-class.md). Da `Close` nicht zerstört die `CDaoDatabase` Objekt ist, können Sie das Objekt durch Öffnen der gleichen Datenbank oder einer anderen Datenbank wiederverwenden.  
  
> [!CAUTION]
>  Rufen Sie die [Update](../../mfc/reference/cdaorecordset-class.md#update) Member-Funktion (falls es ausstehende Bearbeitungen gibt) und die `Close` Member-Funktion für alle geöffneten Recordset-Objekte, bevor Sie eine Datenbank zu schließen. Wenn Sie eine Funktion beendet wird, der deklariert [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) oder `CDaoDatabase` Objekte auf dem Stapel, die Datenbank geschlossen wird, alle nicht gespeicherten Änderungen gehen verloren, alle ausstehenden Transaktionen ein Rollback und alle ausstehenden Änderungen auf Ihre Daten gehen verloren.  
  
> [!CAUTION]
>  Wenn Sie versuchen, ein Datenbankobjekt zu schließen, während alle Recordset-Objekte geöffnet sind oder wenn Sie versuchen, ein Workspace-Objekt schließen, während alle Datenbankobjekte, die mit diesem spezifischen Arbeitsbereich gehören geöffnet sind, wird die Recordset-Objekte werden geschlossen, und alle ausstehenden Updates oder Änderungen werden auf ein Rollback. Wenn Sie versuchen, ein Workspace-Objekt schließen, während alle Datenbankobjekte, die zu der sie gehören geöffnet sind, beendet den Vorgang alle Datenbankobjekte, die auf diesem spezifischen Arbeitsbereich-Objekt, das führt nicht geschlossene Recordset-Objekte, die geschlossen werden, gehören. Wenn Sie nicht Ihr Database-Objekt schließen, meldet MFC ein Assertionsfehler in Debugbuilds.  
  
 Wenn das Datenbankobjekt, das außerhalb des Bereichs einer Funktion definiert ist, und Sie die Funktion beenden, ohne ihn zu schließen, das Datenbankobjekt, das bleibt geöffnet, bis Sie explizit geschlossen oder das Modul, in dem sie definiert ist, außerhalb des gültigen Bereichs ist.  
  
##  <a name="create"></a>  CDaoDatabase::Create  
 Erstellen Sie eine neue Microsoft Jet (. MDB) Datenbank, rufen Sie diese Memberfunktion auf, nach der Erstellung einer `CDaoDatabase` Objekt.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int dwOptions = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Ein Zeichenfolgenausdruck, der den Namen der Datenbankdatei ist, die Sie erstellen. Es kann sein den vollständigen Pfad und Dateiname, z. B. "C:\\\MYDB. MDB". Sie müssen einen Namen angeben. Wenn Sie keine Dateierweiterung angeben. MDB wird angefügt. Wenn Ihr Netzwerk die einheitliche Benennungskonvention (UNC) unterstützt, können Sie auch angeben einen Netzwerkpfad wie z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB". Nur Microsoft Jet (. Verwenden diese Memberfunktion können die Datenbankdateien MDB) erstellt werden. (Doppelter umgekehrter Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist der C++-Escape-Zeichen.)  
  
 *lpszLocale*  
 Es wurde ein Zeichenfolgenausdruck verwendet, um die Sortierreihenfolge für das Erstellen der Datenbank anzugeben. Der Standardwert ist `dbLangGeneral`. Dabei sind folgende Werte möglich:  
  
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
  
 *dwOptions*  
 Eine ganze Zahl, die eine oder mehrere Optionen angibt. Dabei sind folgende Werte möglich:  
  
- `dbEncrypt` Erstellen Sie eine verschlüsselte Datenbank an.  
  
- `dbVersion10` Erstellen Sie eine Datenbank mit der Microsoft Jet-Datenbankversion 1.0.  
  
- `dbVersion11` Erstellen Sie eine Datenbank mit Microsoft Jet-Version 1.1.  
  
- `dbVersion20` Erstellen Sie eine Datenbank mit Microsoft Jet-Version 2.0.  
  
- `dbVersion30` Erstellen Sie eine Datenbank mit Microsoft Jet-Version 3.0.  
  
 Wenn Sie die Verschlüsselungskonstante weglassen, wird eine unverschlüsselte Datenbank erstellt. Sie können nur eine Versionskonstante angeben. Wenn Sie eine Versionskonstante weglassen, wird eine Datenbank, die Version 3.0 der Microsoft Jet-Datenbank verwendet, erstellt.  
  
> [!CAUTION]
>  Wenn eine Datenbank nicht verschlüsselt ist, kann, auch wenn Sie Benutzername und Kennwort-Sicherheit implementieren, um direkt die binäre Datenträgerdatei lesen, aus der Datenbank besteht.  
  
### <a name="remarks"></a>Hinweise  
 `Create` die Datenbankdatei und das zugrunde liegende DAO-Datenbank-Objekt erstellt und initialisiert das C++-Objekt. Das Objekt wird an den zugehörigen Arbeitsbereich datenbankauflistung angefügt. Das Datenbankobjekt, das ist im geöffneten Zustand. Rufen Sie keine `Open*` nach `Create`.  
  
> [!NOTE]
>  Mit `Create`, Sie können nur Microsoft Jet erstellen (. MDB)-Datenbanken. Sie können keine ISAM-Datenbanken oder ODBC-Datenbanken erstellen.  
  
##  <a name="createrelation"></a>  CDaoDatabase::CreateRelation  
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
 *Wert*  
 Der eindeutige Name, der die Relation-Objekt. Der Name muss mit einem Buchstaben beginnen und darf maximal 40 Zeichen enthalten. Er kann Zahlen enthalten und Unterstrich-Zeichen, aber keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 *lpszTable*  
 Der Name der primären Tabelle in der Beziehung. Wenn die Tabelle nicht vorhanden ist, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 *lpszForeignTable*  
 Der Name der foreign-Tabelle in der Beziehung. Wenn die Tabelle nicht vorhanden ist, löst MFC eine Ausnahme vom Typ `CDaoException`.  
  
 *lAttributes*  
 Ein long-Wert, der Informationen über den Beziehungstyp enthält. Sie können diesen Wert verwenden, um unter anderem mit referenzieller Integrität zu erzwingen. Können Sie den bitweisen OR-Operator ( **&#124;**) eines der folgenden Werte kombinieren (solange die Kombination aus sinnvoll ist):  
  
- `dbRelationUnique` Besteht eine 1: 1-Beziehung.  
  
- `dbRelationDontEnforce` Beziehung wird nicht erzwungen (keine referenzielle Integrität).  
  
- `dbRelationInherited` Beziehung in einer nicht aktuellen Datenbank mit den beiden angefügten Tabellen vorhanden ist.  
  
- `dbRelationUpdateCascade` Updates weitergegeben werden (Weitere Informationen zu kaskadierende, siehe Hinweise).  
  
- `dbRelationDeleteCascade` Löschvorgänge werden weitergegeben.  
  
 *lpszField*  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen eines Felds in der primären Tabelle (mit dem Namen von *LpszTable*).  
  
 *lpszForeignField*  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen eines Felds in der fremden Tabelle (mit dem Namen von *LpszForeignTable*).  
  
 *relinfo*  
 Ein Verweis auf eine [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) -Objekt mit Informationen über die Beziehung, die Sie erstellen möchten.  
  
### <a name="remarks"></a>Hinweise  
 Die Beziehung kann keiner Abfrage oder einer verknüpften Tabelle aus einer externen Datenbank umfassen.  
  
 Verwenden Sie die erste Version der Funktion, wenn die Beziehung ein Feld in jeder der beiden Tabellen einschließt. Verwenden Sie die zweite Version aus, wenn die Beziehung mehrere Felder umfasst. Die maximale Anzahl von Feldern in einer Beziehung ist 14.  
  
 Diese Aktion wird ein zugrunde liegendes DAO-Relation-Objekt erstellt, aber dies ist ein Implementierungsdetail MFC, da MFC Kapselung von Beziehung Objekten innerhalb der Klasse enthalten ist `CDaoDatabase`. MFC stellt eine Klasse nicht für Beziehungen bereit.  
  
 Wenn Sie die Beziehung Attribute zum Aktivieren der Cascade-Vorgänge des Objekts festlegen, wird in die Datenbank-Engine automatisch aktualisiert oder löscht Datensätze in eine oder mehrere Tabellen aus, wenn Änderungen an verknüpfte primären Schlüssel Tabellen vorgenommen werden.  
  
 Nehmen wir beispielsweise an, dass Sie eine Cascade Delete-Beziehung zwischen einer Customers-Tabelle und eine Orders-Tabelle einrichten. Wenn Sie Datensätze aus der Customers-Tabelle löschen, werden die Datensätze in der Orders-Tabelle, die im Zusammenhang mit diesen Kunden ebenfalls gelöscht. Darüber hinaus, wenn Sie eine Cascade Delete-Beziehungen zwischen der Orders-Tabelle und anderen Tabellen erstellen, werden Datensätze aus diesen Tabellen automatisch gelöscht, wenn Sie Datensätze aus der Customers-Tabelle löschen.  
  
 Verwandte Informationen finden Sie im Thema "CreateRelation Method" in-DAO-Hilfe.  
  
##  <a name="deletequerydef"></a>  CDaoDatabase::DeleteQueryDef  
 Rufen Sie diese Memberfunktion zum Löschen der angegebenen Querydef – gespeicherte Abfrage, aus der `CDaoDatabase` QueryDefs-Auflistung des Objekts.  
  
```  
void DeleteQueryDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der Name der gespeicherten Abfrage, um zu löschen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Abfrage ist anschließend nicht mehr in der Datenbank definiert.  
  
 Informationen zum Erstellen von Querydef Objekten finden Sie in der Klasse [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Ein Querydef-Objekt wird verknüpft, mit einem bestimmten `CDaoDatabase` Objekt beim Erstellen der `CDaoQueryDef` Übergabe eines Zeigers auf das Datenbankobjekt, das Objekt.  
  
##  <a name="deleterelation"></a>  CDaoDatabase::DeleteRelation  
 Rufen Sie diese Memberfunktion zum Löschen einer vorhandenen Beziehung aus das Datenbankobjekt, das die Relations-Auflistung.  
  
```  
void DeleteRelation(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der Name des zu löschenden Beziehung.  
  
### <a name="remarks"></a>Hinweise  
 Danach ist Sie die Beziehung nicht mehr vorhanden.  
  
 Verwandte Informationen finden Sie im Thema "-Methode Delete" in-DAO-Hilfe.  
  
##  <a name="deletetabledef"></a>  CDaoDatabase::DeleteTableDef  
 Rufen Sie diese Memberfunktion zum Löschen der angegebenen Tabelle und alle darin enthaltenen Daten aus der `CDaoDatabase` TableDefs-Auflistung des Objekts.  
  
```  
void DeleteTableDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der Name des Tabledef löschen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Tabelle wird anschließend nicht mehr in der Datenbank definiert.  
  
> [!NOTE]
>  Seien Sie vorsichtig sein, nicht auf Systemtabellen zu löschen.  
  
 Informationen zum Erstellen von Tabledef Objekten finden Sie in der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Ein Tabledef-Objekt wird verknüpft, mit einem bestimmten `CDaoDatabase` Objekt beim Erstellen der `CDaoTableDef` Übergabe eines Zeigers auf das Datenbankobjekt, das Objekt.  
  
 Verwandte Informationen finden Sie im Thema "-Methode Delete" in-DAO-Hilfe.  
  
##  <a name="execute"></a>  CDaoDatabase::Execute  
 Rufen Sie diese Memberfunktion zum Ausführen einer Aktionsabfrage aus, oder führen eine SQL-Anweisung für die Datenbank an.  
  
```  
void Execute(
    LPCTSTR lpszSQL,  
    int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszSQL*  
 Zeiger auf eine Null-terminierte Zeichenfolge, die mit einem gültigen SQL‑Befehl ausgeführt.  
  
 *nOptions*  
 Eine ganze Zahl, die Optionen in Bezug auf die Integrität der Abfrage angibt. Können Sie den bitweisen OR-Operator ( **&#124;**) eine der folgenden Konstanten kombiniert (sofern sinnvoll ist die Kombination aus – beispielsweise würden Sie nicht kombinieren `dbInconsistent` mit `dbConsistent`):  
  
- `dbDenyWrite` Schreibberechtigung auf anderen Benutzern verweigert.  
  
- `dbInconsistent` (Standard) Inkonsistente Updates.  
  
- `dbConsistent` Einheitliche Aktualisierungen.  
  
- `dbSQLPassThrough` SQL Pass-Through. Bewirkt, dass die SQL-Anweisung für die Verarbeitung einer ODBC-Datenquelle übergeben werden soll.  
  
- `dbFailOnError` Das Rollback erst dann aktualisiert, wenn ein Fehler auftritt.  
  
- `dbSeeChanges` Generieren Sie einen Laufzeitfehler, wenn ein anderer Benutzer die Daten geändert werden, die Sie bearbeiten.  
  
> [!NOTE]
>  Wenn beide `dbInconsistent` und `dbConsistent` enthalten sind oder wenn keines von beiden enthalten ist, wird das Ergebnis ist die Standardeinstellung. Eine Erläuterung dieser Konstanten sind finden Sie im Thema "Execute-Methode" in-DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 `Execute` funktioniert nur bei Aktionsabfragen oder Pass-Through-SQL-Abfragen, die keine Ergebnisse zurückgegeben werden. Es funktioniert nicht für select-Abfragen, die Datensätze zurückgeben.  
  
 Eine Definition sowie die Informationen zur Aktionsabfragen finden Sie unter den Themen "Query-Aktion" und "Execute-Methode" in-DAO-Hilfe.  
  
> [!TIP]
>  Erhält eine syntaktisch richtige SQL-Anweisung und die entsprechenden Berechtigungen, die `Execute` Memberfunktion nicht selbst fehlerhaft, wenn keine einzelne Zeile geändert oder gelöscht werden kann. Aus diesem Grund verwenden Sie immer die `dbFailOnError` option bei Verwendung der `Execute` Memberfunktion versucht, eine Aktualisierung ausführen oder die Abfrage löschen. Diese Option bewirkt, dass MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md) und ein Rollback für alle erfolgreichen Änderungen aus, wenn eines der betroffenen Datensätze sind gesperrt und kann nicht aktualisiert oder gelöscht. Beachten Sie, die Sie, immer aufrufen können `GetRecordsAffected` angezeigt, wie viele Datensätze betroffen sind.  
  
 Rufen Sie die [GetRecordsAffected](#getrecordsaffected) Memberfunktion das Database-Objekt, um zu bestimmen, die Anzahl der Datensätze, die die letzte betroffen `Execute` aufrufen. Z. B. `GetRecordsAffected` gibt Informationen über die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt, wenn eine Abfrage ausführen. Die Anzahl die zurückgegebenen spiegeln sich nicht auf Änderungen in verknüpften Tabellen auf, wenn Cascade aktualisiert oder löscht wirksam sind.  
  
 `Execute` ein Recordset wird nicht zurückgegeben werden. Mithilfe von `Execute` auf einer Abfrage, die Datensätze auswählt bewirkt, dass MFC eine Ausnahme vom Typ `CDaoException`. (Es gibt keine `ExecuteSQL` Memberfunktion, die analog zu `CDatabase::ExecuteSQL`.)  
  
##  <a name="getconnect"></a>  CDaoDatabase::GetConnect  
 Rufen Sie diese Memberfunktion zum Abrufen der Verbindungszeichenfolge zur Verbindung der `CDaoDatabase` Objekt in eine ODBC- oder ISAM-Datenbank.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Verbindungszeichenfolge, wenn [öffnen](#open) wurde erfolgreich auf eine ODBC-Datenquelle aufgerufen wird, andernfalls eine leere Zeichenfolge. Für eine Microsoft Jet (. MDB) Datenbank, die Zeichenfolge ist immer leer, wenn Sie sie für die Verwendung mit festgelegt die `dbSQLPassThrough` Option der Verwendung der [Execute](#execute) Memberfunktion oder öffnen Sie ein Recordset verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge enthält Informationen über die Quelle eine geöffnete Datenbank oder einer Datenbank in einer Pass-Through-Abfrage verwendet. Die Verbindungszeichenfolge besteht aus einer Datenbank-Typspezifizierer und NULL oder mehr Parameter, die durch Semikolons getrennt ein.  
  
> [!NOTE]
>  Verwenden die MFC-DAO-Klassen zum Verbinden mit einer Datenquelle über ODBC ist weniger effizient als das Herstellen einer Verbindung über einer angefügten Tabelle.  
  
> [!NOTE]
>  Die Verbindungszeichenfolge wird zum Übergeben zusätzlicher Informationen auf ODBC und nach Bedarf bestimmte ISAM-Treiber verwendet. Es ist nicht für verwendet werden. MDB-Datenbanken. Für Microsoft Jet-Datenbank-Basistabellen, die Verbindungszeichenfolge ist eine leere Zeichenfolge ("") mit Ausnahme von für eine SQL-Pass-Through-Abfrage Verwendung wie beschrieben unter den oben genannten zurückgegeben Wert.  
  
 Finden Sie unter den [öffnen](#open) Member-Funktion, eine Beschreibung, wie die Verbindungszeichenfolge erstellt wird. Sobald die Verbindungszeichenfolge, in festgelegt wurde der `Open` -Aufruf können später damit können Sie um die Einstellung, um zu bestimmen, der Typ, der Pfad, der Benutzer-ID, Kennwort oder ODBC-Datenquelle der Datenbank zu überprüfen.  
  
##  <a name="getname"></a>  CDaoDatabase::GetName  
 Rufen Sie diese Memberfunktion um den Namen der aktuell geöffneten Datenbank, die den Namen einer vorhandenen Datenbank-Datei ist oder der Name einer registrierten ODBC-Datenquelle abrufen.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den vollständigen Pfad und Dateinamen der Datenbank, wenn erfolgreich; andernfalls ein leeres [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihr Netzwerk die einheitliche Benennungskonvention (UNC) unterstützt, können Sie auch einen Netzwerkpfad angeben, z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelter umgekehrter Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist der C++-Escape-Zeichen.)  
  
 Sie könnten z. B. diesen Namen in einer Überschrift anzuzeigen. Wenn während der Name abgerufen wird, wird ein Fehler auftritt, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
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
  
##  <a name="getquerydefcount"></a>  CDaoDatabase::GetQueryDefCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Abfragen, die in der Datenbank QueryDefs-Auflistung definiert.  
  
```  
short GetQueryDefCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Abfragen, die in der Datenbank definiert.  
  
### <a name="remarks"></a>Hinweise  
 `GetQueryDefCount` ist nützlich, wenn Sie alle Querydefs in der QueryDefs-Auflistung durchlaufen müssen. Um Informationen über eine bestimmte Abfrage in der Auflistung zu erhalten, finden Sie unter [GetQueryDefInfo](#getquerydefinfo).  
  
##  <a name="getquerydefinfo"></a>  CDaoDatabase::GetQueryDefInfo  
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
 *nIndex*  
 Der Index der vordefinierten Abfrage in der Datenbank QueryDefs-Auflistung, für die Suche nach Index.  
  
 *querydefinfo*  
 Ein Verweis auf eine [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 *dwInfoOptions*  
 Optionen, die angeben, welche Informationen das Recordset abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit was sie die Funktion führen, die das Recordset zurückgegeben werden sollen:  
  
- AFX_DAO_PRIMARY_INFO (Standard)-Namen, Typ  
  
- Primäre AFX_DAO_SECONDARY_INFO Informationen plus: Erstellungsdatum, Datum der letzten Aktualisierung, gibt Datensätze zurück, aktualisierbar  
  
- AFX_DAO_ALL_INFO primären und sekundären Informationen plus: SQL, Connect, Timeoutfehlers warten soll.  
  
 *Wert*  
 Eine Zeichenfolge, die mit dem Namen einer Abfrage, die in der Datenbank, für die Suche nach dem Namen definiert.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Versionen der Funktion werden bereitgestellt, sodass Sie eine Abfrage nach Index in der Datenbank QueryDefs-Auflistung oder durch den Namen der Abfrage auswählen können.  
  
 Eine Beschreibung der Informationen in zurückgegebenen *Querydefinfo*, finden Sie unter den [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie eine Ebene Informationen anfordern, erhalten Sie alle vorherigen Ebenen sowie Informationen.  
  
##  <a name="getquerytimeout"></a>  CDaoDatabase::GetQueryTimeout  
 Rufen Sie diese Memberfunktion zum Abrufen der aktuellen Anzahl der Sekunden, Anmeldefehler, bevor nachfolgende Vorgänge in der verbundenen Datenbank ein erfolgt Timeout.  
  
```  
short GetQueryTimeout();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein short Integer, der den Timeoutwert in Sekunden enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorgang kann aufgrund von Netzwerkproblemen für den Zugriff, übermäßige Abfrage Verarbeitungszeit und usw. Timeout. Während die Einstellung aktiviert ist, sondern alle offenen, neu hinzufügen, aktualisieren und delete-Vorgänge für alle zugeordneten Recordsets `CDaoDatabase` Objekt. Sie können die aktuelle Timeouteinstellung ändern, durch den Aufruf [SetQueryTimeout](#setquerytimeout). Ändern den Timeoutwert für Abfragen für ein Recordset nach Öffnen ändert sich nicht auf den Wert für das Recordset aus. Beispielsweise wird bei nachfolgenden [verschieben](../../mfc/reference/cdaorecordset-class.md#move) Vorgänge verwenden Sie den neuen Wert nicht. Standardmäßig ist der Wert wird anfangs festgelegt, wenn die Datenbank-Engine initialisiert wird.  
  
 Der Standardwert für die Abfragetimeouts stammt aus der Windows-Registrierung. Liegt keine registrierungseinstellung, ist der Standardwert 60 Sekunden. Nicht alle Datenbanken unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, erfolgt kein timeout und die Kommunikation mit der Datenbank möglicherweise nicht mehr reagiert. Dieses Verhalten kann während der Entwicklung nützlich sein. Wenn der Aufruf fehlschlägt, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Verwandte Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" in-DAO-Hilfe.  
  
##  <a name="getrecordsaffected"></a>  CDaoDatabase::GetRecordsAffected  
 Rufen Sie diese Memberfunktion zum Ermitteln der Anzahl der vom letzten Aufruf des betroffenen Datensätze der [Execute](#execute) Member-Funktion.  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine lange ganze Zahl, die die Anzahl der betroffenen Datensätze enthält.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert enthält, die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt, indem eine Abfrage ausführen mit `Execute`. Die Anzahl die zurückgegebenen spiegeln sich nicht auf Änderungen in verknüpften Tabellen auf, wenn Cascade aktualisiert oder löscht wirksam sind.  
  
 Verwandte Informationen finden Sie im Thema "RecordsAffected-Eigenschaft" in-DAO-Hilfe.  
  
##  <a name="getrelationcount"></a>  CDaoDatabase::GetRelationCount  
 Rufen Sie diese Memberfunktion, um die Anzahl der Beziehungen zwischen Tabellen in der Datenbank abzurufen.  
  
```  
short GetRelationCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.  
  
### <a name="remarks"></a>Hinweise  
 `GetRelationCount` ist nützlich, wenn Sie alle definierten Beziehungen in der Datenbank Relations-Auflistung durchlaufen müssen. Um Informationen über eine bestimmte Beziehung in der Auflistung zu erhalten, finden Sie unter [GetRelationInfo](#getrelationinfo).  
  
 Um das Konzept der eine Beziehung zu veranschaulichen, sollten Sie in einer Lieferantentabelle und eine Produkttabelle, die eine 1: n Beziehung aufweisen kann. In dieser Beziehung kann ein Lieferant mehr als ein Produkt angeben. Andere Beziehungen sind 1: 1- und m: n.  
  
##  <a name="getrelationinfo"></a>  CDaoDatabase::GetRelationInfo  
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
 *nIndex*  
 Der Index des in der Datenbank Relations-Auflistung, für die Suche anhand des Indexes die Relation-Objekt.  
  
 *relinfo*  
 Ein Verweis auf eine [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 *dwInfoOptions*  
 Optionen, die angeben, welche Informationen über die Beziehung abgerufen werden. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion, die über die Beziehung zurück verursachen:  
  
- AFX_DAO_PRIMARY_INFO (Standard), Tabelle, Foreign Namenstabelle  
  
- Feldinformationen AFX_DAO_SECONDARY_INFO Attribute  
  
 Die Feldinformationen ist eine [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) -Objekt, das die Felder aus der primären Tabelle, die in der Beziehung beteiligten enthält.  
  
 *Wert*  
 Eine Zeichenfolge, die mit dem Namen der Relation-Objekt, für die Suche anhand des Namens.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Versionen dieser Funktion ermöglichen den Zugriff entweder anhand des Indexes oder anhand des Namens. Eine Beschreibung der Informationen in zurückgegebenen *Relinfo*, finden Sie unter den [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie auch Informationen an alle vorherigen Ebenen sowie an.  
  
> [!NOTE]
>  Wenn Sie die Beziehung Attribute zum Aktivieren der Cascade-Vorgänge des Objekts festlegen (`dbRelationUpdateCascades` oder `dbRelationDeleteCascades`), die Microsoft Jet-Datenbank-Engine automatisch aktualisiert oder löscht Datensätze in einem oder mehreren anderen Tabellen aus, wenn Änderungen im Zusammenhang Primärschlüssel Tabellen. Nehmen wir beispielsweise an, dass Sie eine Cascade Delete-Beziehung zwischen einer Customers-Tabelle und eine Orders-Tabelle einrichten. Wenn Sie Datensätze aus der Customers-Tabelle löschen, werden die Datensätze in der Orders-Tabelle, die im Zusammenhang mit diesen Kunden ebenfalls gelöscht. Darüber hinaus, wenn Sie eine Cascade Delete-Beziehungen zwischen der Orders-Tabelle und anderen Tabellen erstellen, werden Datensätze aus diesen Tabellen automatisch gelöscht, wenn Sie Datensätze aus der Customers-Tabelle löschen.  
  
##  <a name="gettabledefcount"></a>  CDaoDatabase:: GetTableDefCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Tabellen in der Datenbank definiert.  
  
```  
short GetTableDefCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in der Datenbank definierten Tabledefs.  
  
### <a name="remarks"></a>Hinweise  
 `GetTableDefCount` ist nützlich, wenn Sie alle Tabledefs in der Datenbank TableDefs-Auflistung durchlaufen müssen. Um Informationen zu einer bestimmten Tabelle in der Auflistung zu erhalten, finden Sie unter [GetTableDefInfo](#gettabledefinfo).  
  
##  <a name="gettabledefinfo"></a>  CDaoDatabase:: GetTableDefInfo  
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
 *nIndex*  
 Der Index des Objekts Tabledef in der Datenbank TableDefs-Auflistung, für die Suche nach Index.  
  
 *tabledefinfo*  
 Ein Verweis auf eine [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 *dwInfoOptions*  
 Optionen, die angeben, welche Informationen in der Tabelle abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion, die über die Beziehung zurück verursachen:  
  
- AFX_DAO_PRIMARY_INFO (Standard) ein, die aktualisiert werden kann, Attribute  
  
- Primäre AFX_DAO_SECONDARY_INFO Informationen plus: Erstellungsdatum, letzte Aktualisierung, Name der Quelltabelle, verbinden  
  
- AFX_DAO_ALL_INFO primären und sekundären Informationen plus: Anzahl der Datensätze Validierungsregel Validierung von Text,  
  
 *Wert*  
 Der Name des Objekts Tabledef, für die Suche anhand des Namens.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Versionen der Funktion werden bereitgestellt, sodass Sie eine Tabelle nach Index in der Datenbank TableDefs-Auflistung oder durch den Namen der Tabelle auswählen können.  
  
 Eine Beschreibung der Informationen in zurückgegebenen *Tabledefinfo*, finden Sie unter den [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.  
  
> [!NOTE]
>  Die Option AFX_DAO_ALL_INFO bietet Informationen, die langsame abgerufen werden können. In diesem Fall die Datensätze in der Tabelle zählen möglicherweise sehr viel Zeit beanspruchen, wenn viele Datensätze vorhanden sind.  
  
##  <a name="getversion"></a>  CDaoDatabase::GetVersion  
 Rufen Sie diese Memberfunktion zum Ermitteln der Version der Microsoft Jet-Datenbankdatei an.  
  
```  
CString GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der die Version der Datenbankdatei mit dem Objekt verbundenen angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert stellt die Versionsnummer im Format "Hauptversion.Nebenversion"; z. B. "3.0". Die Versionsnummer des Produkts (z. B. "3.0") besteht aus der Versionsnummer (3), einem Punkt und die Versionsnummer (0). Die Versionen bis Datum sind, 1.0, 1.1, 2.0 und 3.0.  
  
 Verwandte Informationen finden Sie im Thema "Version-Eigenschaft" in-DAO-Hilfe.  
  
##  <a name="isopen"></a>  CDaoDatabase::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoDatabase` -Objekts für eine Datenbank derzeit geöffnet ist.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoDatabase` Objekt derzeit geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pdaodatabase"></a>  CDaoDatabase::m_pDAODatabase  
 Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO-Datenbank-Objekt zugrunde liegenden der `CDaoDatabase` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Zeiger, wenn Sie die DAO-Schnittstelle direkt zugreifen möchten.  
  
 Informationen zum Aufrufen von DAO direkt finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
##  <a name="m_pworkspace"></a>  CDaoDatabase::m_pWorkspace  
 Enthält einen Zeiger auf die [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) -Objekt, das Datenbankobjekt enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Zeiger, wenn Sie direkt auf den Arbeitsbereich zugreifen müssen – beispielsweise, um Verweise auf andere Datenbankobjekte in der datenbankauflistung des Arbeitsbereichs zu erhalten.  
  
##  <a name="open"></a>  CDaoDatabase::Open  
 Sie müssen diese Member-Funktion, um eine neu erstellte initialisieren Aufrufen `CDaoDatabase` Objekt, das eine vorhandene Datenbank darstellt.  
  
```  
virtual void Open(
    LPCTSTR lpszName,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Ein Zeichenfolgenausdruck mit dem Namen einer vorhandenen Microsoft Jet (. MDB)-Datei. Wenn der Dateiname eine Erweiterung verfügt, ist jedoch erforderlich. Wenn Ihr Netzwerk die einheitliche Benennungskonvention (UNC) unterstützt, können Sie auch angeben einen Netzwerkpfad wie z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelter umgekehrter Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist der C++-Escape-Zeichen.)  
  
 Zu berücksichtigende Aspekte bei Verwendung von *Wert*. Wenn sie:  
  
-   Bezieht sich auf eine Datenbank, die bereits geöffnet ist, für den exklusiven Zugriff von einem anderen Benutzer, die MFC-löst eine Ausnahme vom Typ ist [CDaoException](../../mfc/reference/cdaoexception-class.md). Abfangen von dieser Ausnahme aus, um Ihre Benutzer wissen, dass die Datenbank nicht verfügbar ist.  
  
-   Ist eine leere Zeichenfolge ("") und *LpszConnect* "ODBC;", wird ein Dialogfeld, das Auflisten aller registrierter ODBC-Datenquellennamen wird angezeigt, damit der Benutzer eine Datenbank auswählen kann. Vermeiden Sie direkte Verbindungen mit ODBC-Datenquellen; Verwenden Sie stattdessen einer angefügten Tabelle.  
  
-   Andernfalls verweist nicht auf eine vorhandene Datenbank oder eine gültige ODBC-Datenquellennamen, MFC-löst eine Ausnahme vom Typ `CDaoException`.  
  
> [!NOTE]
>  Weitere Informationen über DAO-Fehlercodes finden Sie unter den DAOERR. H-Datei. Verwandte Informationen finden Sie im Thema "Abfangbarer Datenzugriffsfehlern" in-DAO-Hilfe.  
  
 *bExclusive*  
 Ein boolescher Wert, der TRUE ist, wenn die Datenbank ist für die exklusive (nicht freigegeben) und "false" geöffnet werden, wenn die Datenbank ist für den gemeinsamen Zugriff geöffnet werden. Wenn Sie dieses Argument weglassen, wird die Datenbank für den gemeinsamen Zugriff geöffnet.  
  
 *bReadOnly*  
 Ein boolescher Wert, der TRUE ist, wenn die Datenbank ist für schreibgeschützten Zugriff und "false" geöffnet werden, wenn die Datenbank ist für Lese-/Schreibzugriff geöffnet werden. Wenn Sie dieses Argument weglassen, wird die Datenbank für Lese-/Schreibzugriff geöffnet. Alle abhängigen Recordsets erben dieses Attribut.  
  
 *lpszConnect*  
 Ein Zeichenfolgenausdruck, der zum Öffnen der Datenbank verwendet wird. Diese Zeichenfolge bildet die ODBC eine Verbindung herstellen Argumente. Sie müssen die exklusive und Read-only-Argumente zum Bereitstellen einer Quellzeichenfolge angeben. Wenn die Datenbank Microsoft Jet-Datenbank (. (MDB), die diese Zeichenfolge ist leer (""). Die Syntax für den Standardwert – **_T**("") – enthält die Portabilität für Unicode und ANSI-builds Ihrer Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 `Open` Ordnet die Datenbank mit dem zugrunde liegenden DAO-Objekt. Sie können das Datenbankobjekt, das keine Recordset, Tabledef oder Querydef-Objekte erstellen, bis sie initialisiert ist. `Open` Fügt das Datenbankobjekt, das den zugehörigen Arbeitsbereich datenbankauflistung an.  
  
 Verwenden Sie die Parameter wie folgt:  
  
-   Wenn Sie eine Microsoft Jet öffnen (. MDB)-Datenbank die *Wert* Parameter, und übergeben Sie eine leere Zeichenfolge für die *LpszConnect* Parameter oder übergeben Sie ein Kennwortzeichenfolge im Format "; PWD = Password ", wenn die Datenbank ein Kennwort geschützt ist (. MDB nur Datenbanken).  
  
-   Wenn Sie eine ODBC-Datenquelle öffnen, übergeben Sie eine gültige ODBC-Verbindungszeichenfolge in *LpszConnect* und einer leeren Zeichenfolge in *Wert*.  
  
 Verwandte Informationen finden Sie im Thema "OpenDatabase Method" in-DAO-Hilfe.  
  
> [!NOTE]
>  Für eine bessere Leistung beim Zugriff auf externe Datenbanken, einschließlich ISAM-Datenbanken und ODBC-Datenquellen, wird empfohlen, dass Sie externe Tabellen in einer Microsoft Jet-Engine-Datenbank anfügen (. MDB) anstatt eine direkte Verbindung mit der Datenquelle.  
  
 Es ist möglich, dass ein Verbindungsversuch zu einem Timeout, wenn Sie z. B. der DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch fehlschlägt, `Open` löst eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Die verbleibenden Hinweise gelten nur für die ODBC-Datenbank:  
  
 Wenn die Datenbank eine ODBC-Datenbank und die Parameter in ist Ihre `Open` Aufruf enthalten keine ausreichende Informationen zum Herstellen die Verbindung, die der ODBC-Treiber öffnet ein Dialogfeld, um die erforderlichen Informationen vom Benutzer zu erhalten. Beim Aufruf `Open`, Ihre Verbindungszeichenfolge *LpszConnect*, befindet sich privat und ist verfügbar durch Aufrufen der [GetConnect](#getconnect) Member-Funktion.  
  
 Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf `Open` zum Abrufen von Informationen aus der Benutzer, z. B. ein Kennwort, klicken Sie dann auf die Verbindungszeichenfolge, die Sie, um übergeben diese Informationen hinzufügen `Open`. Oder Sie können Zeit sparen der Verbindungszeichenfolge (z. B. in der Windows-Registrierung. übergeben) daher es das nächste können Sie Ihre Anwendungsaufrufe `Open` auf eine `CDaoDatabase` Objekt.  
  
 Können Sie auch die Verbindungszeichenfolge für mehrere Ebenen von anmeldeautorisierung (jeweils für einen anderen `CDaoDatabase` Objekt) oder um andere datenbankspezifischen Informationen zu übermitteln.  
  
##  <a name="setquerytimeout"></a>  CDaoDatabase::SetQueryTimeout  
 Rufen Sie diese Memberfunktion, um die Standardanzahl von Sekunden, bevor nachfolgende Vorgänge in der verbundenen Datenbank-Timeout Gerätedaten zu überschreiben.  
  
```  
void SetQueryTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 *nSeconds*  
 Die Anzahl der Sekunden, bevor der abfrageversuch einer ist ein Timeout aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorgang kann aufgrund von Access-Netzwerkprobleme, Verarbeitungszeit übermäßig viele Abfragen usw. Timeout. Rufen Sie `SetQueryTimeout` vor dem Öffnen des Recordsets oder vor dem Aufrufen des Recordsets [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [Update](../../mfc/reference/cdaorecordset-class.md#update), oder [löschen](../../mfc/reference/cdaorecordset-class.md#delete) Memberfunktionen, wenn Sie die Abfrage ändern möchten. Der Timeoutwert. Die Einstellung wirkt sich auf alle nachfolgenden [öffnen](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`, `Update`, und `Delete` Aufrufe an alle zugeordneten Recordsets `CDaoDatabase` Objekt. Ändern den Timeoutwert für Abfragen für ein Recordset nach Öffnen ändert sich nicht auf den Wert für das Recordset aus. Beispielsweise wird bei nachfolgenden [verschieben](../../mfc/reference/cdaorecordset-class.md#move) Vorgänge verwenden Sie den neuen Wert nicht.  
  
 Der Standardwert für die Abfragetimeouts beträgt 60 Sekunden. Nicht alle Datenbanken unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, erfolgt kein timeout die Kommunikation mit der Datenbank möglicherweise nicht mehr reagiert. Dieses Verhalten kann während der Entwicklung nützlich sein.  
  
 Verwandte Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" in-DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
