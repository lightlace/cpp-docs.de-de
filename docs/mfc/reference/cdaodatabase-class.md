---
title: CDaoDatabase Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- database classes [C++], DAO
- CDaoDatabase class, vs. CDatabase class
- CDaoDatabase class, and workspace
- CDaoDatabase class
- CDatabase class, vs. CDaoDatabase class
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c173ea0c0132752c08504053d9b00cdec8d3f69b
ms.lasthandoff: 02/24/2017

---
# <a name="cdaodatabase-class"></a>CDaoDatabase-Klasse
Stellt eine Verbindung zu einer Datenbank dar, über welche die Daten bearbeitet werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoDatabase : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|Erstellt ein `CDaoDatabase`-Objekt. Rufen Sie **öffnen** auf das Objekt in einer Datenbank zu verbinden.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](#cantransact)|Gibt einen Wert ungleich NULL, wenn die Datenbank Transaktionen unterstützt.|  
|[CDaoDatabase::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn die `CDaoDatabase` Objekt ist aktualisierbar (schreibgeschützt).|  
|[CDaoDatabase::Close](#close)|Schließt die Verbindung mit der Datenbank.|  
|[CDaoDatabase::Create](#create)|Das zugrunde liegende DAO-Datenbankobjekt, das erstellt und initialisiert die `CDaoDatabase` Objekt.|  
|[CDaoDatabase::CreateRelation](#createrelation)|Definieren eine neue Beziehung zwischen den Tabellen in der Datenbank.|  
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|Löscht ein Querydef-Objekt, das in der Datenbank QueryDefs-Auflistung gespeichert.|  
|[CDaoDatabase::DeleteRelation](#deleterelation)|Löscht eine vorhandene Beziehung zwischen Tabellen in der Datenbank.|  
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|Löscht die Definition einer Tabelle in der Datenbank. Dies löscht die tatsächliche Tabelle und alle zugehörigen Daten.|  
|[CDaoDatabase::Execute](#execute)|Führt eine Abfrage aus. Aufrufen von **Execute** für eine Abfrage, die Ergebnisse zurückgibt, eine Ausnahme auslöst.|  
|[CDaoDatabase::GetConnect](#getconnect)|Gibt die Verbindungszeichenfolge zur Verbindung der `CDaoDatabase` Objekt in einer Datenbank. Für ODBC verwendet.|  
|[CDaoDatabase::GetName](#getname)|Gibt den Namen der Datenbank, die derzeit in Verwendung zurück.|  
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|Gibt die Anzahl der Abfragen, die für die Datenbank definiert.|  
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|Gibt Informationen zu einer bestimmten Abfrage, die in der Datenbank definiert.|  
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|Gibt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge abgefragt werden. Wirkt sich auf alle nachfolgenden öffnen, Hinzufügen neuer, aktualisieren und Vorgänge und andere Vorgänge auf ODBC-Datenquellen (nur) wie z. B. bearbeiten **Execute** aufrufen.|  
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|Gibt die Anzahl der Datensätze, die von der letzten Aktualisierung betroffen bearbeiten oder das Hinzufügen oder durch einen Aufruf von **Execute**.|  
|[CDaoDatabase::GetRelationCount](#getrelationcount)|Gibt die Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.|  
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|Gibt Informationen über eine angegebene Beziehung zwischen Tabellen in der Datenbank definiert.|  
|[CDaoDatabase:: GetTableDefCount](#gettabledefcount)|Gibt die Anzahl der Tabellen in der Datenbank definiert.|  
|[CDaoDatabase:: GetTableDefInfo](#gettabledefinfo)|Gibt Informationen zu einer angegebenen Tabelle in der Datenbank zurück.|  
|[CDaoDatabase::GetVersion](#getversion)|Gibt die Version der Datenbank-Engine, die der Datenbank zugeordnet.|  
|[CDaoDatabase::IsOpen](#isopen)|Gibt einen Wert ungleich NULL, wenn die `CDaoDatabase` -Objekt aktuell mit einer Datenbank verbunden ist.|  
|[CDaoDatabase::Open](#open)|Stellt eine Verbindung mit einer Datenbank her.|  
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|Legt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge (für nur ODBC-Datenquellen) abgefragt werden. Wirkt sich auf alle nachfolgenden öffnen, Hinzufügen neuer, update und delete-Operationen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|Ein Zeiger auf das zugrunde liegende DAO-Datenbankobjekt.|  
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|Ein Zeiger auf die [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) -Objekt, enthält die Datenbank und den Transaktionsbereich definiert.|  
  
## <a name="remarks"></a>Hinweise  
 Informationen über die Datenbankformate unterstützt, finden Sie unter der [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) Member-Funktion. Sie haben eine oder mehrere `CDaoDatabase` Objekte, die in einem bestimmten "Arbeitsbereich" dargestellte aktiv eine [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt. Der Arbeitsbereich enthält eine Auflistung von geöffneten Datenbankobjekten, die Databases-Auflistung aufgerufen.  
  
> [!NOTE]
>  Die MFC-DAO-Datenbankklassen unterscheiden sich von den ODBC-basierten MFC-Datenbankklassen. Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Klasse `CDaoDatabase` stellt eine Schnittstelle, die der ODBC-Klasse ähnelt [CDatabase](../../mfc/reference/cdatabase-class.md). Der Hauptunterschied besteht darin, die `CDatabase` greift auf das DBMS über Open Database Connectivity (ODBC) und einen ODBC-Treiber für dieses DBMS verwaltet. `CDaoDatabase`greift auf Daten über eine (Datenzugriffsobjekt) basierend auf der Microsoft Jet-Datenbankmodul. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die ODBC-basierten MFC-Klassen. DAO-basierte Klassen können Daten, einschließlich der über ODBC-Treiber, über ihre eigenen Datenbank-Engine zugreifen. DAO-basierte Klassen unterstützen auch Vorgänge (Data Definition Language, Datendefinitionssprache), z. B. das Hinzufügen von Tabellen über die Klassen ohne DAO direkt aufrufen.  
  
## <a name="usage"></a>Verwendung  
 Sie können Datenbankobjekte implizit erstellen, bei der Erstellung des Recordset-Objekte. Aber Sie können auch Datenbankobjekte explizit erstellen. Verwenden eine vorhandenen Datenbank explizit mit `CDaoDatabase`, führen Sie einen der folgenden:  
  
-   Erstellen einer `CDaoDatabase` Objekt, das einen Zeiger auf ein offenes übergeben [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt.  
  
-   Erstellen einer `CDaoDatabase` Objekt ohne Angabe des Arbeitsbereichs (MFC erstellt eine temporäre Workspace-Objekt).  
  
 Erstellen Sie eine neue Microsoft Jet (. MDB)-Datenbank, Erstellen einer `CDaoDatabase` Objekt, und rufen die [erstellen](#create) Member-Funktion. Führen Sie *nicht* Aufrufen **öffnen** nach **erstellen**.  
  
 Zum Öffnen einer vorhandenen Datenbank erstellen eine `CDaoDatabase` Objekt, und rufen die [öffnen](#open) Member-Funktion.  
  
 Diese Techniken fügt das DAO datenbankauflistung für den Arbeitsbereich und öffnet eine Verbindung mit den Daten. Wenn Sie erstellen dann [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), oder [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) -Objekte für den Betrieb in der verbundenen Datenbank den Konstruktoren für diese Objekte übergeben einen Zeiger auf die `CDaoDatabase` Objekt. Rufen Sie abschließend die Verbindung mit der [schließen](#close) Member-Funktion und Zerstören der `CDaoDatabase` Objekt. **Schließen** schließt alle Recordsets, die Sie zuvor nicht geschlossen.  
  
## <a name="transactions"></a>Transaktionen  
 Verarbeitung von Transaktionen auf der Ebene des Arbeitsbereichs angegeben wird, finden Sie unter der [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), und [Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) Memberfunktionen der Klasse `CDaoWorkspace`.  
  
## <a name="odbc-connections"></a>ODBC-Verbindungen  
 Die empfohlene Methode zum Arbeiten mit ODBC-Datenquellen Anfügen von externen Tabellen an eine Microsoft Jet ist (. MDB)-Datenbank.  
  
## <a name="collections"></a>Auflistungen  
 Jede Datenbank verwaltet eine eigene Sammlungen von Tabledef, Querydef, Recordset und Beziehungsobjekte. Klasse `CDaoDatabase` stellt Memberfunktionen zum Bearbeiten dieser Objekte bereit.  
  
> [!NOTE]
>  Die Objekte werden nicht in der MFC-Datenbankobjekt in DAO gespeichert. MFC stellt Klassen für Tabledef Querydef und Recordset-Objekte, jedoch nicht für Beziehungsobjekte bereit.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="cantransact"></a>CDaoDatabase::CanTransact  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Datenbank Transaktionen zulässt.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Datenbank Transaktionen unterstützt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Transaktionen in der Datenbank-Arbeitsbereich verwaltet werden.  
  
##  <a name="canupdate"></a>CDaoDatabase::CanUpdate  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoDatabase` Objekt kann Updates.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoDatabase` Objekt kann Updates; andernfalls 0, entweder, den Sie die Übergabe **TRUE** in `bReadOnly` Sie beim Öffnen der `CDaoDatabase` Objekt oder die Datenbank selbst schreibgeschützt ist. Finden Sie unter der [öffnen](#open) Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu Datenbank-aktualisierbarkeit finden Sie im Thema "Updatable-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="cdaodatabase"></a>CDaoDatabase::CDaoDatabase  
 Erstellt ein `CDaoDatabase`-Objekt.  
  
```  
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pWorkspace*  
 Ein Zeiger auf die `CDaoWorkspace` -Objekts, das neue Datenbankobjekt enthält. Wenn Sie den Standardwert übernehmen **NULL**, der Konstruktor erstellt eine temporäre `CDaoWorkspace` -Objekt, das den DAO-Standardarbeitsbereich verwendet. Rufen Sie einen Zeiger auf die Arbeitsbereichsobjekt über die [M_pWorkspace](#m_pworkspace) -Datenmember.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem das Objekt erstellen, wenn Sie eine neue Microsoft Jet erstellen (. MDB) Datenbank, rufen Sie die [erstellen](#create) Member-Funktion. Wenn Sie in diesem Fall sind eine vorhandene Datenbank Öffnen des Objekts aufrufen [öffnen](#open) Member-Funktion.  
  
 Wenn Sie mit dem Objekt abgeschlossen haben, sollten Sie Aufrufen seiner [schließen](#close) Member-Funktion, und löschen Sie dann die `CDaoDatabase` Objekt.  
  
 Es können bequem Einbetten der `CDaoDatabase` Objekt in der Dokumentklasse.  
  
> [!NOTE]
>  Ein `CDaoDatabase` Objekt ist auch implizit erstellt, wenn Sie öffnen ein [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ohne Übergabe eines Zeigers auf ein vorhandenes Objekt `CDaoDatabase` Objekt. Das Datenbankobjekt wird geschlossen, wenn Sie das Recordset-Objekt schließen.  
  
##  <a name="close"></a>CDaoDatabase::Close  
 Rufen Sie diese Memberfunktion zum Trennen einer Datenbank, und schließen Sie alle geöffneten Recordsets, Tabledefs und Querydefs, die der Datenbank zugeordnet.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, diese Objekte selbst schließen, bevor Sie diese Memberfunktion aufrufen. Schließen einer `CDaoDatabase` Objekt entfernt es aus der Auflistung der Datenbanken in der zugeordneten [Arbeitsbereich](../../mfc/reference/cdaoworkspace-class.md). Da **schließen** zerstört nicht das `CDaoDatabase` -Objekt, Sie können das Objekt wiederverwenden, indem der gleichen Datenbank oder eine andere Datenbank öffnen.  
  
> [!CAUTION]
>  Rufen Sie die [Update](../../mfc/reference/cdaorecordset-class.md#update) Member-Funktion (wenn es ausstehende Bearbeitungen) und die **schließen** Memberfunktion auf alle geöffneten Recordsets vor dem Schließen einer Datenbank. Wenn Sie das Programm beenden deklariert einer Funktion [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) oder `CDaoDatabase` Objekte auf dem Stapel, die Datenbank geschlossen wird, alle nicht gespeicherten Änderungen verloren, alle ausstehenden Transaktionen ein Rollback und ausstehenden Änderungen auf Ihre Daten gehen verloren.  
  
> [!CAUTION]
>  Wenn Sie versuchen, ein Datenbankobjekt zu schließen, während alle Recordset-Objekte geöffnet sind, oder wenn Sie versuchen, ein Workspace-Objekt zu schließen, wenn keines der Datenbankobjekte, die mit diesem bestimmten Arbeitsbereich gehören geöffnet sind, die Recordset-Objekte werden geschlossen und ausstehende Updates oder Änderungen werden rückgängig gemacht werden. Wenn Sie versuchen, ein Workspace-Objekt zu schließen, während alle zugehörigen Datenbankobjekte geöffnet sind, beendet den Vorgang alle Datenbankobjekte, die in dieser bestimmten Workspace-Objekt, das möglicherweise kein schließendes Recordset-Objekte, die geschlossen wird. Wenn Sie das Datenbankobjekt nicht schließen, meldet MFC ein Assertionsfehler in Debug-Builds.  
  
 Wenn das Datenbankobjekt, das außerhalb des Bereichs einer Funktion definiert ist, und Sie die Funktion verlassen, ohne die Anwendung schließen, das Datenbankobjekt bleibt geöffnet, bis Sie explizit geschlossen oder das Modul, in dem es definiert ist, außerhalb des gültigen Bereichs ist.  
  
##  <a name="create"></a>CDaoDatabase::Create  
 Erstellen Sie eine neue Microsoft Jet (. MDB) Datenbank, rufen Sie diese Memberfunktion auf, nach der Konstruktion einer `CDaoDatabase` Objekt.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int dwOptions = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeichenfolgenausdruck, der den Namen der Datenbankdatei ist, die Sie erstellen. Es kann der vollständige Pfad und Dateiname, z. B. "C:\\\MYDB. MDB". Sie müssen einen Namen angeben. Wenn Sie keine Erweiterung angeben. MDB wird angefügt. Wenn Ihr Netzwerk die einheitliche Benennungskonvention (UNC) unterstützt, Sie können auch angeben einen Netzwerkpfad wie z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB". Nur Microsoft Jet (. MDB)-Datenbankdateien können diese Memberfunktion mit erstellt werden. (Doppelte umgekehrte Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist die C++-Escape-Zeichen.)  
  
 `lpszLocale`  
 Ein Zeichenfolgenausdruck, der zum Angeben der Sortierreihenfolge zum Erstellen der Datenbank verwendet wird. Der Standardwert ist **DbLangGeneral**. Dabei sind folgende Werte möglich:  
  
- **DbLangGeneral** Englisch, Deutsch, Französisch, Portugiesisch, Italienisch und modernes Spanisch  
  
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
  
- **DbLangSwedfin** Schwedisch und Finnisch  
  
- **DbLangTurkish** Türkisch  
  
 `dwOptions`  
 Eine ganze Zahl, die eine oder mehrere Optionen angibt. Dabei sind folgende Werte möglich:  
  
- **DbEncrypt** eine verschlüsselte Datenbank erstellen.  
  
- **dbVersion10** erstellen Sie eine Datenbank mit Microsoft Jet, Version 1.0.  
  
- **dbVersion11** erstellen Sie eine Datenbank mit Microsoft Jet, Version 1.1.  
  
- **dbVersion20** erstellen Sie eine Datenbank mit Microsoft Jet, Version 2.0.  
  
- **dbVersion30** erstellen Sie eine Datenbank mit Microsoft Jet, Version 3.0.  
  
 Wenn Sie die Verschlüsselungskonstante weglassen, wird eine unverschlüsselte Datenbank erstellt. Sie können nur eine Versionskonstante angeben. Wenn Sie eine Versionskonstante weglassen, wird eine Datenbank, die das Microsoft Jet-Datenbank, Version 3.0 verwendet, erstellt.  
  
> [!CAUTION]
>  Wenn eine Datenbank nicht verschlüsselt ist, ist es möglich, auch wenn die Implementierung der Sicherheit für Benutzername und Kennwort, um die binäre Datenträgerdatei direkt zu lesen, aus die die Datenbank besteht.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** die Datenbankdatei und das zugrunde liegende DAO-Datenbankobjekt, das erstellt und initialisiert das C++-Objekt. Das Objekt wird an den zugehörigen Arbeitsbereich Databases-Auflistung angefügt. Das Datenbankobjekt ist im geöffneten Zustand. Rufen Sie **öffnen** nach **erstellen**.  
  
> [!NOTE]
>  Mit **erstellen**, Sie können nur Microsoft Jet erstellen (. MDB)-Datenbanken. Sie können keine ISAM-Datenbanken oder ODBC-Datenbanken erstellen.  
  
##  <a name="createrelation"></a>CDaoDatabase::CreateRelation  
 Rufen Sie diese Memberfunktion zum Herstellen einer Beziehung zwischen einem oder mehreren Feldern in einer primären Tabelle in der Datenbank und ein oder mehrere Felder in einer Fremdtabelle (einer anderen Tabelle in der Datenbank).  
  
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
 Der eindeutige Name der Relation-Objekt. Der Name muss mit einem Buchstaben beginnen und darf maximal 40 Zeichen enthalten. Es kann Zahlen enthalten und Unterstrich-Zeichen jedoch keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 `lpszTable`  
 Der Name der primären Tabelle in der Beziehung. Wenn die Tabelle nicht vorhanden ist, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 `lpszForeignTable`  
 Der Name der fremden Tabelle in der Beziehung. Wenn die Tabelle nicht vorhanden ist, löst MFC eine Ausnahme vom Typ `CDaoException`.  
  
 `lAttributes`  
 Ein long-Wert, der Informationen über den Beziehungstyp enthält. Sie können diesen Wert verwenden, an, unter anderem die referenzielle Integrität erzwingen. Können Sie den bitweisen OR-Operator ( **|**) einen der folgenden Werte (solange die Kombination sinnvoll) kombinieren:  
  
- **DbRelationUnique** Beziehung&1;:&1; ist.  
  
- **DbRelationDontEnforce** Beziehung wird nicht erzwungen (keine referentielle Integrität).  
  
- **DbRelationInherited** Beziehung in einer-Datenbank, die zwei angefügten Tabellen enthält.  
  
- **DbRelationUpdateCascade** Updates kaskadieren (Weitere Informationen über überlappend, siehe Hinweise).  
  
- **DbRelationDeleteCascade** Löschvorgänge werden weitergegeben.  
  
 *lpszField*  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen eines Felds in der primären Tabelle (mit dem Namen `lpszTable`).  
  
 *lpszForeignField*  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen eines Felds in der fremden Tabelle (mit dem Namen `lpszForeignTable`).  
  
 *relinfo*  
 Ein Verweis auf eine [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) -Objekt, das enthält Informationen über die Beziehung, die Sie erstellen möchten.  
  
### <a name="remarks"></a>Hinweise  
 Die Beziehung kann keiner Abfrage oder einer angefügten Tabelle aus einer externen Datenbank umfassen.  
  
 Verwenden Sie die erste Version der Funktion, wenn die Beziehung ein Feld in jeder der beiden Tabellen einschließt. Verwenden Sie die zweite Version, wenn die Beziehung zwischen mehreren Feldern umfasst. Die maximale Anzahl von Feldern in einer Beziehung ist 14.  
  
 Diese Aktion wird ein zugrunde liegende DAO-Relation-Objekt erstellt, aber dies ist ein Implementierungsdetail MFC, da MFC Kapselung der Beziehung zwischen Objekten in der Klasse enthalten ist `CDaoDatabase`. MFC stellt eine Klasse für Beziehungen keinen.  
  
 Wenn Sie die Beziehung Objektattribute Cascade-Vorgänge aktivieren festlegen, wird die Datenbank-Engine automatisch aktualisiert oder Datensätze in einer oder mehreren Tabellen löscht, wenn verknüpfte Tabellen für primäre Schlüssel geändert wird.  
  
 Nehmen wir beispielsweise an, dass Sie eine Cascade Delete-Beziehung zwischen einer Kundentabelle und einer Orders-Tabelle erstellen. Wenn Sie Datensätze aus der Customers-Tabelle löschen, werden die Datensätze in der Orders-Tabelle, die im Zusammenhang mit diesen Kunden ebenfalls gelöscht. Darüber hinaus wird Sie Cascade Delete Beziehungen zwischen der Orders-Tabelle und anderen Tabellen herstellen, werden Datensätze aus diesen Tabellen automatisch gelöscht, wenn Sie Datensätze aus der Customers-Tabelle löschen.  
  
 Verwandte Informationen finden Sie im Thema "CreateRelation Method" in der DAO-Hilfe.  
  
##  <a name="deletequerydef"></a>CDaoDatabase::DeleteQueryDef  
 Rufen Sie diese Memberfunktion zum Löschen der angegebenen Querydef – gespeicherte Abfrage – aus der `CDaoDatabase` QueryDefs-Auflistung des Objekts.  
  
```  
void DeleteQueryDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name der gespeicherten Abfrage zu löschen.  
  
### <a name="remarks"></a>Hinweise  
 Anschließend wird die Abfrage nicht mehr in der Datenbank definiert.  
  
 Informationen zum Erstellen von Querydef-Objekte, finden Sie unter Klasse [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Ein Querydef-Objekt wird mit einem bestimmten zugeordnet `CDaoDatabase` Objekt beim Erstellen der `CDaoQueryDef` Objekt Übergabe eines Zeigers auf das Datenbankobjekt.  
  
##  <a name="deleterelation"></a>CDaoDatabase::DeleteRelation  
 Rufen Sie diese Memberfunktion zum Löschen einer vorhandenen Beziehung aus der Datenbank des Objekts Relations-Auflistung.  
  
```  
void DeleteRelation(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name der zu löschenden Beziehung.  
  
### <a name="remarks"></a>Hinweise  
 Anschließend besteht die Beziehung nicht mehr.  
  
 Verwandte Informationen finden Sie im Thema "Delete-Methode" in der DAO-Hilfe.  
  
##  <a name="deletetabledef"></a>CDaoDatabase::DeleteTableDef  
 Rufen Sie diese Memberfunktion zum Löschen der angegebenen Tabelle und alle zugehörigen Daten aus der `CDaoDatabase` TableDefs-Auflistung des Objekts.  
  
```  
void DeleteTableDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name des Tabledef löschen.  
  
### <a name="remarks"></a>Hinweise  
 Anschließend wird diese Tabelle nicht mehr in der Datenbank definiert.  
  
> [!NOTE]
>  Seien Sie vorsichtig, nicht auf Systemtabellen zu löschen.  
  
 Informationen zum Tabledef-Objekte erstellen, finden Sie unter Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Ein Tabledef-Objekt wird mit einem bestimmten zugeordnet `CDaoDatabase` Objekt beim Erstellen der `CDaoTableDef` Objekt Übergabe eines Zeigers auf das Datenbankobjekt.  
  
 Verwandte Informationen finden Sie im Thema "Delete-Methode" in der DAO-Hilfe.  
  
##  <a name="execute"></a>CDaoDatabase::Execute  
 Rufen Sie diese Memberfunktion zum Ausführen einer Abfrage, oder führen eine SQL-Anweisung für die Datenbank.  
  
```  
void Execute(
    LPCTSTR lpszSQL,  
    int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSQL`  
 Zeiger auf eine Null-terminierte Zeichenfolge mit einer gültigen SQL-Befehl ausführen.  
  
 `nOptions`  
 Eine ganze Zahl, die Optionen für die Integrität der Abfrage angibt. Können Sie den bitweisen OR-Operator ( **|**) eine der folgenden Konstanten kombiniert (sofern sinnvoll ist die Kombination aus – beispielsweise würden Sie nicht kombinieren **DbInconsistent** mit **DbConsistent**):  
  
- **DbDenyWrite** verweigern Schreibberechtigung für andere Benutzer.  
  
- **DbInconsistent** inkonsistente Aktualisierungen (Standard).  
  
- **DbConsistent** einheitliche Updates.  
  
- **DbSQLPassThrough** SQL Pass-Through. Bewirkt, dass die SQL-Anweisung zur Verarbeitung an eine ODBC-Datenquelle übergeben werden.  
  
- **DbFailOnError** Rollback der Updates, wenn ein Fehler auftritt.  
  
- **DbSeeChanges** generieren einen Laufzeitfehler, wenn ein anderer Benutzer Daten ändert, die Sie bearbeiten.  
  
> [!NOTE]
>  Wenn beide **DbInconsistent** und **DbConsistent** enthalten sind oder wenn keine enthalten ist, wird das Ergebnis ist die Standardeinstellung. Eine Erläuterung dieser Konstanten finden Sie im Thema "Execute-Methode" in der DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 **Führen Sie** funktioniert nur bei Aktionsabfragen oder SQL Pass-Through-Abfragen, die keine Ergebnisse zurückgegeben werden. Es funktioniert nicht für select-Abfragen, die Datensätze zurückgeben.  
  
 Eine Definition und die Informationen zur Aktionsabfragen finden Sie unter den Themen "Aktionsabfrage" und "Execute-Methode" in der DAO-Hilfe.  
  
> [!TIP]
>  Erhält eine syntaktisch richtige SQL-Anweisung und die erforderlichen Berechtigungen, die **Execute** Memberfunktion nicht selbst fehlerhaft, wenn keine einzelne Zeile geändert oder gelöscht werden kann. Verwenden Sie daher immer die **DbFailOnError** option bei Verwendung der **Execute** Memberfunktion, führen Sie eine Aktualisierung oder eine Abfrage löschen. Diese Option bewirkt, dass MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md) und ein Rollback für alle erfolgreichen Änderungen aus, wenn keines der betroffenen Datensätze gesperrt sind und nicht aktualisiert oder gelöscht. Beachten Sie, die Sie, immer aufrufen können `GetRecordsAffected` sehen, wie viele Datensätze betroffen sind.  
  
 Rufen Sie die [GetRecordsAffected](#getrecordsaffected) -Memberfunktion des Datenbankobjekts bestimmen die Anzahl der Datensätze, die von der letzten betroffen **Execute** aufrufen. Z. B. `GetRecordsAffected` gibt Informationen über die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt werden, wenn eine Abfrage ausgeführt. Die zurückgegebene Anzahl wider nicht, bleiben die Änderungen in verknüpften Tabellen, wenn Cascade aktualisiert oder löscht.  
  
 **Führen Sie** kein Recordset zurückgibt. Mithilfe von **ausführen** auf einer Abfrage, die Datensätze auswählt bewirkt, dass MFC eine Ausnahme vom Typ `CDaoException`. (Es gibt keine `ExecuteSQL` Memberfunktion analog zu `CDatabase::ExecuteSQL`.)  
  
##  <a name="getconnect"></a>CDaoDatabase::GetConnect  
 Rufen Sie diese Memberfunktion zum Abrufen der Verbindungszeichenfolge zur Verbindung der `CDaoDatabase` Objekt in eine ODBC- oder ISAM-Datenbank.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Verbindungszeichenfolge, wenn [öffnen](#open) wurde erfolgreich auf eine ODBC-Datenquelle bezeichnet, andernfalls eine leere Zeichenfolge. Für einen Microsoft Jet (. MDB)-Datenbank, die Zeichenfolge ist immer leer, sofern es für die Verwendung mit der **DbSQLPassThrough** Option verwendet, mit der [Execute](#execute) Memberfunktion oder öffnen Sie ein Recordset verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge enthält Informationen über die Quelle einer geöffneten Datenbank oder einer Datenbank in einer Pass-Through-Abfrage verwendet. Die Verbindungszeichenfolge besteht aus einem Datenbank-Typspezifizierer und NULL oder mehr Parameter, die durch Semikolons getrennt ein.  
  
> [!NOTE]
>  Verwenden die MFC-DAO-Klassen für die Verbindung mit einer Datenquelle über ODBC ist weniger effizient als das Herstellen einer Verbindung über einer angefügten Tabelle.  
  
> [!NOTE]
>  Die Verbindungszeichenfolge wird zum Übergeben zusätzlicher Informationen an ODBC- und bestimmte ISAM-Treiber nach Bedarf verwendet. Es ist nicht für verwendet. MDB-Datenbanken. Für Microsoft Jet-Datenbank-Basistabellen, die Verbindungszeichenfolge ist eine leere Zeichenfolge ("") außer wenn Sie ihn für eine SQL-Pass-Through-Abfrage verwenden wie Rückgabewert oben beschrieben.  
  
 Finden Sie unter der [öffnen](#open) Member-Funktion eine Beschreibung wie die Verbindungszeichenfolge erstellt wird. Nachdem die Verbindungszeichenfolge, in festgelegt wurde der **öffnen** Aufruf später können sie um die Einstellung bestimmt den Typ, den Pfad, die Benutzer-ID, Kennwort oder ODBC-Datenquelle der Datenbank zu überprüfen.  
  
##  <a name="getname"></a>CDaoDatabase::GetName  
 Rufen Sie diese Memberfunktion um den Namen der aktuell geöffneten Datenbank, die der Name einer vorhandenen Datenbankdatei ist oder der Name einer registrierten ODBC-Datenquelle abzurufen.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den vollständigen Pfad und Dateinamen der Datenbank, wenn erfolgreich; andernfalls eine leere [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihr Netzwerk die einheitliche Benennungskonvention (UNC) unterstützt, können Sie auch einen Netzwerkpfad angeben, z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelte umgekehrte Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist die C++-Escape-Zeichen.)  
  
 Möglicherweise möchten Sie z. B. diesen Namen in einer Überschrift anzuzeigen. Wenn ein Fehler auftritt, während der Name abgerufen wird, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
> [!NOTE]
>  Für eine bessere Leistung, wenn externe Datenbanken zugegriffen wird, es wird empfohlen, dass Sie externe Tabellen in einer Microsoft Jet-Datenbank anfügen (. MDB) anstatt eine direkte Verbindung mit der Datenquelle.  
  
 Typ der Datenbank wird durch die Datei oder das Verzeichnis, die der Pfad, wie folgt verweist angegeben:  
  
|Pfadname verweist auf...|Datenbanktyp|  
|--------------------------|-------------------|  
|. MDB-Datei|Microsoft Jet-Datenbank (Microsoft Access)|  
|Verzeichnis, enthält. DBF-Dateien|dBASE-Datenbank|  
|Verzeichnis, enthält. XLS-Datei|Microsoft Excel-Datenbank|  
|Verzeichnis, enthält. PDX-Dateien|Paradox-Datenbank|  
|Verzeichnis, Datenbankdateien entsprechend formatierten Text enthält.|Datenbank im Text-format|  
  
 Für ODBC-Datenbanken wie SQL Server und Oracle identifiziert die Datenbank-Verbindungszeichenfolge einen Datenquellennamen (DSN), der von ODBC registriert ist.  
  
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
 Rufen Sie diese Memberfunktion auf verschiedene Arten von Informationen über eine Abfrage in der Datenbank definierten erhalten.  
  
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
 Ein Verweis auf eine [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen das Recordset abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion für das Recordset zurückgegeben verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Typ  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Datum erstellt, Datum der letzten Aktualisierung, gibt Datensätze, aktualisierbar  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: SQL Connect Timeoutfehlers warten soll.  
  
 `lpszName`  
 Eine Zeichenfolge mit dem Namen einer Abfrage in der Datenbank, für die Suche nach dem Namen definiert.  
  
### <a name="remarks"></a>Hinweise  
 Eine Abfrage nach Index in der Datenbank QueryDefs-Auflistung oder durch den Namen der Abfrage können Sie auswählen, werden zwei Versionen der Funktion bereitgestellt.  
  
 Eine Beschreibung der Informationen zurückgegeben *Querydefinfo*, finden Sie unter der [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie eine Ebene Informationen anfordern, erhalten Sie alle vorherigen Ebenen sowie Informationen.  
  
##  <a name="getquerytimeout"></a>CDaoDatabase::GetQueryTimeout  
 Rufen Sie diese Memberfunktion rufen Sie die aktuelle Anzahl der Sekunden, bevor nachfolgende Vorgänge in der verbundenen Datenbank ein erfolgt Timeout.  
  
```  
short GetQueryTimeout();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine kurze ganze Zahl, die den Timeoutwert in Sekunden.  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorgang kann aufgrund von Netzwerkproblemen Zugriff, übermäßige Abfrage Verarbeitungszeit usw. Timeout. Während die Einstellung aktiviert ist, sondern alle offenen, neu hinzufügen, aktualisieren und delete-Operationen für alle zugeordneten Recordsets `CDaoDatabase` Objekt. Sie können die aktuelle Timeouteinstellung ändern, durch Aufrufen von [SetQueryTimeout](#setquerytimeout). Ändern den Timeoutwert für Abfragen für ein Recordset nach öffnen, wird der Wert für das Recordset nicht geändert. Beispielsweise wird bei nachfolgenden [verschieben](../../mfc/reference/cdaorecordset-class.md#move) Vorgänge verwenden Sie den neuen Wert nicht. Der Standardwert wird anfangs festgelegt, wenn die Datenbank-Engine initialisiert wird.  
  
 Der Standardwert für Abfragetimeouts stammt aus der Windows-Registrierung. Wenn kein Registrierungseintrag vorhanden ist, ist der Standardwert 60 Sekunden. Nicht alle Datenbanken unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, tritt kein Timeout. und die Kommunikation mit der Datenbank reagiert. Dieses Verhalten kann während der Entwicklung hilfreich sein. Wenn der Aufruf fehlschlägt, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Verwandte Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getrecordsaffected"></a>CDaoDatabase::GetRecordsAffected  
 Rufen Sie diese Memberfunktion zum Ermitteln der Anzahl der vom letzten Aufruf der betroffenen Datensätze der [Execute](#execute) Member-Funktion.  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine long-integer-Wert, der die Anzahl der betroffenen Datensätze enthält.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert enthält die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt, indem eine Abfrage ausführen, die mit **Execute**. Die zurückgegebene Anzahl wider nicht, bleiben die Änderungen in verknüpften Tabellen, wenn Cascade aktualisiert oder löscht.  
  
 Verwandte Informationen finden Sie im Thema "RecordsAffected-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getrelationcount"></a>CDaoDatabase::GetRelationCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.  
  
```  
short GetRelationCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Beziehungen zwischen Tabellen in der Datenbank definiert.  
  
### <a name="remarks"></a>Hinweise  
 **GetRelationCount** ist hilfreich, wenn Sie alle definierten Beziehungen in der Datenbank Relations-Auflistung durchlaufen müssen. Um Informationen über eine bestimmte Beziehung in der Auflistung zu erhalten, finden Sie unter [GetRelationInfo](#getrelationinfo).  
  
 Betrachten Sie das Konzept einer Beziehung zur Veranschaulichung eine Lieferantentabelle und eine Products-Tabelle, die eine&1;: n-Beziehung aufweisen kann. In dieser Beziehung kann ein Lieferant mehr als ein Produkt angeben. Andere Beziehungen sind&1;:&1;- und n.  
  
##  <a name="getrelationinfo"></a>CDaoDatabase::GetRelationInfo  
 Rufen Sie diese Memberfunktion zum Abrufen von Informationen über eine angegebene Beziehung in der Datenbank Relations-Auflistung.  
  
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
 Der Index des Objekts Beziehung in der Datenbank Relations-Auflistung für die Suche nach Index.  
  
 *relinfo*  
 Ein Verweis auf eine [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über die Beziehung abgerufen werden. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion über die Beziehung zurück verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name der Tabelle, Foreign-Tabelle  
  
- `AFX_DAO_SECONDARY_INFO`Attribute, die Informationen  
  
 Die Feldinformationen ist ein [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) -Objekt, das die Felder in der primären Tabelle in der Beziehung beteiligten enthält.  
  
 `lpszName`  
 Eine Zeichenfolge mit dem Namen der Relation-Objekt für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Versionen dieser Funktion ermöglichen den Zugriff nach Index oder Name. Eine Beschreibung der Informationen zurückgegeben *Relinfo*, finden Sie unter der [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie auch Informationen sowie alle übergeordneten Ebenen.  
  
> [!NOTE]
>  Wenn Sie die Beziehung Objektattribute Cascade-Vorgänge aktivieren festlegen ( **DbRelationUpdateCascades** oder **DbRelationDeleteCascades**), das Microsoft Jet-Datenbankmodul automatisch aktualisiert oder löscht Einträge in einem oder mehreren anderen Tabellen, wenn Änderungen verknüpften primären Schlüssel Tabellen. Nehmen wir beispielsweise an, dass Sie eine Cascade Delete-Beziehung zwischen einer Kundentabelle und einer Orders-Tabelle erstellen. Wenn Sie Datensätze aus der Customers-Tabelle löschen, werden die Datensätze in der Orders-Tabelle, die im Zusammenhang mit diesen Kunden ebenfalls gelöscht. Darüber hinaus wird Sie Cascade Delete Beziehungen zwischen der Orders-Tabelle und anderen Tabellen herstellen, werden Datensätze aus diesen Tabellen automatisch gelöscht, wenn Sie Datensätze aus der Customers-Tabelle löschen.  
  
##  <a name="gettabledefcount"></a>CDaoDatabase:: GetTableDefCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Tabellen in der Datenbank definiert.  
  
```  
short GetTableDefCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in der Datenbank definierten Tabledefs.  
  
### <a name="remarks"></a>Hinweise  
 `GetTableDefCount`ist nützlich, wenn Sie alle Tabledefs in der Datenbank TableDefs-Auflistung durchlaufen müssen. Informationen zu einer bestimmten Tabelle in der Auflistung finden Sie unter [GetTableDefInfo](#gettabledefinfo).  
  
##  <a name="gettabledefinfo"></a>CDaoDatabase:: GetTableDefInfo  
 Rufen Sie diese Memberfunktion auf verschiedene Arten von Informationen zu einer Tabelle in der Datenbank definierten erhalten.  
  
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
 Der Index des Tabledef-Objekts in der Datenbank TableDefs-Auflistung, für die Suche nach Index.  
  
 `tabledefinfo`  
 Ein Verweis auf eine [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über die Tabelle abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion über die Beziehung zurück verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, aktualisiert werden kann, Attribute  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Datum erstellt, die letzte Aktualisierung, Name der Quelltabelle, verbinden  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: Datensatzanzahl Validierungsregel Validation-Text  
  
 `lpszName`  
 Der Name des Tabledef-Objekts, für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 Eine Tabelle der Index in der Datenbank TableDefs-Auflistung oder den Namen der Tabelle können Sie auswählen, werden zwei Versionen der Funktion bereitgestellt.  
  
 Eine Beschreibung der Informationen zurückgegeben `tabledefinfo`, finden Sie unter der [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie.  
  
> [!NOTE]
>  Die `AFX_DAO_ALL_INFO` -Option liefert Informationen, die langsame abgerufen werden können. In diesem Fall könnte zum zählen der Datensätze in der Tabelle sehr zeitaufwändig sein, wenn viele Datensätze vorhanden sind.  
  
##  <a name="getversion"></a>CDaoDatabase::GetVersion  
 Rufen Sie diese Memberfunktion zum Ermitteln der Version der Microsoft Jet-Datenbankdatei.  
  
```  
CString GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der die Version der Datenbankdatei mit dem Objekt verbundenen angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert stellt die Versionsnummer im Format "Hauptversion.Nebenversion"; beispielsweise "3.0". Die Versionsnummer des Produkts (z. B. "3.0") besteht aus der Versionsnummer (3), einem Punkt und der Versionsnummer (0). Die Versionen bis Datum sind 1.0, 1.1, 2.0 und 3.0.  
  
 Verwandte Informationen finden Sie unter dem Thema "Version-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="isopen"></a>CDaoDatabase::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoDatabase` -Objekt für eine Datenbank geöffnet ist.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoDatabase` Objekt wird geöffnet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pdaodatabase"></a>CDaoDatabase::m_pDAODatabase  
 Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO-Datenbank-Objekt zugrunde liegenden der `CDaoDatabase` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Zeiger, wenn Sie auf die DAO-Schnittstelle direkt zugreifen müssen.  
  
 Informationen zum Aufrufen von DAO direkt finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
##  <a name="m_pworkspace"></a>CDaoDatabase::m_pWorkspace  
 Enthält einen Zeiger auf die [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) -Objekt, das das Datenbankobjekt enthält.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger verwenden, wenn Sie direkt auf den Arbeitsbereich zugreifen müssen, z. B. Verweise auf andere Datenbankobjekte in den Arbeitsbereich Databases-Auflistung abgerufen.  
  
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
 Ein Zeichenfolgenausdruck, der den Namen einer vorhandenen Microsoft Jet (. MDB)-Datei. Wenn der Dateiname eine Erweiterung hat, ist jedoch erforderlich. Wenn Ihr Netzwerk die einheitliche Benennungskonvention (UNC) unterstützt, Sie können auch angeben einen Netzwerkpfad wie z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelte umgekehrte Schrägstriche in Zeichenfolgenliteralen erforderlich sind, da "\\" ist die C++-Escape-Zeichen.)  
  
 Einige Aspekte sollten bei der Verwendung `lpszName`. Wenn sie:  
  
-   Verweist auf eine Datenbank, die bereits von einem anderen Benutzer, MFC-löst eine Ausnahme des Typs für exklusiven ist [CDaoException](../../mfc/reference/cdaoexception-class.md). Abfangen dieser Ausnahme aus, um Ihre Benutzer wissen lassen, dass die Datenbank nicht verfügbar ist.  
  
-   Ist eine leere Zeichenfolge ("") und *LpszConnect* "ODBC;" wird ein Dialogfeld Anzeigen aller registrierte ODBC-Datenquellennamen wird angezeigt, damit der Benutzer eine Datenbank auswählen kann. Vermeiden Sie die direkte Verbindungen mit ODBC-Datenquellen; Verwenden Sie stattdessen einer angefügten Tabelle.  
  
-   Andernfalls verweist nicht auf einer vorhandenen Datenbank oder eine gültige ODBC-Datenquellennamen, MFC löst eine Ausnahme vom Typ `CDaoException`.  
  
> [!NOTE]
>  Weitere Informationen zu Fehlercodes für DAO finden Sie unter der DAOERR. H-Datei. Verwandte Informationen finden Sie im Thema "Abfangbarer Datenzugriff" in der DAO-Hilfe.  
  
 `bExclusive`  
 Ein boolescher Wert, der **TRUE** Wenn die Datenbank exklusiv (nicht freigegebenen) geöffnet werden und **FALSE** ist die Datenbank für gemeinsamen Zugriff geöffnet werden. Wenn Sie dieses Argument nicht angeben, wird die Datenbank für gemeinsamen Zugriff geöffnet.  
  
 `bReadOnly`  
 Ein boolescher Wert, der **TRUE** ist die Datenbank für schreibgeschützten Zugriff geöffnet werden und **FALSE** ist die Datenbank für Lese-/Schreibzugriff geöffnet werden. Wenn Sie dieses Argument nicht angeben, wird die Datenbank für Lese-/Schreibzugriff geöffnet. Alle abhängigen Recordsets erben dieses Attribut.  
  
 `lpszConnect`  
 Ein Zeichenfolgenausdruck, der zum Öffnen der Datenbank verwendet wird. Diese Zeichenfolge bildet die ODBC Argumente verbinden. Sie müssen die exklusive und Read-only-Argumente, die eine Quellzeichenfolge bereitstellen angeben. Wenn die Datenbank eine Microsoft Jet-Datenbank (. (MDB), die diese Zeichenfolge ist leer (""). Die Syntax für den Standardwert – **_T**("") – ermöglicht den Portabilität für Unicode als auch in ANSI-builds Ihrer Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 **Öffnen Sie** ordnet das zugrunde liegende DAO-Objekt die Datenbank. Das Database-Objekt können Sie Recordset, Tabledef oder Querydef-Objekte erstellen, bis es initialisiert wird. **Öffnen Sie** fügt das Datenbankobjekt, das an den zugehörigen Arbeitsbereich datenbankauflistung an.  
  
 Verwenden Sie die Parameter wie folgt:  
  
-   Wenn Sie eine Microsoft Jet öffnen (. MDB)-Datenbank die `lpszName` Parameter und übergeben Sie eine leere Zeichenfolge für die `lpszConnect` Parameter bzw. eine Kennwortzeichenfolge der Form "; PWD = Password ", wenn die Datenbank ein Kennwort geschützt ist (. MDB-Datenbanken nur).  
  
-   Wenn Sie eine ODBC-Datenquelle öffnen, übergeben Sie eine gültige ODBC-Verbindungszeichenfolge in `lpszConnect` und eine leere Zeichenfolge in `lpszName`.  
  
 Verwandte Informationen finden Sie im Thema "OpenDatabase-Methode" in der DAO-Hilfe.  
  
> [!NOTE]
>  Für eine bessere Leistung beim Zugriff auf externe Datenbanken, einschließlich ISAM-Datenbanken und ODBC-Datenquellen, wird empfohlen, dass Sie externe Tabellen einer Microsoft Jet-Datenbankmoduls anfügen (. MDB) anstatt eine direkte Verbindung mit der Datenquelle.  
  
 Es ist möglich, für eine Verbindung zu einem Timeout, wenn z. B. der DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch fehlschlägt, **öffnen** löst eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Die verbleibenden Hinweise gelten nur für ODBC-Datenbanken:  
  
 Wenn die Datenbank eine ODBC-Datenbank und die Parameter in der **öffnen** Aufruf enthalten genügend Informationen zum Herstellen die Verbindung, die der ODBC-Treiber öffnet ein Dialogfeld, um die erforderlichen Informationen vom Benutzer zu erhalten. Beim Aufruf von **öffnen**, die Verbindungszeichenfolge `lpszConnect`, privat gespeichert und kann durch Aufrufen der [GetConnect](#getconnect) Member-Funktion.  
  
 Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf von **öffnen** zum Abrufen von Informationen vom Benutzer, z. B. ein Kennwort in die Verbindungszeichenfolge, die Sie, um übergeben diese Informationen dann hinzuzufügen **öffnen**. Oder möglicherweise möchten Sie die Verbindungszeichenfolge, die Sie übergeben (z. B. in der Windows-Registrierung), damit Sie sie das nächste wiederverwenden können ruft Ihre Anwendung, Zeit zu sparen **öffnen** auf ein `CDaoDatabase` Objekt.  
  
 Sie können auch die Verbindungszeichenfolge für mehrere Ebenen des Login-Autorisierung (jeweils ein anderes `CDaoDatabase` Objekt) oder andere datenbankspezifischen Informationen vermitteln.  
  
##  <a name="setquerytimeout"></a>CDaoDatabase::SetQueryTimeout  
 Rufen Sie diese Memberfunktion, um die Standardanzahl von Sekunden, bevor nachfolgende Vorgänge in der verbundenen Datenbank-Timeout zu überschreiben.  
  
```  
void SetQueryTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 `nSeconds`  
 Die Anzahl der Sekunden, bevor der Versuch einer Abfrage ist ein Timeout aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorgang kann aufgrund von Netzwerkproblemen Zugriff, übermäßige Abfrage Verarbeitungszeit usw. Timeout. Rufen Sie `SetQueryTimeout` vor dem Öffnen des Recordsets oder vor dem Aufrufen des Recordsets [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [Update](../../mfc/reference/cdaorecordset-class.md#update), oder [löschen](../../mfc/reference/cdaorecordset-class.md#delete) Memberfunktionen, wenn Sie den Timeoutwert für Abfragen ändern möchten. Die Einstellung wirkt sich auf alle nachfolgenden [öffnen](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`, **Update**, und **löschen** Aufrufe an alle zugeordneten Recordsets `CDaoDatabase` Objekt. Ändern den Timeoutwert für Abfragen für ein Recordset nach öffnen, wird der Wert für das Recordset nicht geändert. Beispielsweise wird bei nachfolgenden [verschieben](../../mfc/reference/cdaorecordset-class.md#move) Vorgänge verwenden Sie den neuen Wert nicht.  
  
 Der Standardwert für Abfragetimeouts beträgt 60 Sekunden. Nicht alle Datenbanken unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, tritt kein Timeout. die Kommunikation mit der Datenbank reagiert. Dieses Verhalten kann während der Entwicklung hilfreich sein.  
  
 Verwandte Informationen finden Sie im Thema "QueryTimeout-Eigenschaft" in der DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)

