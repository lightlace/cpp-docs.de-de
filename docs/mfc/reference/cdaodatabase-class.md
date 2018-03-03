---
title: CDaoDatabase-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 48646e0635098aceea957f93015a5de93515096d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|Erstellt ein `CDaoDatabase`-Objekt. Rufen Sie **öffnen** auf das Objekt mit einer Datenbank herzustellen.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](#cantransact)|Gibt einen Wert ungleich NULL, wenn die Datenbank Transaktionen unterstützt.|  
|[CDaoDatabase::CanUpdate](#canupdate)|Gibt NULL zurück, wenn die `CDaoDatabase` Objekt ist aktualisierbar (schreibgeschützt).|  
|[CDaoDatabase::Close](#close)|Schließt die Verbindung mit der Datenbank.|  
|[CDaoDatabase::Create](#create)|Das zugrunde liegende DAO-Datenbankobjekt erstellt und initialisiert die `CDaoDatabase` Objekt.|  
|[CDaoDatabase::CreateRelation](#createrelation)|Definiert eine neue Beziehung zwischen den Tabellen in der Datenbank an.|  
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|Löscht eine Querydef-Objekt, das in der Datenbank QueryDefs-Auflistung gespeichert.|  
|[CDaoDatabase::DeleteRelation](#deleterelation)|Löscht eine vorhandene Beziehung zwischen Tabellen in der Datenbank an.|  
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|Löscht die Definition einer Tabelle in der Datenbank. Dadurch werden die tatsächliche Tabelle und alle zugehörigen Daten gelöscht.|  
|[CDaoDatabase::Execute](#execute)|Führt eine Abfrage an. Aufrufen von **Execute** für eine Abfrage, die Ergebnisse zurückgibt, eine Ausnahme auslöst.|  
|[CDaoDatabase::GetConnect](#getconnect)|Gibt die Verbindungszeichenfolge zur Verbindung der `CDaoDatabase` Objekt in einer Datenbank. Für ODBC verwendet.|  
|[CDaoDatabase::GetName](#getname)|Gibt den Namen der Datenbank, die derzeit in Verwendung zurück.|  
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|Gibt die Anzahl der Abfragen, die für die Datenbank definiert.|  
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|Informationen zu einer angegebenen, in der Datenbank definierten Abfrage zurückgegeben.|  
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|Gibt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge Abfragen durch einen Timeout beendet. Wirkt sich auf alle nachfolgenden öffnen, neue hinzufügen, aktualisieren und Bearbeiten von Vorgängen und anderen Vorgängen in ODBC-Datenquellen (nur) wie z. B. **Execute** aufrufen.|  
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|Gibt die Anzahl der Datensätze, die von der letzten Aktualisierung betroffenen bearbeiten oder das Hinzufügen oder durch einen Aufruf von **Execute**.|  
|[CDaoDatabase::GetRelationCount](#getrelationcount)|Gibt die Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.|  
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|Gibt Informationen zu einer angegebenen Beziehung zwischen Tabellen in der Datenbank definiert.|  
|[CDaoDatabase:: GetTableDefCount](#gettabledefcount)|Gibt die Anzahl der Tabellen in der Datenbank definiert.|  
|[CDaoDatabase:: GetTableDefInfo](#gettabledefinfo)|Gibt Informationen zu einer angegebenen Tabelle in der Datenbank zurück.|  
|[CDaoDatabase::GetVersion](#getversion)|Gibt die Version des Datenbankmoduls, die der Datenbank zugeordnet.|  
|[CDaoDatabase::IsOpen](#isopen)|Gibt NULL zurück, wenn die `CDaoDatabase` -Objekt aktuell mit einer Datenbank verbunden ist.|  
|[CDaoDatabase::Open](#open)|Stellt eine Verbindung mit einer Datenbank her.|  
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|Legt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge (für nur ODBC-Datenquellen) Abfragen durch einen Timeout beendet. Wirkt sich auf alle nachfolgenden öffnen, neue hinzufügen, Update- und Löschvorgänge.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|Ein Zeiger auf das zugrunde liegende DAO-Datenbankobjekt.|  
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|Ein Zeiger auf die [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt, das von der Datenbank und definiert die Transaktionsprotokoll-Speicherplatz.|  
  
## <a name="remarks"></a>Hinweise  
 Informationen zu den unterstützten Datenbankformaten finden Sie unter der [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) Memberfunktion. Sie haben eine oder mehrere `CDaoDatabase` Objekte, die in einem bestimmten "Arbeitsbereich" dargestellte aktiv zu einem Zeitpunkt eine [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt. Der Arbeitsbereich verwaltet eine Auflistung von geöffneten Datenbankobjekten, die aus der datenbankauflistung aufgerufen.  
  
> [!NOTE]
>  Die MFC-DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf ODBC. Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Klasse `CDaoDatabase` stellt eine Schnittstelle, die ähnlich dem Konzept der ODBC-Klasse [CDatabase](../../mfc/reference/cdatabase-class.md). Der Hauptunterschied besteht darin, die `CDatabase` greift auf das DBMS durch Open Database Connectivity (ODBC) und einem ODBC-Treiber für diese DBMS. `CDaoDatabase`greift auf Daten über eine (Datenzugriffsobjekt) basierend auf der Microsoft Jet-Datenbankmodul. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC; die DAO-basierten Klassen können Daten, einschließlich der ODBC-Treiber, über eigene Datenbankmodul zugreifen. Die DAO-basierten Klassen unterstützen auch (Data Definition Language, Datendefinitionssprache)-Vorgänge, z. B. das Hinzufügen von Tabellen über die Klassen ohne DAO direkt aufrufen.  
  
## <a name="usage"></a>Verwendung  
 Sie können Datenbankobjekte implizit, bei der Erstellung des Recordset-Objekte erstellen. Aber Sie können Datenbankobjekte auch explizit erstellen. Verwenden eine vorhandene Datenbank explizit mit `CDaoDatabase`, führen Sie eine der folgenden:  
  
-   Erstellen einer `CDaoDatabase` Objekt, das die Übergabe eines Zeigers auf ein offenes [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt.  
  
-   Oder erstellen Sie eine `CDaoDatabase` Objekt ohne Angabe des Arbeitsbereichs (MFC-erstellt ein temporärer Arbeitsbereich-Objekt).  
  
 So erstellen eine neue Microsoft Jet (. MDB)-Datenbank, erstellen eine `CDaoDatabase` Objekt, und rufen die [erstellen](#create) Memberfunktion. Führen Sie *nicht* Aufrufen **öffnen** nach **erstellen**.  
  
 Zum Öffnen einer vorhandenen Datenbank erstellen eine `CDaoDatabase` Objekt, und rufen die [öffnen](#open) Memberfunktion.  
  
 Eine beliebige Technik hängt von den DAO-Datenbankobjekt an datenbankauflistung für den Arbeitsbereich und öffnet eine Verbindung mit den Daten. Wenn Sie erstellen dann [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), oder [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekte für Vorgänge für die verbundene Datenbank übergeben, die Konstruktoren für diese Objekte einem Zeiger auf die `CDaoDatabase` Objekt. Aufrufen, wenn Sie fertig sind, verwenden die Verbindung, die [schließen](#close) Member-Funktion und zerstört der `CDaoDatabase` Objekt. **Schließen** schließt alle Recordsets, die Sie zuvor nicht geschlossen.  
  
## <a name="transactions"></a>Transaktionen  
 Transaktionsverarbeitung für die Datenbank auf der Ebene Arbeitsbereich angegeben wird, finden Sie unter der [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), und [Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) Memberfunktionen der Klasse `CDaoWorkspace` .  
  
## <a name="odbc-connections"></a>ODBC-Verbindungen  
 Die empfohlene Methode zum Arbeiten mit ODBC-Datenquellen ist, können Sie externe Tabellen einer Microsoft Jet zuordnen (. MDB)-Datenbank.  
  
## <a name="collections"></a>Auflistungen  
 Jede Datenbank behält eine eigene Sammlungen von Tabledef, Querydef Recordset und Beziehungsobjekte. Klasse `CDaoDatabase` stellt Memberfunktionen zum Bearbeiten von diesen Objekten bereit.  
  
> [!NOTE]
>  Die Objekte werden nicht in der MFC-Datenbankobjekt über DAO, gespeichert. MFC stellt Klassen für Tabledef Querydef und Recordset-Objekte, jedoch nicht für Beziehungsobjekte bereit.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="cantransact"></a>CDaoDatabase::CanTransact  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Datenbank Transaktionen zulässt.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Datenbank Transaktionen unterstützt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Transaktionen werden in der Datenbank-Arbeitsbereich verwaltet.  
  
##  <a name="canupdate"></a>CDaoDatabase::CanUpdate  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoDatabase` Objekt lässt Updates.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoDatabase` Objekt lässt Updates; andernfalls 0, der angibt, entweder, den Sie übergeben **"true"** in `bReadOnly` beim Öffnen Sie die `CDaoDatabase` Objekt oder die Datenbank selbst schreibgeschützt ist. Finden Sie unter der [öffnen](#open) Memberfunktion.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu Datenbank-aktualisierbarkeit finden Sie unter "Aktualisierbare Property" in der DAO-Hilfe.  
  
##  <a name="cdaodatabase"></a>CDaoDatabase::CDaoDatabase  
 Erstellt ein `CDaoDatabase`-Objekt.  
  
```  
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pWorkspace*  
 Ein Zeiger auf die `CDaoWorkspace` -Objekt, das die neue Datenbankobjekt enthält. Wenn Sie den Standardwert übernehmen **NULL**, der Konstruktor erstellt eine temporäre `CDaoWorkspace` -Objekt, das die DAO-Standardarbeitsbereich verwendet. Sie erhalten einen Zeiger auf das Arbeitsbereichsobjekt im, über die [M_pWorkspace](#m_pworkspace) -Datenmember.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, wenn Sie eine neue Microsoft Jet erstellen (. MDB)-Datenbank, rufen Sie des Objekts [erstellen](#create) Memberfunktion. Wenn Sie hingegen sind Öffnen einer vorhandenen Datenbank des Objekts aufrufen [öffnen](#open) Memberfunktion.  
  
 Wenn Sie mit dem Objekt abgeschlossen haben, sollten Sie Aufrufen seiner [schließen](#close) Member-Funktion, und entfernen Sie dann die `CDaoDatabase` Objekt.  
  
 Möglicherweise praktisch sein, das Einbetten der `CDaoDatabase` Objekt in Ihrem Dokumentklasse.  
  
> [!NOTE]
>  Ein `CDaoDatabase` -Objekt wird auch implizit erstellt, wenn Sie öffnen ein [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt ohne die Übergabe eines Zeigers auf eine vorhandene `CDaoDatabase` Objekt. Dieses Datenbankobjekts ist geschlossen, wenn Sie das Recordset-Objekt schließen.  
  
##  <a name="close"></a>CDaoDatabase::Close  
 Rufen Sie diese Memberfunktion zum Trennen einer Datenbank, und schließen Sie alle geöffneten Recordsets, Tabledefs und Querydefs der Datenbank zugeordnet.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, diese Objekte selbst schließen, bevor Sie diese Memberfunktion aufrufen. Schließen einer `CDaoDatabase` Objekt entfernt es aus der datenbankauflistung in der zugeordneten [Arbeitsbereich](../../mfc/reference/cdaoworkspace-class.md). Da **schließen** nicht zerstört die `CDaoDatabase` -Objekt, Sie können jedoch stattdessen das wiederverwenden, indem Sie derselben Datenbank oder einer anderen Datenbank öffnen.  
  
> [!CAUTION]
>  Rufen Sie die [Update](../../mfc/reference/cdaorecordset-class.md#update) Memberfunktion (wenn es ausstehende Bearbeitungen) und die **schließen** Memberfunktion für alle geöffneten Recordset-Objekte, bevor Sie eine Datenbank schließen. Wenn Sie das Programm beenden deklariert einer funktionsrückgabewerts [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) oder `CDaoDatabase` Objekte auf dem Stapel, die Datenbank geschlossen wird, alle nicht gespeicherten Änderungen gehen verloren, alle anstehenden Transaktionen zurückgesetzt und alle ausstehenden Änderungen auf Ihre Daten verloren.  
  
> [!CAUTION]
>  Wenn Sie versuchen, ein Datenbankobjekt zu schließen, während alle Recordset-Objekte geöffnet sind, oder wenn Sie versuchen, ein Arbeitsbereichsobjekt im schließen, wenn keines der Datenbankobjekte, die mit diesem bestimmten Arbeitsbereich gehören geöffnet sind, werden diese Objekte Recordset geschlossen und alle ausstehenden Updates oder bearbeitet werden Rollback ausgeführt. Wenn Sie versuchen, ein Arbeitsbereichsobjekt im schließen, wenn keines der Datenbankobjekte, die darauf gehören geöffnet sind, beendet den Vorgang alle Datenbankobjekte, die auf dieses Objekt bestimmten Arbeitsbereich, die nicht geschlossen Recordset-Objekte, die geschlossen werden möglicherweise gehören. Wenn Sie nicht die Database-Objekt schließen, meldet MFC ein Assertionsfehler in Debugbuilds.  
  
 Wenn das Datenbankobjekt außerhalb des Bereichs einer Funktion definiert ist, und Sie die Funktion, beenden ohne ihn zu schließen, das Datenbankobjekt bleibt geöffnet, bis Sie explizit geschlossen oder geht über das Modul, in dem sie definiert ist.  
  
##  <a name="create"></a>CDaoDatabase::Create  
 So erstellen eine neue Microsoft Jet (. MDB) Datenbank, rufen Sie diese Memberfunktion auf, wenn Sie erstellt haben, eine `CDaoDatabase` Objekt.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int dwOptions = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeichenfolgenausdruck, der den Namen der Datenbankdatei ist, die Sie erstellen. Er kann den vollständigen Pfad und Dateiname, z. B. "C:\\\MYDB. MDB". Sie müssen einen Namen angeben. Wenn Sie keine Dateierweiterung angeben. MDB wird angefügt. Wenn Ihr Netzwerk die uniform Namenskonvention (UNC) unterstützt, Sie können auch angeben einen Netzwerkpfad, z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB". Nur Microsoft Jet (. MDB)-Datenbankdateien können diese Memberfunktion mit erstellt werden. (Doppelte Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist die C++-Escape-Zeichen.)  
  
 `lpszLocale`  
 Ein Zeichenfolgenausdruck, der zum Angeben der Sortierreihenfolge für das Erstellen der Datenbank verwendet wird. Der Standardwert ist **DbLangGeneral**. Dabei sind folgende Werte möglich:  
  
- **DbLangGeneral** Englisch, Deutsch, Französisch, Portugiesisch, Italienisch und Modern Spanisch  
  
- **DbLangArabic** Arabisch  
  
- **DbLangCyrillic** Russisch  
  
- **DbLangCzech** Tschechisch  
  
- **DbLangDutch** Niederländisch  
  
- **DbLangGreek** Griechisch  
  
- **DbLangHebrew** Hebräisch  
  
- **DbLangHungarian** Ungarisch  
  
- **DbLangIcelandic** Isländisch  
  
- **DbLangNordic** Nordeuropäische Sprachen (Microsoft Jet-Datenbank-Engine nur Version 1.0)  
  
- **DbLangNorwdan** Norwegisch und Dänisch  
  
- **DbLangPolish** Polnisch  
  
- **DbLangSpanish** Spanisch (traditionell)  
  
- **DbLangSwedfin** Tschechisch und Finnisch  
  
- **DbLangTurkish** Türkisch  
  
 `dwOptions`  
 Eine ganze Zahl, die eine oder mehrere Optionen angibt. Dabei sind folgende Werte möglich:  
  
- **DbEncrypt** erstellen eine verschlüsselte Datenbank.  
  
- **dbVersion10** erstellen Sie eine Datenbank mit Microsoft Jet-Version 1.0.  
  
- **dbVersion11** erstellen Sie eine Datenbank mit Microsoft Jet-Version 1.1.  
  
- **dbVersion20** erstellen Sie eine Datenbank mit Microsoft Jet-Version 2.0.  
  
- **dbVersion30** erstellen Sie eine Datenbank mit Microsoft Jet-Version 3.0.  
  
 Wenn Sie die Verschlüsselungskonstante weglassen, wird eine nicht verschlüsselte Datenbank erstellt. Sie können nur eine Versionskonstante angeben. Wenn Sie eine Versionskonstante weglassen, wird eine Datenbank, die Version 3.0 der Microsoft Jet-Datenbank verwendet, erstellt.  
  
> [!CAUTION]
>  Wenn eine Datenbank nicht verschlüsselt ist, kann, selbst wenn die Implementierung der Sicherheit für Benutzername und Kennwort, um die binäre Datenträgerdatei direkt zu lesen, aus der Datenbank besteht.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** die Datenbankdatei und das zugrunde liegende DAO-Datenbankobjekt erstellt und initialisiert das C++-Objekt. Das Objekt wird an den zugeordneten Arbeitsbereich datenbankauflistung angefügt. Das Datenbankobjekt ist in einem geöffneten Status; Rufen Sie nicht **öffnen** nach **erstellen**.  
  
> [!NOTE]
>  Mit **erstellen**, Sie können nur Microsoft Jet erstellen (. Datenbanken, MDB). Sie können keine ISAM-Datenbanken oder ODBC-Datenbanken erstellen.  
  
##  <a name="createrelation"></a>CDaoDatabase::CreateRelation  
 Rufen Sie diese Memberfunktion, um eine Beziehung zwischen einer oder mehrere Felder in einer primären Tabelle in der Datenbank und ein oder mehrere Felder in einer Fremdschlüsseltabelle (einer anderen Tabelle in der Datenbank) herzustellen.  
  
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
 `lpszName`  
 Der eindeutige Name der Relation-Objekt. Der Name muss mit einem Buchstaben beginnen und darf maximal 40 Zeichen enthalten. Er kann Zahlen enthalten und Unterstrich-Zeichen jedoch keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 `lpszTable`  
 Der Name der primären Tabelle in der Beziehung. Wenn die Tabelle nicht vorhanden ist, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 `lpszForeignTable`  
 Der Name der fremden Tabelle in der Beziehung. Wenn die Tabelle nicht vorhanden ist, löst MFC eine Ausnahme vom Typ `CDaoException`.  
  
 `lAttributes`  
 Ein long-Wert, der Informationen über den Beziehungstyp enthält. Sie können diesen Wert verwenden, um das Erzwingen der referenziellen Integrität, unter anderem. Können Sie den bitweisen OR-Operator ( **&#124;**) eines der folgenden Werte kombiniert (solange die Kombination sinnvoll ist):  
  
- **DbRelationUnique** Beziehung 1: 1 ist.  
  
- **DbRelationDontEnforce** Beziehung wird nicht erzwungen (keine referenzielle Integrität).  
  
- **DbRelationInherited** Beziehung in einer-Datenbank, die die beiden angefügten Tabellen enthält.  
  
- **DbRelationUpdateCascade** Updates kaskadiert werden (Weitere Informationen über die überlappend, finden Sie unter "Hinweise").  
  
- **DbRelationDeleteCascade** Löschvorgänge werden weitergegeben.  
  
 *lpszField*  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge, die mit dem Namen eines Felds in der primären Tabelle (mit dem Namen von `lpszTable`).  
  
 *lpszForeignField*  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge, die mit dem Namen eines Felds in der fremden Tabelle (mit dem Namen von `lpszForeignTable`).  
  
 *relinfo*  
 Ein Verweis auf eine [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Objekt, das enthält Informationen über die Beziehung, die Sie erstellen möchten.  
  
### <a name="remarks"></a>Hinweise  
 Die Beziehung kann keiner Abfrage oder einer angefügten Tabelle aus einer externen Datenbank umfassen.  
  
 Verwenden Sie die erste Version der Funktion, wenn die Beziehung zwischen einem Feld in den beiden Tabellen einschließt. Verwenden Sie die zweite Version aus, wenn die Beziehung zwischen mehreren Feldern umfasst. Die maximale Anzahl von Feldern in einer Beziehung ist 14.  
  
 Diese Aktion wird ein zugrunde liegendes DAO Relation-Objekt erstellt, aber dies ist ein Implementierungsdetail MFC, da MFC Kapselung der Beziehungsobjekte innerhalb der Klasse enthalten ist `CDaoDatabase`. MFC stellt eine Klasse keine für Beziehungen bereit.  
  
 Wenn Sie die Beziehung Objektattribute für die Cascade-Vorgänge aktivieren festlegen, wird das Datenbankmodul automatisch aktualisiert oder Datensätze in einer oder mehreren Tabellen löscht, wenn Änderungen an verknüpften primären Schlüssel Tabellen vorgenommen werden.  
  
 Nehmen Sie z. B. an, dass eine Cascade Delete-Beziehung zwischen einer Customers-Tabelle und eine Orders-Tabelle zu erstellen. Wenn Sie Datensätze aus der Customers-Tabelle löschen, werden die Datensätze in der Orders-Tabelle, die im Zusammenhang mit diesen Kunden ebenfalls gelöscht. Darüber hinaus, wenn Sie eine Cascade Delete-Beziehungen zwischen der Orders-Tabelle und anderen Tabellen einrichten, werden Datensätze aus diesen Tabellen automatisch gelöscht, wenn Sie Datensätze aus der Customers-Tabelle löschen.  
  
 Verwandte Informationen finden Sie im Thema "CreateRelation Method" DAO-Hilfe.  
  
##  <a name="deletequerydef"></a>CDaoDatabase::DeleteQueryDef  
 Rufen Sie diese Memberfunktion zum Löschen der angegebenen Querydef – gespeicherte Abfrage – aus der `CDaoDatabase` QueryDefs-Auflistung des Objekts.  
  
```  
void DeleteQueryDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name der gespeicherten Abfragen zu löschen.  
  
### <a name="remarks"></a>Hinweise  
 Danach wird die Abfrage nicht mehr in der Datenbank definiert.  
  
 Informationen zum Querydef-Objekte erstellen, finden Sie in der Klasse [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Ein Querydef-Objekt wird verknüpft, mit einem bestimmten `CDaoDatabase` Objekt beim Erstellen der `CDaoQueryDef` Objekt Übergabe eines Zeigers auf das Datenbankobjekt.  
  
##  <a name="deleterelation"></a>CDaoDatabase::DeleteRelation  
 Rufen Sie diese Memberfunktion zum Löschen einer vorhandenen Beziehungs aus das Datenbankobjekt Relations-Auflistung.  
  
```  
void DeleteRelation(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name des zu löschenden Beziehung.  
  
### <a name="remarks"></a>Hinweise  
 Im Anschluss vorhanden ist die Beziehung nicht mehr ein.  
  
 Verwandte Informationen finden Sie im Thema "Methode Delete", DAO-Hilfe.  
  
##  <a name="deletetabledef"></a>CDaoDatabase::DeleteTableDef  
 Rufen Sie diese Memberfunktion zum Löschen der angegebenen Tabelle und alle zugehörigen Daten aus der `CDaoDatabase` TableDefs-Auflistung des Objekts.  
  
```  
void DeleteTableDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name des Tabledef zu löschen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Tabelle wird anschließend nicht mehr in der Datenbank definiert.  
  
> [!NOTE]
>  Seien Sie vorsichtig, nicht auf Systemtabellen zu löschen.  
  
 Informationen zum Tabledef-Objekte erstellen, finden Sie in der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Ein Tabledef-Objekt wird verknüpft, mit einem bestimmten `CDaoDatabase` Objekt beim Erstellen der `CDaoTableDef` Objekt Übergabe eines Zeigers auf das Datenbankobjekt.  
  
 Verwandte Informationen finden Sie im Thema "Methode Delete", DAO-Hilfe.  
  
##  <a name="execute"></a>CDaoDatabase::Execute  
 Rufen Sie diese Memberfunktion zum Ausführen einer Aktionsabfrage, oder führen eine SQL-Anweisung für die Datenbank an.  
  
```  
void Execute(
    LPCTSTR lpszSQL,  
    int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSQL`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit einem gültigen SQL‑Befehl ausführen.  
  
 `nOptions`  
 Eine ganze Zahl, die Optionen, die im Zusammenhang mit der die Integrität der Abfrage angibt. Können Sie den bitweisen OR-Operator ( **&#124;**) eine der folgenden Konstanten kombiniert (sofern sinnvoll ist die Kombination aus – beispielsweise würden Sie nicht kombiniert **DbInconsistent** mit **DbConsistent**):  
  
- **DbDenyWrite** verweigern, anderen Benutzern Schreibberechtigung.  
  
- **DbInconsistent** inkonsistente Updates (Standard).  
  
- **DbConsistent** konsistenter Updates.  
  
- **DbSQLPassThrough** SQL Pass-Through. Bewirkt, dass die SQL-Anweisung für die Verarbeitung einer ODBC-Datenquelle übergeben werden soll.  
  
- **DbFailOnError** Rollback für Updates aus, wenn ein Fehler auftritt.  
  
- **DbSeeChanges** generieren einen Laufzeitfehler, wenn ein anderer Benutzer Daten ändert, die Sie bearbeiten.  
  
> [!NOTE]
>  Wenn beide **DbInconsistent** und **DbConsistent** enthalten sind oder wenn keine enthalten ist, wird das Ergebnis ist die Standardeinstellung. Eine Erläuterung der folgenden Konstanten finden Sie im Thema "Execute-Methode" DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 **Führen Sie** funktioniert nur bei Aktionsabfragen oder SQL-Pass-Through-Abfragen, die keine Ergebnisse zurückgeben. Es funktioniert nicht für select-Abfragen, die Datensätze zurück.  
  
 Eine Definition und die Informationen zur Aktionsabfragen finden Sie unter den Themen "Abfrage" und "Execute-Methode" DAO-Hilfe.  
  
> [!TIP]
>  Erhält eine syntaktisch richtige SQL-Anweisung und die erforderlichen Berechtigungen, die **Execute** Memberfunktion nicht fehl, auch wenn keine einzelne Zeile geändert oder gelöscht werden kann. Verwenden Sie daher immer die **DbFailOnError** option bei Verwendung der **Execute** Memberfunktion versucht, führen Sie ein Update oder eine Abfrage löschen. Diese Option bewirkt, dass MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md) und ein Rollback für alle erfolgreichen Änderungen aus, wenn keines der betroffenen Datensätze gesperrt sind und nicht aktualisiert oder gelöscht. Beachten Sie, die Sie, immer aufrufen können `GetRecordsAffected` sehen, wie viele Datensätze betroffen sind.  
  
 Rufen Sie die [GetRecordsAffected](#getrecordsaffected) Memberfunktion des Database-Objekts, um zu bestimmen, die Anzahl der Datensätze, die von der letzten betroffenen **Execute** aufrufen. Beispielsweise `GetRecordsAffected` gibt Informationen über die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt, wenn eine Abfrage ausführen. Die zurückgegebene Anzahl der widerspiegelt Änderungen in verknüpften Tabellen, wenn Cascade aktualisiert oder löscht wirksam sind nicht.  
  
 **Führen Sie** kein Recordset zurückgibt. Mit **Execute** auf einer Abfrage, die Datensätze auswählt bewirkt, dass MFC eine Ausnahme vom Typ `CDaoException`. (Es ist keine `ExecuteSQL` Memberfunktion, die analog zu `CDatabase::ExecuteSQL`.)  
  
##  <a name="getconnect"></a>CDaoDatabase::GetConnect  
 Rufen Sie diese Memberfunktion zum Abrufen der Verbindung verwendeten Verbindungszeichenfolge die `CDaoDatabase` Objekt in eine ODBC- oder ISAM-Datenbank.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Verbindungszeichenfolge, wenn [öffnen](#open) wurde erfolgreich auf eine ODBC-Datenquelle aufgerufen wurde, andernfalls eine leere Zeichenfolge. Für eine Microsoft Jet (. MDB) Datenbank, die Zeichenfolge ist immer leer, wenn Sie es für die Verwendung mit Festlegen der **DbSQLPassThrough** Option verwendet wird, mit der [Execute](#execute) Memberfunktion oder öffnen Sie ein Recordset verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge enthält Informationen über die Quelle eine geöffnete Datenbank oder einer Datenbank in einer Pass-Through-Abfrage verwendet. Die Verbindungszeichenfolge besteht aus einem Datenbank-Typspezifizierer und NULL oder mehr Parameter, die durch Semikolons getrennt ein.  
  
> [!NOTE]
>  Verwenden die MFC-DAO-Klassen für die Verbindung mit einer Datenquelle über ODBC ist weniger effizient als das Herstellen einer Verbindung über einer angefügten Tabelle.  
  
> [!NOTE]
>  Die Verbindungszeichenfolge wird verwendet, um zusätzliche Informationen auf ODBC und bestimmte ISAM-Treiber nach Bedarf zu übergeben. Es ist nicht für verwendet werden. MDB-Datenbanken. Für Microsoft Jet-Datenbank der Basistabellen, die Verbindungszeichenfolge ist eine leere Zeichenfolge ("") außer wenn Sie es für eine SQL-Pass-Through-Abfrage verwenden unter Rückgabewert oben beschriebenen.  
  
 Finden Sie unter der [öffnen](#open) Memberfunktion eine Beschreibung, wie die Verbindungszeichenfolge erstellt wird. Sobald die Verbindungszeichenfolge, in festgelegt wurde der **öffnen** Aufruf, später können Sie es überprüfen Sie die Einstellung bestimmt den Typ, den Pfad, die Benutzer-ID, Kennwort oder ODBC-Datenquelle der Datenbank.  
  
##  <a name="getname"></a>CDaoDatabase::GetName  
 Rufen Sie diese Memberfunktion um den Namen der aktuell geöffneten Datenbank, die den Namen einer vorhandenen Datenbank-Datei ist oder der Name einer registrierten ODBC-Datenquelle abzurufen.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den vollständigen Pfad und Dateinamen der Datenbank, wenn erfolgreich; andernfalls ein leeres [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihr Netzwerk die uniform Namenskonvention (UNC) unterstützt, können Sie auch einen Netzwerkpfad angeben, z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelte Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist die C++-Escape-Zeichen.)  
  
 Sie sollten z. B. diesen Namen in einer Überschrift anzuzeigen. Wenn ein Fehler auftritt, während der Name abgerufen wird, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
> [!NOTE]
>  Für eine bessere Leistung, wenn externe Datenbanken zugegriffen wird, es wird empfohlen, dass Sie externe Tabellen in einer Microsoft Jet-Datenbank anfügen (. MDB) anstatt direkt mit der Datenquelle.  
  
 Der Datenbanktyp wird angegeben, indem Sie die Datei oder das Verzeichnis, das der angegebene Pfad an, wie folgt zeigt:  
  
|PathName verweist auf...|Datenbanktyp|  
|--------------------------|-------------------|  
|. MDB-Datei|Microsoft Jet-Datenbank (Microsoft Access)|  
|Verzeichnis, enthält. DBF-Dateien|dBASE-Datenbank|  
|Verzeichnis, enthält. XLS-Datei|Microsoft Excel-Datenbank|  
|Verzeichnis, enthält. PDX-Dateien|Paradox-Datenbank|  
|Verzeichnis mit den Datenbankdateien ordnungsgemäß formatierten Text enthält.|Datenbank im Text-format|  
  
 Für ODBC-Datenbanken, wie SQL Server und Oracle identifiziert die Datenbank-Verbindungszeichenfolge einen Datenquellennamen (DSN), der von ODBC registriert ist.  
  
##  <a name="getquerydefcount"></a>CDaoDatabase::GetQueryDefCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Abfragen, die in der Datenbank QueryDefs-Auflistung definiert.  
  
```  
short GetQueryDefCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Abfragen, die in der Datenbank definiert.  
  
### <a name="remarks"></a>Hinweise  
 `GetQueryDefCount`ist nützlich, wenn Sie alle Querydefs in der QueryDefs-Auflistung durchlaufen müssen. Um Informationen über eine bestimmte Abfrage in der Auflistung zu erhalten, finden Sie unter [GetQueryDefInfo](#getquerydefinfo).  
  
##  <a name="getquerydefinfo"></a>CDaoDatabase::GetQueryDefInfo  
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
 `nIndex`  
 Der Index der vordefinierten Abfrage in der Datenbank QueryDefs-Auflistung, für die Suche nach Index.  
  
 *querydefinfo*  
 Ein Verweis auf eine [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen das Recordset abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion für das Recordset zurückgegeben verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Typ  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Datum erstellt, Datum der letzten Aktualisierung, gibt Datensätze, aktualisierbar  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: "SQL" oder "Verbindung herstellen, Timeoutfehlers warten soll.  
  
 `lpszName`  
 Eine Zeichenfolge, die mit dem Namen einer Abfrage in der Datenbank, für die Suche nach dem Namen definiert.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Versionen der Funktion bereitgestellt werden, damit Sie eine Abfrage über einen Index in der Datenbank QueryDefs-Auflistung oder durch den Namen der Abfrage auswählen können.  
  
 Eine Beschreibung der Informationen zurückgegeben *Querydefinfo*, finden Sie unter der [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie eine Ebene Informationen anfordern, erhalten Sie alle vorherigen Ebenen sowie Informationen.  
  
##  <a name="getquerytimeout"></a>CDaoDatabase::GetQueryTimeout  
 Rufen Sie diese Memberfunktion zum Abrufen der aktuellen Anzahl von Sekunden Anmeldefehler, bevor nachfolgende Vorgänge in der verbundenen Datenbank ein erfolgt Timeout.  
  
```  
short GetQueryTimeout();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine kurze ganze Zahl, die den Timeoutwert in Sekunden enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorgang möglicherweise aufgrund von Netzwerkproblemen-Zugriff, übermäßige Abfrage Verarbeitungszeit und usw. Timeout. Während die Einstellung aktiviert ist, sondern alle offenen, neue hinzufügen, aktualisieren und Löschvorgänge für alle zugeordneten Recordsets `CDaoDatabase` Objekt. Sie können die Timeouteinstellung für die aktuelle ändern, durch den Aufruf [SetQueryTimeout](#setquerytimeout). Ändern den Timeoutwert für Abfragen für ein Recordset nach Öffnen ändert sich nicht auf den Wert für das Recordset. Beispielsweise wird bei nachfolgenden [verschieben](../../mfc/reference/cdaorecordset-class.md#move) Vorgänge verwenden Sie den neuen Wert nicht. Der Standardwert wird anfangs festgelegt werden, wenn das Datenbankmodul initialisiert wird.  
  
 Der Standardwert für Abfragetimeouts stammt aus der Windows-Registrierung. Ist keine registrierungseinstellung, ist der Standardwert 60 Sekunden. Nicht alle Datenbanken unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, tritt kein Timeout. und die Kommunikation mit der Datenbank möglicherweise nicht mehr reagiert. Dieses Verhalten kann während der Entwicklung nützlich sein. Wenn der Aufruf fehlschlägt, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Verwandte Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getrecordsaffected"></a>CDaoDatabase::GetRecordsAffected  
 Rufen Sie diese Memberfunktion zum Ermitteln der Anzahl der vom letzten Aufruf der betroffenen Datensätze der [Execute](#execute) Memberfunktion.  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine lange ganze Zahl, die die Anzahl der betroffenen Datensätze enthält.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert enthält die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt, indem eine Abfrage mit ausführen **Execute**. Die zurückgegebene Anzahl der widerspiegelt Änderungen in verknüpften Tabellen, wenn Cascade aktualisiert oder löscht wirksam sind nicht.  
  
 Verwandte Informationen finden Sie im Thema "RecordsAffected-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getrelationcount"></a>CDaoDatabase::GetRelationCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.  
  
```  
short GetRelationCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.  
  
### <a name="remarks"></a>Hinweise  
 **GetRelationCount** ist hilfreich, wenn alle definierten Beziehungen in der Datenbank Relations-Auflistung durchlaufen werden sollen. Informationen zu einer bestimmten Beziehung in der Auflistung zu erhalten, finden Sie unter [GetRelationInfo](#getrelationinfo).  
  
 Um das Konzept einer Beziehung zu veranschaulichen, sollten Sie in einer Lieferantentabelle und eine Produkttabelle, eine 1: n-Beziehung aufweisen kann. In dieser Beziehung kann ein Lieferant mehr als ein Produkt angeben. Andere Beziehungen sind 1: 1- und m: n.  
  
##  <a name="getrelationinfo"></a>CDaoDatabase::GetRelationInfo  
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
 `nIndex`  
 Der Index des Objekts Beziehung in der Datenbank Relations-Auflistung, für die Suche nach Index.  
  
 *relinfo*  
 Ein Verweis auf eine [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über die Beziehung abgerufen werden. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion, die über die Beziehung zurück verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name der Tabelle, Fremdtabelle  
  
- `AFX_DAO_SECONDARY_INFO`Attribute, Feldinformationen  
  
 Die Feldinformationen ist ein [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) Objekt, das die Felder aus der primären Tabelle in der Beziehung beteiligten enthält.  
  
 `lpszName`  
 Eine Zeichenfolge mit dem Namen des Relation-Objekt, für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Versionen dieser Funktion ermöglichen den Zugriff über einen Index oder anhand des Namens. Eine Beschreibung der Informationen zurückgegeben *Relinfo*, finden Sie unter der [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie ebenfalls Informationen auf alle vorherigen Ebenen sowie an.  
  
> [!NOTE]
>  Wenn Sie die Beziehung Objektattribute für die Cascade-Vorgänge aktivieren festgelegt ( **DbRelationUpdateCascades** oder **DbRelationDeleteCascades**), das Microsoft Jet-Datenbankmodul automatisch aktualisiert wird, oder Datensätze in einer oder mehreren Tabellen löscht, wenn Änderungen an verknüpften primären Schlüssel Tabellen vorgenommen werden. Nehmen Sie z. B. an, dass eine Cascade Delete-Beziehung zwischen einer Customers-Tabelle und eine Orders-Tabelle zu erstellen. Wenn Sie Datensätze aus der Customers-Tabelle löschen, werden die Datensätze in der Orders-Tabelle, die im Zusammenhang mit diesen Kunden ebenfalls gelöscht. Darüber hinaus, wenn Sie eine Cascade Delete-Beziehungen zwischen der Orders-Tabelle und anderen Tabellen einrichten, werden Datensätze aus diesen Tabellen automatisch gelöscht, wenn Sie Datensätze aus der Customers-Tabelle löschen.  
  
##  <a name="gettabledefcount"></a>CDaoDatabase:: GetTableDefCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Tabellen in der Datenbank definiert.  
  
```  
short GetTableDefCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in der Datenbank definierten Tabledefs.  
  
### <a name="remarks"></a>Hinweise  
 `GetTableDefCount`ist nützlich, wenn Sie alle Tabledefs in der Datenbank TableDefs-Auflistung durchlaufen müssen. Um Informationen zu einer bestimmten Tabelle in der Auflistung zu erhalten, finden Sie unter [GetTableDefInfo](#gettabledefinfo).  
  
##  <a name="gettabledefinfo"></a>CDaoDatabase:: GetTableDefInfo  
 Rufen Sie diese Memberfunktion, um verschiedene Arten von Informationen zu einer Tabelle in der Datenbank definierten zu erhalten.  
  
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
 `nIndex`  
 Der Index des Objekts Tabledef in der Datenbank TableDefs-Auflistung, für die Suche nach Index.  
  
 `tabledefinfo`  
 Ein Verweis auf eine [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über die Tabelle abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion, die über die Beziehung zurück verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, aktualisiert werden kann, Attribute  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Datum erstellt, die letzte Aktualisierung, Name der Quelltabelle, verbinden  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: Anzahl der Datensätze Validierungsregel, Text zu,  
  
 `lpszName`  
 Der Name des Objekts Tabledef für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Versionen der Funktion bereitgestellt werden, damit Sie eine Tabelle über einen Index in der Datenbank TableDefs-Auflistung oder durch den Namen der Tabelle auswählen können.  
  
 Eine Beschreibung der Informationen zurückgegeben `tabledefinfo`, finden Sie unter der [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.  
  
> [!NOTE]
>  Die `AFX_DAO_ALL_INFO` Option enthält Informationen, die langsame abgerufen werden kann. In diesem Fall konnte der Datensätze in der Tabelle gezählt sehr zeitaufwändig sein, wenn viele Datensätze vorhanden sind.  
  
##  <a name="getversion"></a>CDaoDatabase::GetVersion  
 Rufen Sie diese Memberfunktion, um die Version der Microsoft Jet-Datenbankdatei zu ermitteln.  
  
```  
CString GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der die Version der Datenbankdatei mit dem Objekt verbundenen angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert stellt die Versionsnummer im Format "größer.kleiner"; beispielsweise "3.0". Die Versionsnummer des Produkts (z. B. "3.0") besteht aus der Versionsnummer (3), einem Punkt und die Versionsnummer (0). Die Versionen bisheriges sind 1.0, 1.1, 2.0 und 3.0.  
  
 Verwandte Informationen finden Sie im Thema "Version-Eigenschaft" DAO-Hilfe.  
  
##  <a name="isopen"></a>CDaoDatabase::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoDatabase` Objekt ist derzeit geöffnet ist, in einer Datenbank.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoDatabase` Objekt ist derzeit geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pdaodatabase"></a>CDaoDatabase::m_pDAODatabase  
 Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO-Datenbank-Objekt zugrunde liegenden der `CDaoDatabase` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie this-Zeiger, wenn Sie die DAO-Schnittstelle direkt zugreifen müssen.  
  
 Informationen zum Aufrufen von DAO direkt, finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
##  <a name="m_pworkspace"></a>CDaoDatabase::m_pWorkspace  
 Enthält einen Zeiger auf die [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) -Objekt, das das Datenbankobjekt enthält.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger verwenden, wenn Sie den Arbeitsbereich direkt zugreifen müssen, z. B. Zeiger auf andere Datenbankobjekte in den Arbeitsbereich datenbankauflistung abgerufen.  
  
##  <a name="open"></a>CDaoDatabase::Open  
 Sie müssen diese Memberfunktion zum Initialisieren einer neu erstellten Aufrufen `CDaoDatabase` Objekt, das eine vorhandene Datenbank darstellt.  
  
```  
virtual void Open(
    LPCTSTR lpszName,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeichenfolgenausdruck, der den Namen einer vorhandenen Microsoft Jet ist (. Datenbankdatei MDB). Falls der Dateiname eine Erweiterung enthält, ist erforderlich. Wenn Ihr Netzwerk die uniform Namenskonvention (UNC) unterstützt, Sie können auch angeben einen Netzwerkpfad, z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelte Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist die C++-Escape-Zeichen.)  
  
 Einige Aspekte sollten bei der Verwendung `lpszName`. Wenn sie:  
  
-   Bezieht sich auf eine Datenbank, die bereits für den exklusiven Zugriff von einem anderen Benutzer, MFC-löst eine Ausnahme des Typs geöffnet ist [CDaoException](../../mfc/reference/cdaoexception-class.md). Abfangen Sie, wird diese Ausnahme aus, um die Benutzer wissen, dass die Datenbank nicht verfügbar ist.  
  
-   Ist eine leere Zeichenfolge ("") und *LpszConnect* "ODBC;" wird ein Dialogfeld, das alle registrierte ODBC-Datenquellennamen auflisten wird angezeigt, damit der Benutzer eine Datenbank auswählen kann. Vermeiden Sie direkte Verbindungen mit ODBC-Datenquellen; Verwenden Sie stattdessen einer angefügten Tabelle.  
  
-   Andernfalls verweist nicht auf einer vorhandenen Datenbank oder eine gültige ODBC-Datenquellenname, MFC löst eine Ausnahme vom Typ `CDaoException`.  
  
> [!NOTE]
>  Weitere Informationen zu Fehlercodes für DAO finden Sie unter der DAOERR. H-Datei. Verwandte Informationen finden Sie im Thema "Abfangbarer Datenzugriff" DAO-Hilfe.  
  
 `bExclusive`  
 Ein boolescher Wert, der **"true"** Wenn die Datenbank ist für den exklusiven (Shared) Zugriff geöffnet werden und **"false"** , wenn die Datenbank ist für den gemeinsamen Zugriff geöffnet werden. Wenn Sie dieses Argument auslassen, wird die Datenbank für den gemeinsamen Zugriff geöffnet.  
  
 `bReadOnly`  
 Ein boolescher Wert, der **"true"** ist die Datenbank für schreibgeschützten Zugriff geöffnet werden und **"false"** , wenn die Datenbank ist für Lese-/Schreibzugriff geöffnet werden. Wenn Sie dieses Argument auslassen, wird die Datenbank für Lese-/Schreibzugriff geöffnet. Alle abhängigen Recordsets erben dieses Attribut.  
  
 `lpszConnect`  
 Ein Zeichenfolgenausdruck, der zum Öffnen der Datenbank verwendet wird. Diese Zeichenfolge bildet die ODBC eine Verbindung herstellen Argumente. Sie müssen die exklusive und Read-only-Argumente zum Bereitstellen einer Quellzeichenfolge angeben. Wenn die Datenbank mit einer Microsoft Jet-Datenbank ist (. MDB), die diese Zeichenfolge ist leer (""). Die Syntax für den Standardwert – **_T**("") – enthält die Portabilität für sowohl Unicode als auch ANSI builds der Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 **Open** ordnet die Datenbank mit dem zugrunde liegenden DAO-Objekt. Das Datenbankobjekt können Sie Recordset, Tabledef oder DAO Querydef-Objekte erstellen, bis es initialisiert wird. **Open** fügt der Datenbankobjekt zugeordneten Arbeitsbereich datenbankauflistung.  
  
 Verwenden Sie die Parameter wie folgt:  
  
-   Wenn Sie eine Microsoft Jet öffnen (. MDB)-Datenbank die `lpszName` Parameter und übergeben Sie eine leere Zeichenfolge für die `lpszConnect` Parameter "oder" Pass eine Kennwortzeichenfolge im Format "; PWD = Kennwort ", wenn die Datenbank ein Kennwort geschützt ist (. MDB nur Datenbanken).  
  
-   Wenn Sie eine ODBC-Datenquelle öffnen, übergeben Sie eine gültige ODBC-Verbindungszeichenfolge in `lpszConnect` und eine leere Zeichenfolge in `lpszName`.  
  
 Verwandte Informationen finden Sie im Thema "OpenDatabase Method" DAO-Hilfe.  
  
> [!NOTE]
>  Für eine bessere Leistung beim Zugriff auf externe Datenbanken, einschließlich ISAM-Datenbanken und ODBC-Datenquellen, wird empfohlen, dass Sie externe Tabellen mit einer Microsoft Jet-Datenbankmodul-Datenbank anfügen (. MDB) anstatt direkt mit der Datenquelle.  
  
 Es ist möglich, für einen Verbindungsversuch zu einem Timeout, wenn Sie z. B. die DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch nicht gelingt, **öffnen** löst eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Die verbleibenden Hinweise gelten nur für ODBC-Datenbanken:  
  
 Wenn die Datenbank ein ODBC-Datenbank und die Parameter in ist Ihre **öffnen** Aufruf enthalten keine ausreichende Informationen zum Herstellen die Verbindung, die ODBC-Treiber öffnet ein Dialogfeld, um die erforderlichen Informationen vom Benutzer zu erhalten. Beim Aufruf **öffnen**, Ihre Verbindungszeichenfolge `lpszConnect`, privat gespeichert und ist verfügbar durch Aufrufen der [GetConnect](#getconnect) Memberfunktion.  
  
 Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf **öffnen** beim Abrufen von Informationen aus der Benutzer, z. B. eines Kennworts der Verbindungszeichenfolge übergeben Sie an diese Informationen dann hinzufügen **öffnen**. Vielleicht möchten Sie Zeit sparen der Verbindungszeichenfolge übergeben (z. B. in der Windows-Registrierung), damit Sie es das nächste wiederverwenden können Ihre Anwendung Aufrufe **öffnen** auf eine `CDaoDatabase` Objekt.  
  
 Sie können auch die Verbindungszeichenfolge für mehrere Ebenen von anmeldeautorisierung (jeweils für ein anderes `CDaoDatabase` Objekt) oder um andere Datenbank-spezifische Informationen zu übermitteln.  
  
##  <a name="setquerytimeout"></a>CDaoDatabase::SetQueryTimeout  
 Rufen Sie diese Memberfunktion, um die Standardanzahl von Sekunden, bevor nachfolgende Vorgänge in der verbundenen Datenbank-Timeout zu überschreiben.  
  
```  
void SetQueryTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 `nSeconds`  
 Die Anzahl der Sekunden, bevor ein abfrageversuch ein Timeout eintritt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorgang möglicherweise aufgrund von Netzwerkzugriffsproblemen, eine übermäßige Abfrage Verarbeitungszeit usw. Timeout. Rufen Sie `SetQueryTimeout` vor dem Öffnen des Recordsets oder vor dem Aufrufen des Recordsets [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [Update](../../mfc/reference/cdaorecordset-class.md#update), oder [löschen](../../mfc/reference/cdaorecordset-class.md#delete) Memberfunktionen, wenn die Abfrage nicht geändert werden sollen Timeout-Wert. Die Einstellung wirkt sich auf alle nachfolgenden [öffnen](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`, **Update**, und **löschen** Aufrufe an alle zugeordneten Recordsets `CDaoDatabase` Objekt. Ändern den Timeoutwert für Abfragen für ein Recordset nach Öffnen ändert sich nicht auf den Wert für das Recordset. Beispielsweise wird bei nachfolgenden [verschieben](../../mfc/reference/cdaorecordset-class.md#move) Vorgänge verwenden Sie den neuen Wert nicht.  
  
 Der Standardwert für Abfragetimeouts ist 60 Sekunden. Nicht alle Datenbanken unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, tritt kein Timeout. die Kommunikation mit der Datenbank möglicherweise nicht mehr reagiert. Dieses Verhalten kann während der Entwicklung nützlich sein.  
  
 Verwandte Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
