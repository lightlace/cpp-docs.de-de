---
title: CDaoQueryDef Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
dev_langs:
- C++
helpviewer_keywords:
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81e7d3b093da8127887878b2ac5f2af652f549c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef-Klasse
Stellt eine Abfragedefinition ("Querydef") dar, die in einer Datenbank gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Erstellt eine **CDaoQueryDef** Objekt. Rufen Sie als Nächstes **öffnen** oder **erstellen**, abhängig von Ihren Anforderungen.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoQueryDef:: Append](#append)|Fügt die Querydef QueryDefs-Auflistung für die Datenbank als eine gespeicherte Abfrage.|  
|[CDaoQueryDef::CanUpdate](#canupdate)|Gibt ungleich NULL, wenn die Abfrage die Datenbank aktualisiert werden kann.|  
|[CDaoQueryDef::Close](#close)|Schließt das Querydef-Objekt. Zerstören Sie das C++-Objekt, wenn Sie damit fertig sind.|  
|[CDaoQueryDef::Create](#create)|Erstellt das zugrunde liegende DAO Querydef-Objekt. Verwenden Sie die Querydef als eine temporäre Abfrage oder einen Aufruf **Append** in der Datenbank gespeichert.|  
|[CDaoQueryDef:: Execute](#execute)|Führt die Abfrage, die vom Objekt Querydef definiert.|  
|[CDaoQueryDef::GetConnect](#getconnect)|Gibt die Querydef zugeordnete Verbindungszeichenfolge zurück. Die Verbindungszeichenfolge identifiziert die Datenquelle an. (Für SQL-Abfragen Pass-Through-, andernfalls eine leere Zeichenfolge.)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Gibt das Datum der Erstellung die gespeicherte Abfrage zurück.|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Gibt das Datum der letzten Aktualisierung die gespeicherte Abfrage zurück.|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Gibt die Anzahl der Felder, die durch die Querydef definiert.|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Gibt Informationen zu einem bestimmten Feld in der Abfrage definiert.|  
|[CDaoQueryDef::GetName](#getname)|Gibt den Namen der Querydef zurück.|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|Gibt den Timeoutwert für ODBC (für eine ODBC-Abfrage) verwendeten zurück, wenn die Querydef ausgeführt wird. Dies bestimmt, wie lange auf die Abfrage Aktion abgeschlossen zu ermöglichen.|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Gibt die Anzahl von Parametern für die Abfrage definiert.|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Gibt Informationen über einen angegebenen Parameter auf die Abfrage zurück.|  
|[CDaoQueryDef:: GetParamValue](#getparamvalue)|Gibt den Wert eines angegebenen Parameters an die Abfrage zurück.|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Gibt die Anzahl der von einer Aktionsabfrage betroffenen Datensätze zurück.|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Gibt einen Wert ungleich NULL, wenn die Abfrage, die durch die Querydef definierten Datensätze zurückgibt.|  
|[CDaoQueryDef::GetSQL](#getsql)|Die SQL-Zeichenfolge, die angibt, die durch die Querydef definierte Abfrage zurückgegeben.|  
|[CDaoQueryDef::GetType](#gettype)|Gibt den Abfragetyp: löschen, aktualisieren, anfügen, Tabelle, und so weiter.|  
|[CDaoQueryDef::IsOpen](#isopen)|Gibt ungleich NULL zurück, falls die Querydef geöffnet ist und ausgeführt werden kann.|  
|[CDaoQueryDef::Open](#open)|Öffnet eine vorhandene Querydef in QueryDefs-Auflistung der Datenbank gespeichert.|  
|[CDaoQueryDef::SetConnect](#setconnect)|Legt die Verbindungszeichenfolge für eine SQL-Pass-Through-Abfrage für eine ODBC-Datenquelle fest.|  
|[CDaoQueryDef::SetName](#setname)|Legt den Namen der gespeicherten Abfragen, die den Namen in Verwendung zu ersetzen, wenn Querydef erstellt wurde.|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|Legt den Timeoutwert für ODBC (für eine ODBC-Abfrage) verwendeten Wenn Querydef ausgeführt wird.|  
|[CDaoQueryDef:: SetParamValue](#setparamvalue)|Legt den Wert eines angegebenen Parameters der Abfrage fest.|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Gibt an, ob die Querydef Datensätze zurückgibt. Wenn dieses Attribut auf **"true"** gilt nur für SQL Pass-Through-Abfragen.|  
|[CDaoQueryDef::SetSQL](#setsql)|Legt fest, die SQL-Zeichenfolge, die angibt, die durch die Querydef definierte Abfrage.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|Ein Zeiger auf die OLE-Schnittstelle für das zugrunde liegende DAO Querydef-Objekt.|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Ein Zeiger auf die `CDaoDatabase` Objekt der Querydef zugeordnet ist. Querydef kann oder nicht in der Datenbank gespeichert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Querydef ist ein Datenzugriffsobjekt, die die SQL-Anweisung enthält, die beschrieben wird eine Abfrage, und seine Eigenschaften, z. B. "Erstellungsdatum" und "ODBC-Timeout". Sie können auch temporäre Querydef-Objekte erstellen, ohne sie zu speichern, aber es ist praktisch – und wesentlich effizienter – wiederverwendet, speichern Sie häufig Abfragen in einer Datenbank. Ein [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) -Objekt verwaltet eine Auflistung mit dem Namen der QueryDefs-Auflistung, die, die die gespeicherten Querydefs enthält.  
  
> [!NOTE]
>  DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf der Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können dennoch den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC; die DAO-basierten Klassen können Daten, einschließlich der ODBC-Treiber, über eigene Datenbankmodul zugreifen. Die DAO-basierten Klassen unterstützen auch (Data Definition Language, Datendefinitionssprache)-Vorgänge, z. B. das Hinzufügen von Tabellen über die Klassen ohne DAO direkt aufrufen.  
  
## <a name="usage"></a>Verwendung  
 Verwenden Sie Querydef-Objekte entweder zum Arbeiten mit einer vorhandenen Abfrage gespeichert oder zum Erstellen einer neuen Abfrage oder temporäre Abfrage gespeichert:  
  
1.  In allen Fällen erstellen Sie zuerst eine `CDaoQueryDef` -Objekt, indem ein Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) -Objekt, der die Abfrage angehört.  
  
2.  Führen Sie dann die folgenden Einträge, je nachdem, was soll:  
  
    -   Rufen Sie zum Verwenden einer vorhandenen gespeicherten Abfrage des Objekts Querydef [öffnen](#open) Memberfunktion, die den Namen der gespeicherten Abfragen angeben.  
  
    -   Um eine neue gespeicherte Abfrage zu erstellen, rufen Sie des Querydef Objekts [erstellen](#create) Memberfunktion, die den Namen der Abfrage angeben. Rufen Sie anschließend [Append](#append) zum Speichern der Abfrage, indem er QueryDefs-Auflistung für die Datenbank angefügt werden. **Erstellen** versetzt Querydef in den geöffneten Zustand daher nach dem Aufruf **erstellen** rufen Sie nicht **öffnen**.  
  
    -   Rufen Sie zum Erstellen einer temporären Querydef **erstellen**. Übergeben Sie eine leere Zeichenfolge nach dem Abfragenamen. Rufen Sie nicht **Append**.  
  
 Aufrufen, wenn Sie fertig sind, mithilfe eines Querydef-Objekts, dessen [schließen](#close) Member-Funktion; zerstören Sie das Querydef-Objekt.  
  
> [!TIP]
>  Die einfachste Möglichkeit zum Erstellen von gespeicherten Abfragen wird Sie erstellt und in der Datenbank mit Microsoft Access zu speichern. Sie können dann öffnen und in der MFC-Code zu verwenden.  
  
## <a name="purposes"></a>Zweck  
 Sie können ein Querydef-Objekt für keines der folgenden Zwecken verwenden:  
  
-   Zum Erstellen einer `CDaoRecordset` Objekt  
  
-   Zum Aufrufen des Objekts **Execute** Memberfunktion versucht, eine Abfrage oder eine SQL-Pass-Through-Abfrage direkt ausführen  
  
 Verwenden Sie ein Querydef-Objekt für jeden Typ der Abfrage, einschließlich Select, Aktion, Kreuztabelle, Delete, Update, anfügen, Tabelle, Datendefinition, SQL Pass-Through-, Union, und massenabfragen. Typ der Abfrage wird durch den Inhalt der SQL-Anweisung bestimmt, die Sie angeben. Informationen zu Abfragetypen finden Sie unter der **Execute** und ["GetType"](#gettype) Memberfunktionen. Recordsets werden im Allgemeinen zum Zurückgeben von Zeilen abfragt, in der Regel die Verwendung der **auswählen... AUS** Schlüsselwörter. **Führen Sie** wird am häufigsten bei Massenvorgängen verwendet. Weitere Informationen finden Sie unter [Execute](#execute) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## <a name="querydefs-and-recordsets"></a>Querydefs und Recordsets  
 Ein Querydef-Objekt verwendet wird, zum Erstellen einer `CDaoRecordset` -Objekt, in der Regel erstellen oder öffnen eine Querydef, wie oben beschrieben. Erstellen Sie dann auf einem Recordset-Objekt, das die Übergabe eines Zeigers für Ihr Objekt Querydef beim Aufrufen [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open). Die Querydef, die Sie übergeben, muss sich im geöffneten Zustand. Weitere Informationen finden Sie in der Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Querydef können Sie einem Recordset (die gängigste Verwendung für eine Querydef) erstellen, wenn sie im geöffneten Zustand ist. Querydef in einem geöffneten Status versetzt, durch den Aufruf eines **öffnen** oder **erstellen**.  
  
## <a name="external-databases"></a>Externe Datenbanken  
 QueryDef-Objekte sind die bevorzugte Methode zum Verwenden des systemeigenen SQL-Dialekts von einer externen Datenbank-Engine. Sie können beispielsweise erstellen Sie eine Transact-SQL-Abfrage (wie in Microsoft SQL Server verwendet wird) und speichern Sie ihn in ein Querydef-Objekt. Wenn Sie eine SQL-Abfrage nicht basierend auf der Microsoft Jet-Datenbankmodul verwenden müssen, müssen Sie eine Verbindungszeichenfolge angeben, die auf der externen Datenquelle verweist. Abfragen mit gültiger Verbindungszeichenfolgen umgehen das Datenbankmodul und übergeben Sie die Abfrage direkt an den externen Datenbankserver für die Verarbeitung.  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen ist, um sie zu einer Microsoft Jet anzufügen (. MDB)-Datenbank.  
  
 Weitere Informationen finden Sie unter den Themen "QueryDef Object", "QueryDefs-Auflistung" und "CdbDatabase Object" in der DAO SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="append"></a>  CDaoQueryDef:: Append  
 Rufen Sie diese Memberfunktion auf, nach dem Aufruf [erstellen](#create) zum Erstellen eines neuen Querydef-Objekts.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Hinweise  
 **Append** Querydef in der Datenbank speichert, indem das Objekt QueryDefs-Auflistung für die Datenbank angefügt. Sie können die Querydef als temporäres Objekt verwenden, ohne angefügt, aber beibehalten werden sollen, müssen Sie aufrufen **Append**.  
  
 Wenn Sie versuchen, ein temporäres Querydef-Objekt angefügt werden soll, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="canupdate"></a>  CDaoQueryDef::CanUpdate  
 Rufen Sie diese Memberfunktion, um festzustellen, ob Sie die Querydef ändern können – z. B. das Ändern der Name oder die SQL-Zeichenfolge.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie so ändern Sie die Querydef zulässig sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Querydef ändern, wenn:  
  
-   Er basiert nicht auf eine Datenbank, die schreibgeschützt geöffnet ist.  
  
-   Sie haben die Update-Berechtigungen für die Datenbank.  
  
     Dies hängt davon ab, gibt an, ob Sie Sicherheitsfunktionen implementiert haben. MFC bietet keine Unterstützung für die Sicherheit. Sie müssen es selbst durch Aufrufen von DAO direkt oder mithilfe von Microsoft Access implementieren. Finden Sie im Thema "Berechtigungen Property" in der DAO-Hilfe aus.  
  
##  <a name="cdaoquerydef"></a>  CDaoQueryDef::CDaoQueryDef  
 Erstellt eine **CDaoQueryDef** Objekt.  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Parameter  
 `pDatabase`  
 Ein Zeiger auf ein offenes [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt kann es sich um eine vorhandene Querydef gespeichert, in der Datenbank QueryDefs-Auflistung, eine neue Abfrage in der Auflistung gespeichert werden oder eine temporäre Abfrage, nicht zu speichernde darstellen. Im nächste Schritt hängt vom Typ der Querydef ab:  
  
-   Wenn das Objekt eine vorhandene Querydef darstellt, rufen Sie des Objekts [öffnen](#open) Memberfunktion initialisiert werden.  
  
-   Wenn das Objekt eine neue Querydef zu speichernde darstellt, rufen Sie des Objekts [erstellen](#create) Memberfunktion. Dadurch wird die Datenbank QueryDefs-Auflistung des Objekts hinzugefügt. Rufen Sie anschließend `CDaoQueryDef` -Elementfunktion auf, die Attribute des Objekts festgelegt. Rufen Sie zum Schluss [Append](#append).  
  
-   Wenn das Objekt eine temporäre Querydef (nicht in der Datenbank gespeichert werden) darstellt, rufen Sie **erstellen**, übergeben eine leere Zeichenfolge für den Abfragenamen ein. Nach dem Aufruf **erstellen**, initialisieren Sie die Querydef, indem Sie direkt festlegen seiner Attribute. Rufen Sie nicht **Append**.  
  
 Um die Attribute der Querydef festzulegen, können Sie die [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout), und [SetReturnsRecords](#setreturnsrecords) Memberfunktionen.  
  
 Wenn Sie mit dem Objekt Querydef abgeschlossen haben, rufen Sie die [schließen](#close) Memberfunktion. Wenn Sie einen Zeiger auf die Querydef verfügen, verwenden die **löschen** Operator, um die C++-Objekt zu zerstören.  
  
##  <a name="close"></a>  CDaoQueryDef::Close  
 Rufen Sie diese Memberfunktion auf, wenn Sie fertig sind, mit dem DAO Querydef-Objekt.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Das zugrunde liegende DAO-Objekt frei jedoch nicht zerstört ist, die gespeicherte DAO Querydef-Objekt oder die C++-Querydef schließen `CDaoQueryDef` Objekt. Dies ist nicht identisch mit [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), Querydef aus der Datenbank QueryDefs-Auflistung in DAO (sofern keine temporäre Querydef) gelöscht.  
  
##  <a name="create"></a>  CDaoQueryDef::Create  
 Rufen Sie diese Memberfunktion, um eine neue gespeicherte Abfrage oder eine neue temporäre Abfrage zu erstellen.  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der eindeutige Name der Abfrage in der Datenbank gespeichert. Informationen dazu, die Zeichenfolge finden Sie im Thema "CreateQueryDef Method" DAO-Hilfe. Wenn Sie annehmen, dass den Standardwert eine leere Zeichenfolge ist, wird eine temporäre Querydef erstellt. Eine solche Abfrage ist nicht in der QueryDefs-Auflistung gespeichert.  
  
 `lpszSQL`  
 Die SQL-Zeichenfolge, die die Abfrage definiert. Wenn Sie den Standardwert übernehmen **NULL**, müssen Sie später Aufrufen [SetSQL](#setsql) zum Festlegen der Zeichenfolge. Bis dahin ist die Abfrage nicht definiert. Jedoch nicht definierte Abfrage können zu einem Recordset öffnen; Einzelheiten finden Sie unter "Hinweise". Die SQL-Anweisung muss definiert werden, bevor Sie auf die QueryDefs-Auflistung Querydef anfügen können.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen Namen im übergeben `lpszName`, rufen Sie dann [Append](#append) Querydef in der Datenbank QueryDefs-Auflistung zu speichern. Andernfalls wird das Objekt ist eine temporäre Querydef und wird nicht gespeichert. In beiden Fällen ist die Querydef im geöffneten Zustand, und entweder können Sie sie zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) -Objekt, oder rufen Sie der Querydef [Execute](#execute) Memberfunktion.  
  
 Wenn Sie nicht in eine SQL-Anweisung angeben `lpszSQL`, nicht möglich, führen Sie die Abfrage mit **Execute** jedoch können sie ein Recordset erstellen. In diesem Fall verwendet MFC das Recordset Standard-SQL-Anweisung.  
  
##  <a name="execute"></a>  CDaoQueryDef:: Execute  
 Rufen Sie diese Memberfunktion zum Ausführen der Abfrage, die vom Objekt Querydef definiert.  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Parameter  
 `nOptions`  
 Eine ganze Zahl, die die Merkmale der Abfrage bestimmt. Verwandte Informationen finden Sie im Thema "Execute-Methode" DAO-Hilfe. Können Sie den bitweisen OR-Operator ( **&#124;**) die folgenden Konstanten für dieses Argument zu kombinieren:  
  
- **DbDenyWrite** verweigern, anderen Benutzern Schreibberechtigung.  
  
- **DbInconsistent** inkonsistente Updates.  
  
- **DbConsistent** konsistenter Updates.  
  
- **DbSQLPassThrough** SQL Pass-Through. Bewirkt, dass die SQL-Anweisung mit einer ODBC-Datenbank für die Verarbeitung übergeben werden.  
  
- **DbFailOnError** Default-Wert. Rollback für Updates, wenn ein Fehler auftritt und der Bericht den Fehler an den Benutzer.  
  
- **DbSeeChanges** generieren einen Laufzeitfehler, wenn ein anderer Benutzer Daten ändert, die Sie bearbeiten.  
  
> [!NOTE]
>  Eine Erläuterung der Begriffe "inkonsistent" und "konsistent" sind, finden Sie im Thema "Execute-Methode" DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 QueryDef-Objekte, die verwendet werden, für die Ausführung auf diese Weise können Sie nur die folgenden Abfragetypen darstellen:  
  
-   Aktionsabfragen  
  
-   SQL-Pass-Through-Abfragen  
  
 **Führen Sie** funktioniert nicht für Abfragen, Zurückgeben von Datensätzen, z. B. select-Abfragen. **Führen Sie** wird häufig zum Abfragen der Bulk-Vorgang, z. B. **UPDATE**, **einfügen**, oder **SELECT INTO**, oder für Vorgänge Data Definition Language (DDL).  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Datenquellen Tabellen an einen Microsoft Jet angefügt wird (. MDB)-Datenbank. Weitere Informationen finden Sie im Thema "Zugreifen auf externe Datenbanken mit DAO" DAO-Hilfe.  
  
 Rufen Sie die [GetRecordsAffected](#getrecordsaffected) -Memberfunktion des Querydef-Objekts, um zu bestimmen, die Anzahl der Datensätze, die von der letzten betroffen **Execute** aufrufen. Beispielsweise `GetRecordsAffected` gibt Informationen über die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt, wenn eine Abfrage ausführen. Die zurückgegebene Anzahl der widerspiegelt Änderungen in verknüpften Tabellen, wenn Cascade aktualisiert oder löscht wirksam sind nicht.  
  
 Wenn Sie beide einschließen **DbInconsistent** und **DbConsistent** oder wenn Sie weder einschließen, wird das Ergebnis ist die Standardeinstellung **DbInconsistent**.  
  
 **Führen Sie** kein Recordset zurückgibt. Mit **Execute** auf einer Abfrage, die Datensätze auswählt bewirkt, dass MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="getconnect"></a>  CDaoQueryDef::GetConnect  
 Rufen Sie diese Memberfunktion zum Abrufen der Verbindungszeichenfolge die Querydef der Datenquelle zugeordnet.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält die Verbindungszeichenfolge für die Querydef.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nur mit ODBC-Datenquellen und bestimmte ISAM-Treiber verwendet. Es ist nicht mit Microsoft Jet verwendet (. MDB) Datenbanken; In diesem Fall `GetConnect` eine leere Zeichenfolge zurückgegeben. Weitere Informationen finden Sie unter [SetConnect](#setconnect).  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen zu Anfügen ist ein. MDB-Datenbank. Weitere Informationen finden Sie im Thema "Zugreifen auf externe Datenbanken mit DAO" DAO-Hilfe.  
  
 Informationen zu Verbindungszeichenfolgen finden Sie unter "Verbinden der Eigenschaft" DAO-Hilfe.  
  
##  <a name="getdatecreated"></a>  CDaoQueryDef::GetDateCreated  
 Rufen Sie diese Memberfunktion, um das Datum zu erhalten, die das Querydef-Objekt erstellt wurde.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt mit dem Datum und Uhrzeit, die Querydef erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="getdatelastupdated"></a>  CDaoQueryDef::GetDateLastUpdated  
 Diese Memberfunktion zum Abrufen des Querydef-Objekts durch des Datums der letzten Aktualisierung Aufruf – Wenn eine seiner Eigenschaften wurden geändert, z. B. seinen Namen, die SQL-Zeichenfolge oder der Verbindungszeichenfolge.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das das Datum und die Uhrzeit der letzten die Querydef Aktualisierung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="getfieldcount"></a>  CDaoQueryDef::GetFieldCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Felder in der Abfrage.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder in der Abfrage definiert.  
  
### <a name="remarks"></a>Hinweise  
 `GetFieldCount` eignet sich für alle Felder in der Querydef durchlaufen. Verwenden Sie zu diesem Zweck `GetFieldCount` in Verbindung mit [GetFieldInfo](#getfieldinfo).  
  
##  <a name="getfieldinfo"></a>  CDaoQueryDef::GetFieldInfo  
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
 Optionen, die angeben, welche Informationen das Feld abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:  
  
- `AFX_DAO_PRIMARY_INFO` (Standard) Name, Typ, Größe, Attribute  
  
- `AFX_DAO_SECONDARY_INFO` Primäre Informationen plus: Ordnungsposition, die erforderlich sind, der Länge NULL zulassen, Quellfeld, ausländischen Name, Quelltabelle, Reihenfolge sortieren  
  
- `AFX_DAO_ALL_INFO` Primäre und sekundäre Informationen plus: Default Value Text zu, Validierungsregel  
  
 `lpszName`  
 Eine Zeichenfolge, die mit dem Namen des gewünschten Felds für die Suche nach Namen. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Informationen zurückgegeben `fieldinfo`, finden Sie unter der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur enthält Member, die beschreibende Informationen unter entsprechen `dwInfoOptions` oben. Wenn Sie eine Ebene Informationen anfordern, erhalten Sie alle vorherigen Ebenen sowie Informationen.  
  
##  <a name="getname"></a>  CDaoQueryDef::GetName  
 Rufen Sie diese Memberfunktion um den Namen der Querydef dargestellte Abfrage abzurufen.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Abfrage.  
  
### <a name="remarks"></a>Hinweise  
 DAO Querydef sind eindeutige, benutzerdefinierten Namen. Weitere Informationen zu Querydef-Namen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getodbctimeout"></a>  CDaoQueryDef::GetODBCTimeout  
 Rufen Sie diese Memberfunktion zum Abrufen von der aktuellen Zeitlimit bis zum Timeout einer Abfrage mit einer ODBC-Datenquelle.  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Sekunden, bevor Sie eine Abfrage ein Timeout eintritt.  
  
### <a name="remarks"></a>Hinweise  
 Informationen über dieses Zeitlimit finden Sie unter im Thema "Timeoutfehlers warten soll Property" in der DAO-Hilfe.  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen ist, um sie zu einer Microsoft Jet anzufügen (. MDB)-Datenbank. Weitere Informationen finden Sie im Thema "Zugreifen auf externe Datenbanken mit DAO" DAO-Hilfe.  
  
##  <a name="getparametercount"></a>  CDaoQueryDef::GetParameterCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Parametern in gespeicherten Abfragen.  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in der Abfrage definierten Parametern.  
  
### <a name="remarks"></a>Hinweise  
 `GetParameterCount` eignet sich für alle Parameter in der Querydef durchlaufen. Verwenden Sie zu diesem Zweck `GetParameterCount` in Verbindung mit [GetParameterInfo](#getparameterinfo).  
  
 Weitere Informationen finden Sie unter den Themen "Parameterobjekt", "Parameters-Auflistung" und "Parameter Deklaration (SQL)" in der DAO-Hilfe.  
  
##  <a name="getparameterinfo"></a>  CDaoQueryDef::GetParameterInfo  
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
 Der nullbasierte Index des gewünschten Parameters im Parameters-Auflistung der Querydef für die Suche nach Index.  
  
 `paraminfo`  
 Ein Verweis auf eine [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen zu den abzurufenden Parameters. Hier ist die verfügbare Option aufgeführt, zusammen mit Was führt die Funktion zurückgibt:  
  
- `AFX_DAO_PRIMARY_INFO` (Standard) Name, Typ  
  
 `lpszName`  
 Eine Zeichenfolge, die mit dem Namen des gewünschten Parameters für die Suche nach Namen. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Informationen zurückgegeben `paraminfo`, finden Sie unter der [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) Struktur. Diese Struktur enthält Member, die beschreibende Informationen unter entsprechen `dwInfoOptions` oben.  
  
 Verwandte Informationen finden Sie im Thema "Parameter Deklaration (SQL)" in der DAO-Hilfe.  
  
##  <a name="getparamvalue"></a>  CDaoQueryDef:: GetParamValue  
 Rufen Sie diese Memberfunktion zum Abrufen des aktuellen Wert des angegebenen Parameters im Parameters-Auflistung der Querydef gespeichert.  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name des Parameters, dessen Wert für die Suche nach dem Namen möchten.  
  
 `nIndex`  
 Der nullbasierte Index des Parameters im Parameters-Auflistung der Querydef für die Suche nach Index. Sie können diesen Wert durch Aufrufe von abrufen [GetParameterCount](#getparametercount) und [GetParameterInfo](#getparameterinfo).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt der Klasse [COleVariant](../../mfc/reference/colevariant-class.md) , die den Wert des Parameters enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Parameter nach Namen oder ihre Ordnungsposition in der Auflistung zugreifen.  
  
 Verwandte Informationen finden Sie im Thema "Parameter Deklaration (SQL)" in der DAO-Hilfe.  
  
##  <a name="getrecordsaffected"></a>  CDaoQueryDef::GetRecordsAffected  
 Rufen Sie diese Memberfunktion, um zu bestimmen, wie viele Datensätze nach dem letzten Aufruf von betroffenen [Execute](#execute).  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der betroffenen Datensätze.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Anzahl der widerspiegelt Änderungen in verknüpften Tabellen, wenn Cascade aktualisiert oder löscht wirksam sind nicht.  
  
 Weitere Informationen finden Sie im Thema "RecordsAffected-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getreturnsrecords"></a>  CDaoQueryDef::GetReturnsRecords  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Querydef basiert auf einer Abfrage, die Datensätze zurückgibt.  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Querydef auf einer Abfrage basiert, die Datensätze zurückgibt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird nur für SQL Pass-Through-Abfragen verwendet. Weitere Informationen zu SQL-Abfragen finden Sie unter der [Execute](#execute) Memberfunktion. Weitere Informationen zum Arbeiten mit SQL-Pass-Through-Abfragen finden Sie unter der [SetReturnsRecords](#setreturnsrecords) Memberfunktion.  
  
 Verwandte Informationen finden Sie im Thema "ReturnsRecords-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getsql"></a>  CDaoQueryDef::GetSQL  
 Rufen Sie diese Memberfunktion zum Abrufen von der SQL-Anweisung, die die Abfrage definiert, auf der die Querydef basiert.  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die SQL-Anweisung, die die Abfrage definiert, auf der die Querydef basiert.  
  
### <a name="remarks"></a>Hinweise  
 Sie werden dann wahrscheinlich die Zeichenfolge für die Schlüsselwörter, Tabellennamen, Spaltennamen usw. analysieren.  
  
 Weitere Informationen finden Sie unter den Themen "SQL-Eigenschaft", "Vergleich von Microsoft Jet-Datenbank-Engine SQL und ANSI SQL" und "Abfragen einer Datenbank mit SQL im Code" DAO-Hilfe.  
  
##  <a name="gettype"></a>  CDaoQueryDef::GetType  
 Rufen Sie diese Memberfunktion, um die Abfrage die Querydef zu bestimmen.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ der Abfrage von Querydef definiert. Werte finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Der Abfragetyp wird durch was Sie in der Querydef SQL-Zeichenfolge angeben, wenn Sie Querydef erstellen, oder rufen Sie einer vorhandenen Querydef festgelegt [SetSQL](#setsql) Memberfunktion. Der Abfragetyp, der von dieser Funktion zurückgegebenen ist einer der folgenden Werte möglich:  
  
- **DbQSelect** auswählen  
  
- **DbQAction** Aktion  
  
- **DbQCrosstab** Kreuztabelle  
  
- **DbQDelete** löschen  
  
- **DbQUpdate** Update  
  
- **DbQAppend** Anfügen  
  
- **DbQMakeTable** Tabellenerstellungsabfrage  
  
- **DbQDDL** Datendefinition  
  
- **DbQSQLPassThrough** Pass-Through-  
  
- **DbQSetOperation** Union  
  
- **DbQSPTBulk** mit verwendet **DbQSQLPassThrough** eine Abfrage angeben, die keinen Datensätze zurückgibt.  
  
> [!NOTE]
>  Um eine SQL-Pass-Through-Abfrage zu erstellen, legen Sie nicht die **DbSQLPassThrough** konstant. Dies wird automatisch vom Microsoft Jet-Datenbankmodul festgelegt, wenn Sie eine Querydef-Serverobjekt erstellen und legen die Verbindungszeichenfolge.  
  
 Weitere Informationen zu SQL-Zeichenfolgen, finden Sie unter [GetSQL](#getsql). Informationen zu Abfragetypen finden Sie unter [Execute](#execute).  
  
##  <a name="isopen"></a>  CDaoQueryDef::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoQueryDef` Objekt ist derzeit geöffnet.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoQueryDef` Objekt ist derzeit geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Querydef muss im geöffneten Zustand sein, bevor Sie ihn verwenden, rufen Sie [Execute](#execute) oder zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt. Eine Querydef entweder in einen Aufruf der geöffneten Zustand zu versetzen [erstellen](#create) (für eine neue Querydef) oder [öffnen](#open) (für eine vorhandene Querydef).  
  
##  <a name="m_pdatabase"></a>  CDaoQueryDef::m_pDatabase  
 Enthält einen Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt, das mit dem DAO Querydef-Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger verwenden, wenn Sie direkt auf die Datenbank zugreifen müssen, z. B. zum Abrufen von Zeigern auf andere Querydef oder ein Recordset-Objekte in der Datenbank-Auflistungen.  
  
##  <a name="m_pdaoquerydef"></a>  CDaoQueryDef::m_pDAOQueryDef  
 Enthält einen Zeiger auf die OLE-Schnittstelle für das zugrunde liegende DAO Querydef-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger wird für die Vollständigkeit und Konsistenz mit anderen Klassen bereitgestellt. Da MFC vielmehr vollständig DAO Querydef kapselt, entsprechen Sie jedoch wahrscheinlich nicht benötigen. Wenn Sie es verwenden, holen Sie dies mit Vorsicht – insbesondere ändern den Wert des Zeigers nicht, wenn Sie wissen, was Sie tun.  
  
##  <a name="open"></a>  CDaoQueryDef::Open  
 Rufen Sie diese Memberfunktion zum Öffnen einer Querydef, die zuvor in der Datenbank QueryDefs-Auflistung gespeichert.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Eine Zeichenfolge mit dem Namen der gespeicherten Querydef zu öffnen. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Sobald die Querydef geöffnet ist, können Sie Aufrufen seiner [Execute](#execute) Memberfunktion oder verwenden Sie die Querydef erstellen eine [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt.  
  
##  <a name="setconnect"></a>  CDaoQueryDef::SetConnect  
 Rufen Sie diese Memberfunktion zum Festlegen der Verbindungszeichenfolge für das Querydef-Objekt.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszConnect`  
 Eine Zeichenfolge, eine Verbindungszeichenfolge für den zugeordneten enthält [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Verbindungszeichenfolge wird verwendet, um zusätzliche Informationen auf ODBC und bestimmte ISAM-Treiber nach Bedarf zu übergeben. Er wird nicht für Microsoft Jet verwendet (. Datenbanken, MDB).  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen zu Anfügen ist ein. MDB-Datenbank.  
  
 Legen Sie vor dem Ausführen einer Querydef, die mit einer ODBC-Datenquelle eine SQL-Pass-Through-Abfrage darstellt, die Verbindungszeichenfolge mit `SetConnect` , und rufen Sie [SetReturnsRecords](#setreturnsrecords) angeben, ob die Abfrage Datensätze zurückgibt.  
  
 Weitere Informationen zu Struktur und Beispiele für die Komponenten Verbindungszeichenfolge der Verbindungszeichenfolge finden Sie im Thema "Verbinden der Eigenschaft" DAO-Hilfe.  
  
##  <a name="setname"></a>  CDaoQueryDef::SetName  
 Rufen Sie diese Memberfunktion auf, sollten Sie den Namen einer Querydef ändern, der nicht temporär ist.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Eine Zeichenfolge, der neue Name für eine temporäre Abfrage in der zugeordneten enthält [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 DAO Querydef sind eindeutige, benutzerdefinierten Namen. Sie können Aufrufen `SetName` vor Querydef Objekt wird an die QueryDefs-Auflistung angefügt.  
  
##  <a name="setodbctimeout"></a>  CDaoQueryDef::SetODBCTimeout  
 Rufen Sie diese Memberfunktion zum Festlegen des Zeitlimits, bis zum Timeout einer Abfrage mit einer ODBC-Datenquelle.  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>Parameter  
 *nODBCTimeout*  
 Die Anzahl der Sekunden, bevor Sie eine Abfrage ein Timeout eintritt.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion können Sie überschreiben die Standardanzahl von Sekunden, bevor nachfolgende Vorgänge in der verbundenen Datenquelle "Timeout". Ein Vorgang möglicherweise aufgrund von Netzwerkproblemen-Zugriff, übermäßige Abfrage Verarbeitungszeit und usw. Timeout. Rufen Sie `SetODBCTimeout` vor dem Ausführen einer Abfrage mit diesem DAO Querydef, wenn Sie den Timeoutwert für Abfragen ändern möchten. (Wie ODBC Verbindungen wiederverwendet wird, ist der Timeoutwert für alle Clients in der gleichen Verbindung identisch.)  
  
 Der Standardwert für Abfragetimeouts ist 60 Sekunden.  
  
##  <a name="setparamvalue"></a>  CDaoQueryDef:: SetParamValue  
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
 Der festzulegende Wert; finden Sie unter "Hinweise".  
  
 `nIndex`  
 Die Ordnungsposition des Parameters in der Querydef Parameters-Auflistung. Sie können diesen Wert durch Aufrufe von abrufen [GetParameterCount](#getparametercount) und [GetParameterInfo](#getparameterinfo).  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter muss bereits als Teil der SQL-Zeichenfolge der Querydef eingerichtet wurde. Sie können die Parameter nach Namen oder ihre Ordnungsposition in der Auflistung zugreifen.  
  
 Geben Sie den Wert für die festzulegende als ein `COleVariant` Objekt. Weitere Informationen zum Festlegen der gewünschten Wert und geben Sie Ihre `COleVariant` Objekt, finden Sie unter Klasse [COleVariant](../../mfc/reference/colevariant-class.md).  
  
##  <a name="setreturnsrecords"></a>  CDaoQueryDef::SetReturnsRecords  
 Rufen Sie diese Memberfunktion als Teil des Prozesses zum Einrichten einer SQL-Pass-Through-Abfrage mit einer externen Datenbank.  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>Parameter  
 *bReturnsRecords*  
 Übergeben Sie **"true"** Wenn die Abfrage auf einer externen Datenbank Datensätze; zurückgibt, andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 In diesem Fall müssen Sie erstellen die Querydef und legen Sie die Eigenschaften, die mit anderen `CDaoQueryDef` Memberfunktionen. Eine Beschreibung der externen Datenbanken, finden Sie unter [SetConnect](#setconnect).  
  
##  <a name="setsql"></a>  CDaoQueryDef::SetSQL  
 Rufen Sie diese Memberfunktion zum Festlegen der SQL-Anweisung, die die Querydef ausgeführt wird.  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSQL`  
 Eine Zeichenfolge, enthält eine vollständige SQL-Anweisung, die für die Ausführung geeignet ist. Das DBMS hängt die Syntax dieser Zeichenfolge, die das Abfrage-abzielt. Eine Erläuterung der Syntax, die in der Microsoft Jet-Datenbankmodul verwendet finden Sie im Thema "Erstellen von SQL-Anweisungen in Code" in der DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Ein typisches Einsatzgebiet von `SetSQL` ist das Einrichten einer Querydef-Objekt für die Verwendung in einer SQL-Pass-Through-Abfrage. (Die Syntax der SQL-Pass-Through-Abfragen auf dem Ziel-DBMS, finden Sie in der Dokumentation für das DBMS).  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
