---
title: CDaoQueryDef Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoQueryDef
dev_langs:
- C++
helpviewer_keywords:
- QueryDef objects
- CDaoQueryDef class
- queries [Visual Studio], defining
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: 24
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
ms.openlocfilehash: 0bf06c68bb7072aa1907e4c730848cca9ff5e7d0
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef-Klasse
Stellt eine Abfragedefinition ("Querydef") dar, die in einer Datenbank gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Erstellt eine **CDaoQueryDef** Objekt. Anschließend rufen **öffnen** oder **erstellen**je nach Ihren Anforderungen.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoQueryDef:: Append](#append)|QueryDefs-Auflistung für die Datenbank als gespeicherte Abfrage hinzufügt Querydef.|  
|[CDaoQueryDef::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn die Abfrage die Datenbank aktualisiert werden kann.|  
|[CDaoQueryDef::Close](#close)|Schließt das Querydef-Objekt. Zerstören Sie das C++-Objekt, wenn Sie damit fertig sind.|  
|[CDaoQueryDef::Create](#create)|Erstellt das zugrunde liegende DAO Querydef-Objekt. Verwenden Sie die Querydef als temporäre Abfrage oder Aufruf **Append** in der Datenbank zu speichern.|  
|[CDaoQueryDef:: Execute](#execute)|Führt die Abfrage durch das Querydef-Objekt definiert.|  
|[CDaoQueryDef::GetConnect](#getconnect)|Gibt die Verbindungszeichenfolge Querydef zugeordnet. Die Verbindungszeichenfolge identifiziert die Datenquelle. (SQL-Abfragen Pass-Through-, andernfalls eine leere Zeichenfolge.)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Gibt das Datum der Erstellung die gespeicherte Abfrage.|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Gibt das Datum der letzten Aktualisierung die gespeicherte Abfrage.|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Gibt die Anzahl der von der Querydef definierten Felder zurück.|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Gibt Informationen zu einem bestimmten Feld in der Abfrage definiert.|  
|[CDaoQueryDef::GetName](#getname)|Gibt den Namen der Querydef.|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|Gibt den Timeoutwert für ODBC (für eine ODBC-Abfrage) verwendeten Wenn Querydef ausgeführt wird. Dies bestimmt, wie lange die Abfrage Aktion zu ermöglichen.|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Gibt die Anzahl von Parametern für die Abfrage definiert.|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Gibt Informationen über einen bestimmten Parameter an die Abfrage zurück.|  
|[CDaoQueryDef:: GetParamValue](#getparamvalue)|Gibt den Wert der angegebenen Parameter an die Abfrage zurück.|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Gibt die Anzahl der Datensätze, die eine Abfrage betroffen.|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Gibt einen Wert ungleich NULL, wenn die Abfrage durch die Querydef definiert Datensätze zurückgibt.|  
|[CDaoQueryDef::GetSQL](#getsql)|Die SQL-Zeichenfolge, die angibt, die durch die Querydef definierte Abfrage zurückgegeben.|  
|[CDaoQueryDef::GetType](#gettype)|Gibt den Abfragetyp: löschen, aktualisieren, anfügen, Tabelle, und so weiter.|  
|[CDaoQueryDef::IsOpen](#isopen)|Gibt einen Wert ungleich NULL zurück, wenn Querydef geöffnet ist und ausgeführt werden kann.|  
|[CDaoQueryDef::Open](#open)|Öffnet eine vorhandene Querydef in der QueryDefs-Auflistung der Datenbank gespeichert.|  
|[CDaoQueryDef::SetConnect](#setconnect)|Legt die Verbindungszeichenfolge für eine SQL-Pass-Through-Abfrage für eine ODBC-Datenquelle fest.|  
|[CDaoQueryDef::SetName](#setname)|Legt den Namen der gespeicherten Abfrage, der verwendete Name ersetzt werden, wenn die Querydef erstellt wurde.|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|Legt den Timeoutwert für ODBC (für eine ODBC-Abfrage) verwendeten Wenn Querydef ausgeführt wird.|  
|[CDaoQueryDef:: SetParamValue](#setparamvalue)|Legt den Wert der angegebenen Parameter der Abfrage fest.|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Gibt an, ob die Querydef Datensätze zurückgibt. Wenn dieses Attribut auf **TRUE** gilt nur für SQL Pass-Through-Abfragen.|  
|[CDaoQueryDef::SetSQL](#setsql)|Legt die SQL-Zeichenfolge, die angibt, die durch die Querydef definierte Abfrage fest.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|Ein Zeiger auf die OLE-Schnittstelle für das zugrunde liegende DAO Querydef-Objekt.|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Ein Zeiger auf die `CDaoDatabase` dem Querydef zugeordnet ist. Querydef kann oder nicht in der Datenbank gespeichert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Querydef ist ein Access-Objekt, das die SQL-Anweisung enthält, die beschreibt, eine Abfrage, und alle Eigenschaften, wie z. B. "Erstellungsdatum" und "ODBC-Timeout". Sie können auch temporäre Querydef-Objekte erstellen, ohne sie zu speichern, aber es ist praktisch, – und sehr viel effizienter – zum Speichern häufig wiederverwendet Abfragen in einer Datenbank. Ein [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt verwaltet eine Sammlung namens QueryDefs-Auflistung, die die gespeicherten Querydefs enthält.  
  
> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können immer noch Zugriff auf ODBC-Datenquellen mit DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die ODBC-basierten MFC-Klassen. DAO-basierte Klassen können Daten, einschließlich der über ODBC-Treiber, über ihre eigenen Datenbank-Engine zugreifen. DAO-basierte Klassen unterstützen auch Vorgänge (Data Definition Language, Datendefinitionssprache), z. B. das Hinzufügen von Tabellen über die Klassen ohne DAO direkt aufrufen.  
  
## <a name="usage"></a>Verwendung  
 Verwenden Sie Querydef-Objekte entweder zusammen mit einer vorhandenen Abfrage gespeichert oder zum Erstellen einer neuen Abfrage oder temporäre Abfrage gespeichert:  
  
1.  In allen Fällen erstellen Sie zuerst eine `CDaoQueryDef` -Objekt, indem einen Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt, zu dem die Abfrage gehört.  
  
2.  Führen Sie die folgenden, je nachdem, was Sie:  
  
    -   Um eine vorhandene gespeicherte Abfrage zu verwenden, rufen Sie des Querydef-Objekts [öffnen](#open) Member-Funktion, die den Namen der gespeicherten Abfrage angeben.  
  
    -   Um eine neue gespeicherte Abfrage zu erstellen, rufen Sie des Querydef-Objekts [erstellen](#create) Member-Funktion, die den Namen der Abfrage angeben. Rufen Sie dann [Append](#append) für die Abfrage aus, indem Sie an der Datenbank QueryDefs-Auflistung angefügt. **Erstellen** versetzt die Querydef in den geöffneten Zustand, daher nach dem Aufruf von **erstellen** rufen Sie **öffnen**.  
  
    -   Rufen Sie zum Erstellen einer temporären Querydef **erstellen**. Übergeben Sie eine leere Zeichenfolge nach dem Abfragenamen. Rufen Sie **Append**.  
  
 Aufrufen, wenn Sie fertig sind, mit einem Querydef-Objekt, dessen [schließen](#close) Member-Funktion und anschließend das Querydef-Objekt zu zerstören.  
  
> [!TIP]
>  Die einfachste Möglichkeit zum Erstellen von gespeicherter Abfragen wird Sie erstellt und in der Datenbank mithilfe von Microsoft Access zu speichern. Sie können dann öffnen und in der MFC-Code verwenden.  
  
## <a name="purposes"></a>Zweck  
 Sie können Querydef-Objekts für eines der folgenden Zwecken verwenden:  
  
-   Erstellen einer `CDaoRecordset` Objekt  
  
-   Zum Aufrufen des Objekts **Execute** Member-Funktion direkt eine Abfrage oder eine SQL-Pass-Through-Abfrage ausführen  
  
 Verwenden Sie ein Querydef-Objekt für jede Art von Abfrage, einschließlich Select, Aktion, Kreuztabelle, Delete, Update, anfügen, Tabelle, Datendefinition, SQL Pass-Through-, Union-, und massenabfragen. Die Abfrage wird durch den Inhalt der SQL-Anweisung bestimmt, den Sie angeben. Informationen zu Abfragetypen finden Sie unter der **ausführen** und [GetType](#gettype) Memberfunktionen. Recordsets werden im Allgemeinen zum Zurückgeben von Zeilen abfragt, in der Regel mithilfe der **auswählen... AUS** Schlüsselwörter. **Führen Sie** wird am häufigsten für Massenvorgänge verwendet. Weitere Informationen finden Sie unter [ausführen](#execute) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## <a name="querydefs-and-recordsets"></a>Querydefs und Recordsets  
 Erstellung ein Querydef-Objekts verwenden ein `CDaoRecordset` -Objekt, in der Regel erstellen oder öffnen eine Querydef, wie oben beschrieben. Erstellen Sie ein Recordset-Objekt, das einen Zeiger auf das Querydef-Objekt übergeben, wenn Sie aufrufen [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open). Die Querydef, die Sie übergeben muss im geöffneten Zustand sein. Weitere Informationen finden Sie unter Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Eine Querydef können Sie einem Recordset (die häufigste Verwendung für eine Querydef) erstellen, wenn sie im geöffneten Zustand ist. Geöffneten Zustand durch Aufrufen die Querydef abgelegt **öffnen** oder **erstellen**.  
  
## <a name="external-databases"></a>Externe Datenbanken  
 QueryDef-Objekte sind die bevorzugte Methode zum Verwenden des systemeigenen SQL-Dialekts von einer externen Datenbank-Engine. Sie können z. B. Erstellen einer Transact-SQL-Abfrage (wie Microsoft SQL Server verwendet wird) und speichern es in einem Querydef-Objekt. Wenn Sie eine SQL-Abfrage, die nicht auf Grundlage der Microsoft Jet-Datenbankmodul verwenden müssen, müssen Sie eine Verbindungszeichenfolge angeben, die auf die externe Datenquelle verweist. Abfragen mit gültiger Verbindungszeichenfolgen umgehen das Datenbankmodul und übergeben Sie die Abfrage direkt an den externen Datenbankserver zur Verarbeitung.  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen ist sie an eine Microsoft Jet anfügen (. MDB)-Datenbank.  
  
 Weitere Informationen finden Sie unter den Themen "QueryDef-Objekt", "QueryDefs-Auflistung" und "CdbDatabase Object" in der DAO SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="a-nameappenda--cdaoquerydefappend"></a><a name="append"></a>CDaoQueryDef:: Append  
 Rufen Sie diese Memberfunktion aufrufen, nachdem Sie [erstellen](#create) zum Erstellen eines neuen Querydef-Objekts.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Hinweise  
 **Fügen Sie** speichert die Querydef in der Datenbank durch Anfügen des Objekts an die Datenbank QueryDefs-Auflistung. Sie können die Querydef als temporäres Objekt verwenden, ohne angefügt, aber beibehalten werden soll, rufen Sie **Append**.  
  
 Wenn Sie versuchen, eine temporäre Querydef-Objekt anfügen, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="a-namecanupdatea--cdaoquerydefcanupdate"></a><a name="canupdate"></a>CDaoQueryDef::CanUpdate  
 Rufen Sie diese Memberfunktion, um festzustellen, ob Sie die Querydef ändern können – z. B. das Ändern der Name oder die SQL-Zeichenfolge.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie berechtigt sind, ändern Sie die Querydef; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Querydef ändern, wenn:  
  
-   Er basiert nicht auf eine Datenbank, die schreibgeschützt geöffnet ist.  
  
-   Sie haben die Update-Berechtigungen für die Datenbank.  
  
     Dies ist abhängig, ob Sie die Sicherheitsfunktionen implementiert haben. MFC bietet keine Unterstützung für die Sicherheit. Sie müssen sie selbst durch Aufrufen von DAO direkt oder mithilfe von Microsoft Access implementieren. Finden Sie im Thema "Permissions-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="a-namecdaoquerydefa--cdaoquerydefcdaoquerydef"></a><a name="cdaoquerydef"></a>CDaoQueryDef::CDaoQueryDef  
 Erstellt eine **CDaoQueryDef** Objekt.  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Parameter  
 `pDatabase`  
 Ein Zeiger auf ein offenes [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt kann eine vorhandene Querydef gespeichert in der Datenbank QueryDefs-Auflistung, eine neue Abfrage in der Auflistung gespeichert werden oder eine temporäre Abfrage, nicht zu speichernden darstellen. Der nächste Schritt hängt vom Typ der Querydef:  
  
-   Wenn das Objekt eine vorhandene Querydef darstellt, rufen Sie des Objekts [öffnen](#open) Memberfunktion initialisieren.  
  
-   Steht das Objekt eine neue Querydef gespeichert werden soll, rufen Sie des Objekts [erstellen](#create) Member-Funktion. Dadurch wird die Datenbank QueryDefs-Auflistung des Objekts hinzugefügt. Rufen Sie dann `CDaoQueryDef` Memberfunktionen, die die Attribute des Objekts festgelegt. Rufen Sie abschließend [Append](#append).  
  
-   Wenn das Objekt eine temporäre Querydef (nicht in der Datenbank gespeichert werden) darstellt, rufen Sie **erstellen**, übergeben eine leere Zeichenfolge für die Abfrage an. Nach dem Aufruf von **erstellen**, initialisieren Sie die Querydef durch direktes Festlegen seiner Attribute. Rufen Sie **Append**.  
  
 Um die Attribute der Querydef festlegen möchten, können Sie die [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout), und [SetReturnsRecords](#setreturnsrecords) Memberfunktionen.  
  
 Rufen Sie abschließend mit der Querydef-Objekt seine [schließen](#close) Member-Funktion. Wenn Sie einen Zeiger auf die Querydef verfügen, verwenden die **löschen** Operator, um das C++-Objekt zu zerstören.  
  
##  <a name="a-nameclosea--cdaoquerydefclose"></a><a name="close"></a>CDaoQueryDef::Close  
 Rufen Sie diese Memberfunktion auf, wenn Sie fertig sind, verwenden das Querydef-Objekt.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Schließen die Querydef gibt das zugrunde liegende DAO-Objekt werden jedoch nicht zerstört gespeicherten DAO Querydef-Objekts oder die C++- `CDaoQueryDef` Objekt. Dies ist nicht identisch mit [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), Querydef aus der Datenbank QueryDefs-Auflistung in DAO (sofern nicht mit einer temporären Querydef) gelöscht.  
  
##  <a name="a-namecreatea--cdaoquerydefcreate"></a><a name="create"></a>CDaoQueryDef::Create  
 Rufen Sie diese Memberfunktion, um eine neue gespeicherte Abfrage oder eine neue temporäre Abfrage zu erstellen.  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der eindeutige Name der Abfrage in der Datenbank gespeichert. Informationen zu der Zeichenfolge finden Sie im Thema "CreateQueryDef-Methode" in der DAO-Hilfe. Wenn Sie annehmen, dass den Standardwert eine leere Zeichenfolge ist, wird eine temporäre Querydef erstellt. Eine solche Abfrage ist nicht in der QueryDefs-Auflistung gespeichert.  
  
 `lpszSQL`  
 Die SQL-Zeichenfolge, die die Abfrage definiert. Wenn Sie den Standardwert übernehmen **NULL**, müssen Sie später Aufrufen [SetSQL](#setsql) zum Festlegen der Zeichenfolge. Bis dahin ist die Abfrage nicht definiert. Sie können jedoch die nicht definierte Abfrage verwenden, ein Recordset zu öffnen; Einzelheiten finden Sie unter "Hinweise". Die SQL-Anweisung muss definiert werden, bevor Sie die Querydef der QueryDefs-Auflistung anfügen können.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen Namen im übergeben `lpszName`, rufen Sie dann [Append](#append) Querydef in der QueryDefs-Auflistung der Datenbank zu speichern. Andernfalls wird das Objekt ist eine temporäre Querydef und wird nicht gespeichert. In beiden Fällen ist die Querydef im geöffneten Zustand und entweder können Sie sie zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) -Objekt, oder rufen Sie der Querydef [Execute](#execute) Member-Funktion.  
  
 Wenn Sie nicht in eine SQL-Anweisung angeben `lpszSQL`, Sie können die Abfrage mit nicht ausführen **Execute** jedoch können Sie sie so erstellen Sie ein Recordset. In diesem Fall verwendet MFC Standard-SQL-Anweisung des Recordsets.  
  
##  <a name="a-nameexecutea--cdaoquerydefexecute"></a><a name="execute"></a>CDaoQueryDef:: Execute  
 Rufen Sie diese Memberfunktion zum Ausführen der Abfrage durch das Querydef-Objekt definiert.  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Parameter  
 `nOptions`  
 Eine ganze Zahl, die die Merkmale der Abfrage bestimmt. Verwandte Informationen finden Sie im Thema "Execute-Methode" in der DAO-Hilfe. Können Sie den bitweisen OR-Operator ( **|**) die folgenden Konstanten für dieses Argument zu kombinieren:  
  
- **DbDenyWrite** verweigern Schreibberechtigung für andere Benutzer.  
  
- **DbInconsistent** inkonsistente Aktualisierungen.  
  
- **DbConsistent** einheitliche Updates.  
  
- **DbSQLPassThrough** SQL Pass-Through. Bewirkt, dass die SQL-Anweisung zur Verarbeitung an eine ODBC-Datenbank übergeben werden.  
  
- **DbFailOnError** Default-Wert. Rollback für Updates, wenn ein Fehler auftritt und der Bericht den Fehler an den Benutzer.  
  
- **DbSeeChanges** generieren einen Laufzeitfehler, wenn ein anderer Benutzer Daten ändert, die Sie bearbeiten.  
  
> [!NOTE]
>  Eine Erläuterung der Begriffe "inkonsistent" und "konsistent" finden Sie im Thema "Execute-Methode" in der DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 QueryDef-Objekte, die zur Ausführung auf diese Weise können Sie nur die folgenden Abfragetypen darstellen:  
  
-   Aktionsabfragen  
  
-   SQL-Pass-Through-Abfragen  
  
 **Führen Sie** funktioniert nicht für Abfragen, die Einträge, wie z. B. select-Abfragen zurückgeben. **Führen Sie** wird häufig für Massenkopieren Vorgang Abfragen verwendet, wie z. B. **UPDATE**, **einfügen**, oder **SELECT INTO**, oder für Vorgänge Data Definition Language (DDL).  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Datenquellen ist, können Sie eine Microsoft Jet Tabellen zuordnen (. MDB)-Datenbank. Weitere Informationen finden Sie im Thema "Zugreifen auf externe Datenbanken mit DAO" in der DAO-Hilfe.  
  
 Rufen Sie die [GetRecordsAffected](#getrecordsaffected) -Memberfunktion des Querydef-Objekts bestimmen die Anzahl der Datensätze, die von der letzten betroffen **Execute** aufrufen. Z. B. `GetRecordsAffected` gibt Informationen über die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt werden, wenn eine Abfrage ausgeführt. Die zurückgegebene Anzahl wider nicht, bleiben die Änderungen in verknüpften Tabellen, wenn Cascade aktualisiert oder löscht.  
  
 Wenn Sie beide enthalten **DbInconsistent** und **DbConsistent** oder wenn Sie weder einschließen, wird das Ergebnis ist die Standardeinstellung **DbInconsistent**.  
  
 **Führen Sie** kein Recordset zurückgibt. Mithilfe von **ausführen** auf einer Abfrage, die Datensätze auswählt bewirkt, dass MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="a-namegetconnecta--cdaoquerydefgetconnect"></a><a name="getconnect"></a>CDaoQueryDef::GetConnect  
 Rufen Sie diese Memberfunktion zum Abrufen der Verbindungszeichenfolge die Querydef der Datenquelle zugeordnet.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) mit der Verbindungszeichenfolge für die Querydef.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nur mit ODBC-Datenquellen und bestimmte ISAM-Treiber verwendet. Es ist nicht mit Microsoft Jet verwendet (. Datenbanken MDB); In diesem Fall `GetConnect` eine leere Zeichenfolge zurückgegeben. Weitere Informationen finden Sie unter [SetConnect](#setconnect).  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen ist, fügen Sie diese ein. MDB-Datenbank. Weitere Informationen finden Sie im Thema "Zugreifen auf externe Datenbanken mit DAO" in der DAO-Hilfe.  
  
 Informationen zu Verbindungszeichenfolgen finden Sie unter dem Thema "Connect-Eigenschaft" DAO-Hilfe.  
  
##  <a name="a-namegetdatecreateda--cdaoquerydefgetdatecreated"></a><a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated  
 Rufen Sie diese Memberfunktion, um das Datum zu erhalten, die das Querydef-Objekt erstellt wurde.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das das Datum und die Uhrzeit der Erstellung die Querydef enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="a-namegetdatelastupdateda--cdaoquerydefgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoQueryDef::GetDateLastUpdated  
 Rufen Sie diese Memberfunktion zum Abrufen des Querydef-Objekts durch des Datums der letzten Aktualisierung – Wenn die Eigenschaften wurden geändert, z. B. den Namen, die SQL-Zeichenfolge oder der Verbindungszeichenfolge.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das das Datum und die Uhrzeit der letzten die Querydef Aktualisierung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="a-namegetfieldcounta--cdaoquerydefgetfieldcount"></a><a name="getfieldcount"></a>CDaoQueryDef::GetFieldCount  
 Rufen Sie diese Memberfunktion, um die Anzahl der Felder in der Abfrage abzurufen.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder in der Abfrage definiert.  
  
### <a name="remarks"></a>Hinweise  
 `GetFieldCount`eignet sich für alle Felder in der Querydef durchlaufen. Verwenden Sie zu diesem Zweck `GetFieldCount` in Verbindung mit [GetFieldInfo](#getfieldinfo).  
  
##  <a name="a-namegetfieldinfoa--cdaoquerydefgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoQueryDef::GetFieldInfo  
 Rufen Sie diese Memberfunktion zum Abrufen von verschiedenen Arten von Informationen zu einem Feld in der Querydef definiert.  
  
```  
void GetFieldInfo(
    int nIndex,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetFieldInfo(
    LPCTSTR lpszName,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des gewünschten Felds in die Querydef Fields-Auflistung, für die Suche nach Index.  
  
 `fieldinfo`  
 Ein Verweis auf ein `CDaoFieldInfo` Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen das Feld abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgeben verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Typ, Größe und der Attribute  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Ordnungsposition erforderlich, der Länge NULL zulassen, Quellfeld, fremden Name, Quelltabelle, Reihenfolge sortieren  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: Validierungsregel Standardwert Validation-Text  
  
 `lpszName`  
 Eine Zeichenfolge mit dem Namen des gewünschten Felds für die Suche nach Namen. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Informationen zurückgegeben `fieldinfo`, finden Sie unter der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur hat Member, die beschreibende Informationen unter entsprechen `dwInfoOptions` oben. Wenn Sie eine Ebene Informationen anfordern, erhalten Sie alle vorherigen Ebenen sowie Informationen.  
  
##  <a name="a-namegetnamea--cdaoquerydefgetname"></a><a name="getname"></a>CDaoQueryDef::GetName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens der Abfrage durch die Querydef dargestellt.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Abfrage.  
  
### <a name="remarks"></a>Hinweise  
 QueryDef sind eindeutigen benutzerdefinierten Namen. Weitere Informationen zu Querydef-Namen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="a-namegetodbctimeouta--cdaoquerydefgetodbctimeout"></a><a name="getodbctimeout"></a>CDaoQueryDef::GetODBCTimeout  
 Rufen Sie diese Memberfunktion zum Abrufen der aktuellen Frist, bis zum Timeout einer Abfrage mit einer ODBC-Datenquelle.  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Sekunden, bevor eine Abfrage ist ein Timeout aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu dieser Frist finden Sie im Thema "ODBCTimeout Property" in der DAO-Hilfe.  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen ist sie an eine Microsoft Jet anfügen (. MDB)-Datenbank. Weitere Informationen finden Sie im Thema "Zugreifen auf externe Datenbanken mit DAO" in der DAO-Hilfe.  
  
##  <a name="a-namegetparametercounta--cdaoquerydefgetparametercount"></a><a name="getparametercount"></a>CDaoQueryDef::GetParameterCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Parameter in der gespeicherten Abfrage.  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Parameter in der Abfrage definiert.  
  
### <a name="remarks"></a>Hinweise  
 `GetParameterCount`eignet sich für alle Parameter in der Querydef durchlaufen. Verwenden Sie zu diesem Zweck `GetParameterCount` in Verbindung mit [GetParameterInfo](#getparameterinfo).  
  
 Weitere Informationen finden Sie unter den Themen "Parameter-Objekt", "Parameterauflistung" und "Parameter-Deklaration (SQL)" in der DAO-Hilfe.  
  
##  <a name="a-namegetparameterinfoa--cdaoquerydefgetparameterinfo"></a><a name="getparameterinfo"></a>CDaoQueryDef::GetParameterInfo  
 Rufen Sie diese Memberfunktion zum Abrufen von Informationen über einen Parameter in der Querydef definiert.  
  
```  
void GetParameterInfo(
    int nIndex,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetParameterInfo(
    LPCTSTR lpszName,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des gewünschten Parameters in der Querydef-Parameters-Auflistung, für die Suche nach Index.  
  
 `paraminfo`  
 Ein Verweis auf eine [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen zu den abzurufenden Parameters. Die verfügbare Option ist hier aufgeführt, zusammen mit, was die Funktion zurückgegeben wird:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Typ  
  
 `lpszName`  
 Eine Zeichenfolge mit dem Namen des gewünschten Parameters, für die Suche nach Namen. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Informationen zurückgegeben `paraminfo`, finden Sie unter der [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) Struktur. Diese Struktur hat Member, die beschreibende Informationen unter entsprechen `dwInfoOptions` oben.  
  
 Verwandte Informationen finden Sie im Thema "Parameter-Deklaration (SQL)" in der DAO-Hilfe.  
  
##  <a name="a-namegetparamvaluea--cdaoquerydefgetparamvalue"></a><a name="getparamvalue"></a>CDaoQueryDef:: GetParamValue  
 Rufen Sie diese Memberfunktion rufen Sie den aktuellen Wert des angegebenen Parameters in der Querydef-Parameters-Auflistung gespeichert.  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name des Parameters, dessen Wert für die Suche nach dem Namen soll.  
  
 `nIndex`  
 Der nullbasierte Index des Parameters in der Querydef-Parameters-Auflistung, für die Suche nach Index. Sie können diesen Wert durch Aufrufe abrufen [GetParameterCount](#getparametercount) und [GetParameterInfo](#getparameterinfo).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt der Klasse [COleVariant](../../mfc/reference/colevariant-class.md) , die den Wert des Parameters enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Parameter nach Namen oder nach der Ordnungsposition in der Auflistung zugreifen.  
  
 Verwandte Informationen finden Sie im Thema "Parameter-Deklaration (SQL)" in der DAO-Hilfe.  
  
##  <a name="a-namegetrecordsaffecteda--cdaoquerydefgetrecordsaffected"></a><a name="getrecordsaffected"></a>CDaoQueryDef::GetRecordsAffected  
 Rufen Sie diese Memberfunktion, um zu bestimmen, wie viele Datensätze betroffen sind, durch den letzten Aufruf von [Execute](#execute).  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der betroffenen Datensätze.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Anzahl wider nicht, bleiben die Änderungen in verknüpften Tabellen, wenn Cascade aktualisiert oder löscht.  
  
 Weitere Informationen finden Sie im Thema "RecordsAffected-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="a-namegetreturnsrecordsa--cdaoquerydefgetreturnsrecords"></a><a name="getreturnsrecords"></a>CDaoQueryDef::GetReturnsRecords  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Querydef basiert auf einer Abfrage, die Datensätze zurückgibt.  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Querydef auf einer Abfrage basiert, die Datensätze gibt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist nur für SQL Pass-Through-Abfragen verwendet. Weitere Informationen zu SQL-Abfragen finden Sie unter der [Execute](#execute) Member-Funktion. Weitere Informationen zum Arbeiten mit SQL Pass-Through-Abfragen finden Sie unter der [SetReturnsRecords](#setreturnsrecords) Member-Funktion.  
  
 Verwandte Informationen finden Sie unter dem Thema "ReturnsRecords-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="a-namegetsqla--cdaoquerydefgetsql"></a><a name="getsql"></a>CDaoQueryDef::GetSQL  
 Rufen Sie diese Memberfunktion rufen Sie die SQL-Anweisung, die die Abfrage definiert, auf der die Querydef basiert.  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die SQL-Anweisung, die die Abfrage definiert, auf der die Querydef basiert.  
  
### <a name="remarks"></a>Hinweise  
 Sie werden dann die Zeichenfolge für die Schlüsselwörter, Tabellennamen usw. wahrscheinlich analysiert.  
  
 Weitere Informationen finden Sie unter den Themen "SQL-Eigenschaft", "Vergleich von Microsoft Jet Database Engine SQL und ANSI SQL" und "Abfragen einer Datenbank mit SQL im Code" DAO-Hilfe.  
  
##  <a name="a-namegettypea--cdaoquerydefgettype"></a><a name="gettype"></a>CDaoQueryDef::GetType  
 Rufen Sie diese Memberfunktion, um die Abfrage des Querydef zu bestimmen.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ der Abfrage durch die Querydef definiert. Werte finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Der Abfragetyp wird durch die Querydef SQL-Zeichenfolge angeben beim Erstellen der Querydef oder rufen Sie einer vorhandenen Querydef festgelegt [SetSQL](#setsql) Member-Funktion. Der Abfragetyp, der von dieser Funktion zurückgegebenen ist einer der folgenden Werte möglich:  
  
- **DbQSelect** auswählen  
  
- **DbQAction** Aktion  
  
- **DbQCrosstab** Kreuztabelle  
  
- **DbQDelete** löschen  
  
- **DbQUpdate** aktualisieren  
  
- **DbQAppend** Anfügen  
  
- **DbQMakeTable** Tabelle  
  
- **DbQDDL** Datendefinition  
  
- **DbQSQLPassThrough** Pass-Through-  
  
- **DbQSetOperation** Union  
  
- **DbQSPTBulk** mit verwendete **DbQSQLPassThrough** zum Angeben einer Abfrage, die keine Datensätze zurückgibt.  
  
> [!NOTE]
>  Um eine SQL-Pass-Through-Abfrage zu erstellen, legen Sie nicht die **DbSQLPassThrough** konstant. Dies wird automatisch durch das Microsoft Jet-Datenbankmodul festgelegt, wenn Sie ein Querydef-Objekt erstellen und der Verbindungszeichenfolge festlegen.  
  
 Weitere Informationen zu SQL-Zeichenfolgen finden Sie unter [GetSQL](#getsql). Informationen zu Abfragetypen finden Sie unter [Execute](#execute).  
  
##  <a name="a-nameisopena--cdaoquerydefisopen"></a><a name="isopen"></a>CDaoQueryDef::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoQueryDef` Objekt ist derzeit geöffnet.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoQueryDef` Objekt wird geöffnet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Querydef muss im geöffneten Zustand sein, bevor Sie ihn verwenden, rufen Sie [ausführen](#execute) oder zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt. Querydef entweder in einen Aufruf der geöffneten Zustand zu versetzen [erstellen](#create) (für neue Querydef) oder [öffnen](#open) (für eine vorhandene Querydef).  
  
##  <a name="a-namempdatabasea--cdaoquerydefmpdatabase"></a><a name="m_pdatabase"></a>CDaoQueryDef::m_pDatabase  
 Enthält einen Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt, das Querydef-Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger verwenden, wenn Sie direkt auf die Datenbank zugreifen müssen, z. B. zum Abrufen von Zeigern auf andere Querydef oder Recordset-Objekte in der Datenbank-Auflistungen.  
  
##  <a name="a-namempdaoquerydefa--cdaoquerydefmpdaoquerydef"></a><a name="m_pdaoquerydef"></a>CDaoQueryDef::m_pDAOQueryDef  
 Enthält einen Zeiger auf die OLE-Schnittstelle für das zugrunde liegende DAO Querydef-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Zeiger wird für die Vollständigkeit und Konsistenz mit anderen Klassen bereitgestellt. Da MFC stattdessen vollständig DAO Querydefs kapselt, können Sie jedoch wahrscheinlich nicht benötigen. Wenn Sie es verwenden, sollten Sie die Vorsicht – insbesondere ändern den Wert des Zeigers nicht, wenn Sie wissen, was Sie tun.  
  
##  <a name="a-nameopena--cdaoquerydefopen"></a><a name="open"></a>CDaoQueryDef::Open  
 Rufen Sie diese Memberfunktion zum Öffnen einer Querydef, die zuvor in der Datenbank QueryDefs-Auflistung gespeichert.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Eine Zeichenfolge mit dem Namen der gespeicherten Querydef zu öffnen. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Sobald die Querydef geöffnet ist, können Sie Aufrufen seiner [ausführen](#execute) Memberfunktion oder verwenden Sie die Querydef erstellen eine [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt.  
  
##  <a name="a-namesetconnecta--cdaoquerydefsetconnect"></a><a name="setconnect"></a>CDaoQueryDef::SetConnect  
 Rufen Sie diese Memberfunktion zum Festlegen der Verbindungszeichenfolge für das Querydef-Objekt.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszConnect`  
 Eine Zeichenfolge, die eine Verbindungszeichenfolge für den zugeordneten enthält [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Verbindungszeichenfolge wird zum Übergeben zusätzlicher Informationen an ODBC- und bestimmte ISAM-Treiber nach Bedarf verwendet. Er wird nicht für Microsoft Jet verwendet (. MDB)-Datenbanken.  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen ist, fügen Sie diese ein. MDB-Datenbank.  
  
 Legen Sie vor der Ausführung einer Querydef, die eine SQL-Pass-Through-Abfrage zu einer ODBC-Datenquelle darstellt, die Verbindungszeichenfolge mit `SetConnect` , und rufen Sie [SetReturnsRecords](#setreturnsrecords) an, ob die Abfrage Datensätze zurückgibt.  
  
 Weitere Informationen zur Struktur und Beispiele für die Verbindung die Komponenten der Verbindungszeichenfolge finden Sie unter dem Thema "Connect-Eigenschaft" DAO-Hilfe.  
  
##  <a name="a-namesetnamea--cdaoquerydefsetname"></a><a name="setname"></a>CDaoQueryDef::SetName  
 Rufen Sie diese Memberfunktion auf, Sie ggf. den Namen einer Querydef ändern, der nicht temporär ist.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Eine Zeichenfolge, die den neuen Namen für eine temporäre Abfrage in der zugeordneten enthält [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 QueryDef sind eindeutige, benutzerdefinierten Namen. Rufen Sie `SetName` vor Querydef-Objekt der QueryDefs-Auflistung angefügt wird.  
  
##  <a name="a-namesetodbctimeouta--cdaoquerydefsetodbctimeout"></a><a name="setodbctimeout"></a>CDaoQueryDef::SetODBCTimeout  
 Rufen Sie diese Memberfunktion, um die Frist fest, bevor ein Timeout für eine Abfrage mit einer ODBC-Datenquelle.  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>Parameter  
 *nODBCTimeout*  
 Die Anzahl der Sekunden, bevor eine Abfrage ist ein Timeout aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion können Sie die Standardzahl von Sekunden, bevor nachfolgende Vorgänge auf die verbundene Datenquelle "Timeout". Ein Vorgang kann aufgrund von Netzwerkproblemen Zugriff, übermäßige Abfrage Verarbeitungszeit usw. Timeout. Rufen Sie `SetODBCTimeout` vor dem Ausführen einer Abfrage mit diesem Querydef, wenn Sie den Timeoutwert für Abfragen ändern möchten. (Wie ODBC Verbindungen wiederverwendet, ist der Timeoutwert für alle Clients in derselben Verbindung identisch.)  
  
 Der Standardwert für Abfragetimeouts beträgt 60 Sekunden.  
  
##  <a name="a-namesetparamvaluea--cdaoquerydefsetparamvalue"></a><a name="setparamvalue"></a>CDaoQueryDef:: SetParamValue  
 Rufen Sie diese Memberfunktion um den Wert eines Parameters in der Querydef zur Laufzeit festzulegen.  
  
```  
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name des Parameters, dessen Wert festgelegt werden soll.  
  
 `varValue`  
 Der festzulegende Wert; Siehe Hinweise.  
  
 `nIndex`  
 Die Ordnungsposition des Parameters in der Querydef-Parameters-Auflistung. Sie können diesen Wert durch Aufrufe abrufen [GetParameterCount](#getparametercount) und [GetParameterInfo](#getparameterinfo).  
  
### <a name="remarks"></a>Hinweise  
 Die Parameter muss als Teil der SQL-Zeichenfolge der Querydef bereits eingerichtet haben. Sie können die Parameter nach Namen oder nach der Ordnungsposition in der Auflistung zugreifen.  
  
 Geben Sie den Wert festlegen als ein `COleVariant` Objekt. Weitere Informationen zum Festlegen der gewünschten Wert und geben Sie Ihre `COleVariant` Objekt, finden Sie unter Klasse [COleVariant](../../mfc/reference/colevariant-class.md).  
  
##  <a name="a-namesetreturnsrecordsa--cdaoquerydefsetreturnsrecords"></a><a name="setreturnsrecords"></a>CDaoQueryDef::SetReturnsRecords  
 Rufen Sie diese Memberfunktion als Teil des Prozesses zum Einrichten einer SQL-Pass-Through-Abfrage mit einer externen Datenbank.  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>Parameter  
 *bReturnsRecords*  
 Übergeben Sie **TRUE** , wenn die Abfrage auf eine externe Datenbank Datensätze; zurückgibt, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 In diesem Fall müssen Sie die Querydef erstellen und legen Sie die Eigenschaften, die mit anderen `CDaoQueryDef` Memberfunktionen. Eine Beschreibung der externe Datenbanken, finden Sie unter [SetConnect](#setconnect).  
  
##  <a name="a-namesetsqla--cdaoquerydefsetsql"></a><a name="setsql"></a>CDaoQueryDef::SetSQL  
 Rufen Sie diese Memberfunktion zum Festlegen der SQL-Anweisung, die die Querydef ausgeführt wird.  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSQL`  
 Eine Zeichenfolge, die eine vollständige SQL-Anweisung, die für die Ausführung geeignet. Das DBMS hängt die Syntax dieser Zeichenfolge, die die Abfrage als Zielversion verwendet. Eine Erläuterung der Syntax, die in der Microsoft Jet-Datenbankmodul verwendet finden Sie im Thema "Erstellen von SQL-Anweisungen in Code" in der DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Eine standardmäßige Verwendung für `SetSQL` ist das Einrichten einer Querydef-Objekt für die Verwendung in einer SQL-Pass-Through-Abfrage. (Die Syntax der SQL-Pass-Through-Abfragen auf dem Ziel-DBMS, finden Sie in der Dokumentation für das DBMS).  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)

