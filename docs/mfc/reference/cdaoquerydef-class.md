---
title: CDaoQueryDef-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 24aeac6c19a481f3be8d6555862c9631cb1672b1
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339448"
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
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Erstellt ein `CDaoQueryDef`-Objekt. Rufen Sie als Nächstes `Open` oder `Create`, je nach Ihren Anforderungen.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoQueryDef:: Append](#append)|Fügt die Querydef QueryDefs-Auflistung als gespeicherte Abfrage der Datenbank an.|  
|[CDaoQueryDef::CanUpdate](#canupdate)|Gibt, die ungleich NULL, wenn die Abfrage die Datenbank aktualisiert werden kann.|  
|[CDaoQueryDef::Close](#close)|Schließt das Querydef-Objekt. Zerstören Sie das C++-Objekt, wenn Sie damit fertig sind.|  
|[CDaoQueryDef::Create](#create)|Erstellt das zugrunde liegende DAO Querydef-Objekt. Verwenden Sie die Querydef als temporäre Abfrage oder Aufruf `Append` in der Datenbank zu speichern.|  
|[CDaoQueryDef:: Execute](#execute)|Führt die Abfrage, die vom Objekt Querydef definiert wird.|  
|[CDaoQueryDef::GetConnect](#getconnect)|Gibt die Querydef zugeordnete Verbindungszeichenfolge zurück. Die Verbindungszeichenfolge identifiziert die Datenquelle. (Für SQL-Abfragen Pass-Through- andernfalls eine leere Zeichenfolge.)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Gibt das Datum, an das die gespeicherte Abfrage erstellt wurde.|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Gibt das Datum, an das die gespeicherte Abfrage zuletzt aktualisiert wurde.|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Gibt die Anzahl der von der Querydef definierten Felder zurück.|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Gibt Informationen zu einem bestimmten Feld in der Abfrage definiert.|  
|[CDaoQueryDef::GetName](#getname)|Der Name des Querydef zurückgegeben.|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|Gibt den Timeoutwert für ODBC (für eine ODBC-Abfrage) verwendeten zurück, wenn die Querydef ausgeführt wird. Dies bestimmt, wie lange der Abfrage Aktion zu ermöglichen.|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Gibt die Anzahl von Parametern, die für die Abfrage definiert.|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Gibt Informationen über einen angegebenen Parameter für die Abfrage zurück.|  
|[CDaoQueryDef:: GetParamValue](#getparamvalue)|Der Wert eines angegebenen Parameters werden der Abfrage zurückgegeben.|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Gibt die Anzahl der Datensätze, die von einer Aktionsabfrage betroffen sind.|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Gibt zurück, ungleich NULL, wenn die Abfrage, die durch die Querydef definierten Datensätze zurückgibt.|  
|[CDaoQueryDef::GetSQL](#getsql)|Die SQL-Zeichenfolge, die angibt, die durch die Querydef definierte Abfrage zurückgegeben.|  
|[CDaoQueryDef::GetType](#gettype)|Gibt den Abfragetyp zurück: löschen, aktualisieren, anzufügen, Tabelle, und so weiter.|  
|[CDaoQueryDef::IsOpen](#isopen)|Gibt ungleich NULL zurück, wenn die Querydef geöffnet ist und ausgeführt werden kann.|  
|[CDaoQueryDef::Open](#open)|Öffnet eine vorhandene Querydef in der Datenbank QueryDefs-Auflistung gespeichert.|  
|[CDaoQueryDef::SetConnect](#setconnect)|Legt die Verbindungszeichenfolge für eine SQL-Pass-Through-Abfrage für eine ODBC-Datenquelle fest.|  
|[CDaoQueryDef::SetName](#setname)|Legt den Namen der gespeicherten Abfrage, und Ersetzen Sie dabei den Namen verwendet als die Querydef erstellt wurde.|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|Legt den Timeoutwert für ODBC (für eine ODBC-Abfrage) verwendeten Wenn Querydef ausgeführt wird.|  
|[CDaoQueryDef:: SetParamValue](#setparamvalue)|Legt den Wert eines angegebenen Parameters für die Abfrage fest.|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Gibt an, ob die Querydef Datensätze zurückgibt. Wenn dieses Attribut auf "true" ist nur für SQL Pass-Through-Abfragen gültig.|  
|[CDaoQueryDef::SetSQL](#setsql)|Legt fest, die SQL-Zeichenfolge, die angibt, die durch die Querydef definierte Abfrage.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|Ein Zeiger auf die OLE-Schnittstelle für das zugrunde liegende DAO Querydef-Objekt.|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Ein Zeiger auf die `CDaoDatabase` Objekt dem Querydef zugeordnet ist. Die Querydef kann oder nicht in der Datenbank gespeichert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Querydef ist ein Datenzugriffsobjekt, die die SQL-Anweisung enthält, die beschreibt, eine Abfrage, und alle Eigenschaften, z. B. "Erstellungsdatum" und "ODBC-Timeout". Sie können auch temporäre Querydef-Objekte erstellen, ohne sie zu speichern, aber es ist praktisch, – und sehr viel effizienter, zum Speichern häufig wiederverwendet Abfragen in einer Datenbank. Ein [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) -Objekt verwaltet eine Sammlung mit dem Namen der QueryDefs-Auflistung, die die gespeicherten Querydefs enthält.  
  
> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von der MFC-Datenbankklassen in Bezug auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können weiterhin den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC; die DAO-basierten Klassen können Daten, einschließlich über ODBC-Treiber, über eigene Datenbank-Engine zugreifen. Die DAO-basierten Klassen unterstützen auch Vorgänge wie das Hinzufügen von Tabellen über die Klassen, ohne direkt aufrufen von DAO (Data Definition Language, Datendefinitionssprache).  
  
## <a name="usage"></a>Verwendung  
 Verwenden Sie Querydef Objekte funktioniert mit einer vorhandenen Abfrage gespeichert oder zum Erstellen einer neuen Abfrage oder temporäre Abfrage gespeichert:  
  
1.  In allen Fällen erstellen Sie zunächst eine `CDaoQueryDef` -Objekt, indem einen Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekts, zu dem die Abfrage gehört.  
  
2.  Führen Sie Folgendes, je nachdem, was soll:  
  
    -   Rufen Sie zum Verwenden einer vorhandenen gespeicherten Abfrage des Objekts Querydef [öffnen](#open) Member-Funktion, die den Namen der gespeicherten Abfrage angeben.  
  
    -   Rufen Sie zum Erstellen einer neuen gespeicherten Abfrage des Objekts Querydef [erstellen](#create) Member-Funktion, die den Namen der Abfrage angeben. Rufen Sie anschließend [Append](#append) zum Speichern der Abfrage, indem er an der Datenbank QueryDefs-Auflistung angehängt. `Create` setzt die Querydef in einem geöffneten Zustand, also nach dem Aufruf `Create` nicht aufgerufen `Open`.  
  
    -   Rufen Sie zum Erstellen einer temporären Querydef `Create`. Übergeben Sie eine leere Zeichenfolge für den Namen der Abfrage. Rufen Sie `Append` nicht auf.  
  
 Aufrufen, wenn Sie fertig sind, mit einem Querydef-Objekt, dessen [schließen](#close) Member funktioniert, klicken Sie dann die Querydef-Objekt zu zerstören.  
  
> [!TIP]
>  Die einfachste Möglichkeit zum Erstellen von gespeicherten Abfragen, werden sie erstellen und speichern sie in der Datenbank mithilfe von Microsoft Access ab. Anschließend können Sie öffnen und in Ihrer MFC-Code verwenden.  
  
## <a name="purposes"></a>Zweck  
 Sie können ein Querydef-Objekt für eine der folgenden Zwecken verwenden:  
  
-   Zum Erstellen einer `CDaoRecordset` Objekt  
  
-   Zum Aufrufen des Objekts `Execute` Memberfunktion, wird eine Abfrage oder eine SQL-Pass-Through-Abfrage direkt auszuführen  
  
 Sie können verwenden ein Querydef-Objekt für jede Art von Abfrage, einschließlich Select, Aktion, einer Kreuztabelle, Delete, Update, anzufügen, Tabellenerstellungsabfrage, Datendefinition, SQL Pass-Through-, Union, und massenabfragen. Der Abfragetyp wird durch den Inhalt der SQL-Anweisung bestimmt, die Sie angeben. Weitere Informationen zu Abfragetypen, finden Sie unter den `Execute` und [GetType](#gettype) Memberfunktionen. Recordsets dienen meist zum Zurückgeben von Zeilen abfragt, in der Regel die Verwendung der **auswählen... VON** Schlüsselwörter. `Execute` wird am häufigsten für Massenvorgänge verwendet. Weitere Informationen finden Sie unter [Execute](#execute) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## <a name="querydefs-and-recordsets"></a>Querydefs und Recordsets  
 Ein Querydef-Objekt verwendet wird, zum Erstellen einer `CDaoRecordset` -Objekt, in der Regel erstellen oder öffnen eine Querydef wie oben beschrieben. Erstellen Sie dann auf einem Recordset-Objekt, das die Übergabe eines Zeigers auf das Objekt Querydef beim Aufrufen [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open). Die Querydef, die Sie übergeben muss sich im geöffneten Zustand. Weitere Informationen finden Sie in der Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Eine Querydef können kein Recordsets (Dies ist die häufigste Verwendung für eine Querydef) erstellen, wenn sie im geöffneten Zustand ist. Querydef in einer geöffneten Zustand zu versetzen, durch Aufrufen von entweder `Open` oder `Create`.  
  
## <a name="external-databases"></a>Externe Datenbanken  
 QueryDef-Objekte sind die bevorzugte Methode für die native SQL-abfragedialekt von einer externen Datenbank-Engine verwenden. Sie können beispielsweise erstellen Sie eine Transact-SQL-Abfrage (wie in Microsoft SQL Server) und speichern Sie sie in einem Querydef-Objekt. Wenn Sie eine SQL-Abfrage nicht basierend auf der Microsoft Jet-Datenbank-Engine verwenden möchten, müssen Sie eine Verbindungszeichenfolge angeben, die auf der externen Datenquelle verweist. Abfragen mit gültiger Verbindungszeichenfolgen umgehen die Datenbank-Engine und übergeben Sie die Abfrage direkt an den externen Datenbankserver für die Verarbeitung.  
  
> [!TIP]
>  Anhängen an einen Microsoft Jet ist die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen (. MDB)-Datenbank.  
  
 Weitere Informationen finden Sie unter den Themen "QueryDef Object", "QueryDefs-Auflistung" und "CdbDatabase Object" in das DAO SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="append"></a>  CDaoQueryDef:: Append  
 Rufen Sie diese Memberfunktion auf, nach dem Aufruf von [erstellen](#create) zum Erstellen eines neuen Querydef-Objekts.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Hinweise  
 `Append` Speichert die Querydef in der Datenbank durch Anfügen von das-Objekt an der Datenbank QueryDefs-Auflistung. Sie können Querydef als temporäres Objekt verwenden, ohne sie angefügt, aber wenn beibehalten werden soll, müssen Sie aufrufen `Append`.  
  
 Wenn Sie versuchen, ein temporäres Querydef-Objekt angefügt werden soll, löst MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="canupdate"></a>  CDaoQueryDef::CanUpdate  
 Rufen Sie diese Memberfunktion, um festzustellen, ob Sie die Querydef ändern können, z. B. das Ändern der Name oder die SQL-Zeichenfolge.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Sie so ändern Sie die Querydef zulässig sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Querydef ändern, wenn:  
  
-   Er basiert nicht auf eine Datenbank, die schreibgeschützt geöffnet ist.  
  
-   Sie haben die Update-Berechtigungen für die Datenbank.  
  
     Dies hängt davon ab, ob Sie Sicherheitsfunktionen implementiert haben. MFC bietet keine Unterstützung für die Sicherheit. Sie müssen sie sich durch Aufrufen von DAO direkt oder mithilfe von Microsoft Access implementieren. Finden Sie im Thema "Berechtigungen Property" in-DAO-Hilfe aus.  
  
##  <a name="cdaoquerydef"></a>  CDaoQueryDef::CDaoQueryDef  
 Erstellt ein `CDaoQueryDef`-Objekt.  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Parameter  
 *pDatabase*  
 Ein Zeiger auf ein offenes [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt kann es sich um eine vorhandene Querydef gespeichert, in der Datenbank QueryDefs-Auflistung, eine neue Abfrage in der Auflistung gespeichert werden oder eine temporäre Abfrage nicht gespeichert werden sollen darstellen. Der nächste Schritt hängt davon ab, auf dem Typ des Querydef:  
  
-   Aufrufen des Objekts, wenn das Objekt eine vorhandene Querydef darstellt, [öffnen](#open) Memberfunktion, um es zu initialisieren.  
  
-   Wenn das Objekt eine neue Querydef gespeichert werden, steht, Aufrufen des Objekts [erstellen](#create) Member-Funktion. Dadurch wird der Datenbank QueryDefs-Auflistung des Objekts hinzugefügt. Rufen Sie anschließend `CDaoQueryDef` Member-Funktionen, um die Attribute des Objekts festzulegen. Rufen Sie zum Schluss [Append](#append).  
  
-   Wenn das Objekt eine temporäre Querydef (nicht in der Datenbank gespeichert werden) dargestellt wird, rufen Sie `Create`, übergeben eine leere Zeichenfolge für die Abfrage den Namen. Nach dem Aufruf `Create`, initialisieren Sie die Querydef, indem Sie direkt festlegen seiner Attribute. Rufen Sie `Append` nicht auf.  
  
 Um die Attribute der Querydef festzulegen, können Sie die [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout), und [SetReturnsRecords](#setreturnsrecords) Memberfunktionen.  
  
 Wenn Sie mit dem Objekt Querydef abgeschlossen haben, rufen Sie die [schließen](#close) Member-Funktion. Wenn Sie einen Zeiger auf die Querydef verfügen, verwenden die **löschen** Operator, um die C++-Objekt zu zerstören.  
  
##  <a name="close"></a>  CDaoQueryDef::Close  
 Rufen Sie diese Memberfunktion auf, wenn Sie fertig sind, mit dem Querydef-Objekt.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Querydef schließen das zugrunde liegende DAO-Objekt frei, jedoch nicht zerstört das gespeicherte Objekt der DAO-Querydef oder C++ `CDaoQueryDef` Objekt. Dies ist nicht identisch mit [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), dabei wird die Querydef aus der Datenbank QueryDefs-Auflistung in-DAO-(sofern keiner temporären Querydef).  
  
##  <a name="create"></a>  CDaoQueryDef::Create  
 Rufen Sie diese Memberfunktion, um eine neue gespeicherte Abfrage oder eine neue temporäre Abfrage zu erstellen.  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der eindeutige Name der Abfrage in der Datenbank gespeichert. Informationen dazu, die Zeichenfolge finden Sie im Thema "CreateQueryDef Method" in-DAO-Hilfe. Wenn Sie zustimmen, dass den Standardwert eine leere Zeichenfolge ist, wird eine temporäre Querydef erstellt. Eine solche Abfrage wird nicht in der QueryDefs-Auflistung gespeichert.  
  
 *lpszSQL*  
 Die SQL-Zeichenfolge, die die Abfrage definiert. Wenn Sie den Standardwert NULL annehmen, müssen Sie später Aufrufen [SetSQL](#setsql) zum Festlegen der Zeichenfolge. Bis dahin ist die Abfrage nicht definiert. Sie können jedoch die nicht definierte Abfrage verwenden, um zu einem Recordset zu öffnen; Einzelheiten finden Sie unter "Hinweise". Die SQL-Anweisung muss definiert werden, bevor Sie die Querydef der QueryDefs-Auflistung anfügen können.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen Namen im übergeben *Wert*, rufen Sie anschließend [Append](#append) Querydef in der Datenbank QueryDefs-Auflistung zu speichern. Andernfalls wird das Objekt ist eine temporäre Querydef und wird nicht gespeichert. In beiden Fällen wird die Querydef im geöffneten Zustand ist, und entweder können Sie sie zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, oder rufen Sie die Querydef [Execute](#execute) Member-Funktion.  
  
 Wenn Sie nicht in eine SQL-Anweisung angeben *LpszSQL*, Sie können nicht ausgeführt, die Abfrage mit `Execute` jedoch können Sie sie einem Recordset zu erstellen. In diesem Fall verwendet MFC die Recordset Standard-SQL-Anweisung.  
  
##  <a name="execute"></a>  CDaoQueryDef:: Execute  
 Rufen Sie diese Memberfunktion zum Ausführen der Abfrage, die vom Objekt Querydef definiert wird.  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Parameter  
 *nOptions*  
 Eine ganze Zahl, die die Merkmale der Abfrage bestimmt. Verwandte Informationen finden Sie im Thema "Execute-Methode" in-DAO-Hilfe. Können Sie den bitweisen OR-Operator ( **&#124;**) die folgenden Konstanten für dieses Argument kombinieren:  
  
- `dbDenyWrite` Schreibberechtigung auf anderen Benutzern verweigert.  
  
- `dbInconsistent` Inkonsistente Updates.  
  
- `dbConsistent` Einheitliche Aktualisierungen.  
  
- `dbSQLPassThrough` SQL Pass-Through. Bewirkt, dass die SQL-Anweisung für die Verarbeitung einer ODBC-Datenbank übergeben werden soll.  
  
- `dbFailOnError` Der Standardwert. Rollback für Updates, wenn ein Fehler auftritt und der Bericht den Fehler an den Benutzer.  
  
- `dbSeeChanges` Generieren Sie einen Laufzeitfehler, wenn ein anderer Benutzer die Daten geändert werden, die Sie bearbeiten.  
  
> [!NOTE]
>  Eine Erläuterung der Begriffe "inkonsistent" und "konsistent", finden Sie im Thema "Execute-Methode" in-DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 QueryDef-Objekte, die verwendet werden, für die Ausführung auf diese Weise können nur eine der folgenden Abfragetypen darstellen:  
  
-   Aktionsabfragen  
  
-   SQL-Pass-Through-Abfragen  
  
 `Execute` funktioniert nicht für Abfragen, die Datensätze, wie z. B. select-Abfragen zurückgeben. `Execute` Häufig wird für Abfragen der Bulk-Vorgang, wie z. B. **UPDATE**, **einfügen**, oder **SELECT INTO**, oder für Vorgänge Data Definition Language (DDL).  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Datenquellen Tabellen an einen Microsoft Jet angefügt ist (. MDB)-Datenbank. Weitere Informationen finden Sie im Thema "Den Zugriff auf externe Datenbanken mit DAO" in-DAO-Hilfe.  
  
 Rufen Sie die [GetRecordsAffected](#getrecordsaffected) Memberfunktion das Querydef-Objekt, um zu bestimmen, die Anzahl der Datensätze, die die letzte betroffen `Execute` aufrufen. Z. B. `GetRecordsAffected` gibt Informationen über die Anzahl der Datensätze gelöscht, aktualisiert oder eingefügt, wenn eine Abfrage ausführen. Die Anzahl die zurückgegebenen spiegeln sich nicht auf Änderungen in verknüpften Tabellen auf, wenn Cascade aktualisiert oder löscht wirksam sind.  
  
 Wenn Sie beide Nummern aufnehmen `dbInconsistent` und `dbConsistent` oder wenn Sie weder einschließen, wird das Ergebnis ist die Standardeinstellung `dbInconsistent`.  
  
 `Execute` ein Recordset wird nicht zurückgegeben werden. Mithilfe von `Execute` auf einer Abfrage, die Datensätze auswählt bewirkt, dass MFC eine Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="getconnect"></a>  CDaoQueryDef::GetConnect  
 Rufen Sie diese Memberfunktion zum Abrufen der Verbindungszeichenfolge des Querydef der Datenquelle zugeordnet.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) mit der Verbindungszeichenfolge für die Querydef.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nur mit ODBC-Datenquellen und bestimmte ISAM-Treiber verwendet. Er wird nicht mit der Microsoft Jet verwendet (. MDB)-Datenbanken; In diesem Fall `GetConnect` eine leere Zeichenfolge zurückgegeben. Weitere Informationen finden Sie unter [SetConnect](#setconnect).  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen, die sie zum Anfügen ist ein. MDB-Datenbank. Weitere Informationen finden Sie im Thema "Den Zugriff auf externe Datenbanken mit DAO" in-DAO-Hilfe.  
  
 Informationen zu Verbindungszeichenfolgen finden Sie im Thema "Verbinden der Eigenschaft" in-DAO-Hilfe.  
  
##  <a name="getdatecreated"></a>  CDaoQueryDef::GetDateCreated  
 Rufen Sie diese Memberfunktion, um das Datum zu erhalten, die das Querydef-Objekt erstellt wurde.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, enthält das Datum und die Uhrzeit die Querydef erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.  
  
##  <a name="getdatelastupdated"></a>  CDaoQueryDef::GetDateLastUpdated  
 Aufruf dieser Memberfunktion zum Abrufen des Querydef-Objekts durch des Datums der letzten Aktualisierung, wenn eine der Eigenschaften wurden geändert, wie z. B. seinen Namen, die SQL-Zeichenfolge oder die Verbindungszeichenfolge.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das das Datum und Uhrzeit der letzten die Querydef Aktualisierung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.  
  
##  <a name="getfieldcount"></a>  CDaoQueryDef::GetFieldCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Felder in der Abfrage.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder, die in der Abfrage definiert.  
  
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
 *nIndex*  
 Der nullbasierte Index des gewünschten Felds in die Querydef Fields-Sammlung, für die Suche nach Index.  
  
 *FieldInfo*  
 Ein Verweis auf eine `CDaoFieldInfo` -Objekt, das die angeforderten Informationen zurückgibt.  
  
 *dwInfoOptions*  
 Optionen, die angeben, welche Informationen über das Feld abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:  
  
- AFX_DAO_PRIMARY_INFO (Standard) Name, Typ, Größe und der Attribute  
  
- Primäre AFX_DAO_SECONDARY_INFO Informationen plus: Ordnungszahl ab, die erforderlich sind, der Länge NULL zulassen, Quellfeld, fremden Name, Quelltabelle, Reihenfolge sortieren  
  
- AFX_DAO_ALL_INFO primären und sekundären Informationen plus: Validierungsregel Standardwert Überprüfung Text  
  
 *Wert*  
 Eine Zeichenfolge, die mit dem Namen des gewünschten Felds, für die Suche anhand des Namens. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Informationen in zurückgegebenen *Fieldinfo*, finden Sie unter den [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur hat Member, die die beschreibende Informationen unter entsprechen *DwInfoOptions* oben. Wenn Sie eine Ebene Informationen anfordern, erhalten Sie alle vorherigen Ebenen sowie Informationen.  
  
##  <a name="getname"></a>  CDaoQueryDef::GetName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens der Abfrage durch die Querydef dargestellt wird.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Abfrage.  
  
### <a name="remarks"></a>Hinweise  
 QueryDef sind eindeutigen benutzerdefinierten Namen. Weitere Informationen zu Querydef Namen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.  
  
##  <a name="getodbctimeout"></a>  CDaoQueryDef::GetODBCTimeout  
 Rufen Sie diese Memberfunktion zum Abrufen des aktuellen Zeitlimits, vor dem Timeout einer Abfrage mit einer ODBC-Datenquelle.  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Sekunden, bevor eine Abfrage ist ein Timeout aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Informationen dazu, dieses Zeitlimit finden Sie im Thema "Timeoutfehlers warten soll Property" in-DAO-Hilfe.  
  
> [!TIP]
>  Anhängen an einen Microsoft Jet ist die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen (. MDB)-Datenbank. Weitere Informationen finden Sie im Thema "Den Zugriff auf externe Datenbanken mit DAO" in-DAO-Hilfe.  
  
##  <a name="getparametercount"></a>  CDaoQueryDef::GetParameterCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Parametern in der gespeicherten Abfrage.  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in der Abfrage definierten Parametern.  
  
### <a name="remarks"></a>Hinweise  
 `GetParameterCount` eignet sich für alle Parameter in der Querydef durchlaufen. Verwenden Sie zu diesem Zweck `GetParameterCount` in Verbindung mit [GetParameterInfo](#getparameterinfo).  
  
 Weitere Informationen finden Sie unter den Themen "Parameterobjekt", "Parameterauflistung" und "Parameter Deklaration (SQL)" in-DAO-Hilfe.  
  
##  <a name="getparameterinfo"></a>  CDaoQueryDef::GetParameterInfo  
 Rufen Sie diese Memberfunktion zum Abrufen von Informationen zu im Querydef definierten Parameters ein.  
  
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
 *nIndex*  
 Der nullbasierte Index des gewünschten Parameters in der Querydef Parameters-Auflistung, für die Suche nach Index.  
  
 *paraminfo*  
 Ein Verweis auf eine [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 *dwInfoOptions*  
 Optionen, die angeben, welche Informationen über den Parameter abgerufen werden. Die verfügbare Option ist hier aufgeführt, zusammen mit, was die Funktion zurückgegeben wird:  
  
- AFX_DAO_PRIMARY_INFO (Standard)-Namen, Typ  
  
 *Wert*  
 Eine Zeichenfolge, die mit dem Namen des gewünschten Parameters für die Suche anhand des Namens. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Informationen in zurückgegebenen *Paraminfo*, finden Sie unter den [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) Struktur. Diese Struktur hat Member, die die beschreibende Informationen unter entsprechen *DwInfoOptions* oben.  
  
 Verwandte Informationen finden Sie im Thema "Parameter Deklaration (SQL)" in-DAO-Hilfe.  
  
##  <a name="getparamvalue"></a>  CDaoQueryDef:: GetParamValue  
 Rufen Sie diese Memberfunktion zum Abrufen des aktuellen Werts des angegebenen Parameters in der Parameterauflistung des Querydef gespeichert.  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der Name des Parameters, dessen Wert Sie verwenden, für die Suche anhand des Namens möchten.  
  
 *nIndex*  
 Der nullbasierte Index des Parameters in der Querydef Parameters-Auflistung, für die Suche nach Index. Sie erhalten diesen Wert durch Aufrufe [GetParameterCount](#getparametercount) und [GetParameterInfo](#getparameterinfo).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt der Klasse [COleVariant](../../mfc/reference/colevariant-class.md) , die den Wert des Parameters enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Parameter nach Namen oder anhand ihrer Ordnungsposition in der Auflistung zugreifen.  
  
 Verwandte Informationen finden Sie im Thema "Parameter Deklaration (SQL)" in-DAO-Hilfe.  
  
##  <a name="getrecordsaffected"></a>  CDaoQueryDef::GetRecordsAffected  
 Rufen Sie diese Memberfunktion, um zu bestimmen, wie viele Datensätze betroffen sind, durch den letzten Aufruf von [Execute](#execute).  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der betroffenen Datensätze.  
  
### <a name="remarks"></a>Hinweise  
 Die Anzahl die zurückgegebenen spiegeln sich nicht auf Änderungen in verknüpften Tabellen auf, wenn Cascade aktualisiert oder löscht wirksam sind.  
  
 Weitere Informationen finden Sie im Thema "RecordsAffected-Eigenschaft" in-DAO-Hilfe.  
  
##  <a name="getreturnsrecords"></a>  CDaoQueryDef::GetReturnsRecords  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Querydef auf einer Abfrage basiert, die Datensätze zurückgibt.  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Querydef auf einer Abfrage basiert, die Datensätze zurückgibt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird nur für SQL Pass-Through-Abfragen verwendet. Weitere Informationen zu SQL-Abfragen finden Sie unter den [Execute](#execute) Member-Funktion. Weitere Informationen zum Arbeiten mit SQL Pass-Through-Abfragen finden Sie unter den [SetReturnsRecords](#setreturnsrecords) Member-Funktion.  
  
 Verwandte Informationen finden Sie im Thema "ReturnsRecords-Eigenschaft" in-DAO-Hilfe.  
  
##  <a name="getsql"></a>  CDaoQueryDef::GetSQL  
 Rufen Sie diese Memberfunktion, um die SQL-Anweisung abzurufen, die die Abfrage definiert, auf der die Querydef basiert.  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die SQL-Anweisung, die die Abfrage definiert, auf der die Querydef basiert.  
  
### <a name="remarks"></a>Hinweise  
 Sie werden dann wahrscheinlich die Zeichenfolge für Schlüsselwörter, Tabellen- und So weiter analysieren.  
  
 Weitere Informationen finden Sie unter den Themen "SQL-Eigenschaft", "Vergleich von Microsoft Jet-Datenbank-Engine-SQL und ANSI SQL" und "Abfragen einer Datenbank mit SQL in Code" in-DAO-Hilfe.  
  
##  <a name="gettype"></a>  CDaoQueryDef::GetType  
 Rufen Sie diese Memberfunktion, um die Abfrage die Querydef zu bestimmen.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ der Abfrage durch die Querydef definiert. Werte finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Der Abfragetyp wird festgelegt, durch was Sie in der Querydef des SQL-Zeichenfolge angeben, beim Erstellen der Querydef oder einer vorhandenen Querydef Aufrufen [SetSQL](#setsql) Member-Funktion. Der Abfragetyp, der von dieser Funktion zurückgegebenen kann es sich um eine der folgenden Werte sein:  
  
- `dbQSelect` Wählen Sie  
  
- `dbQAction`-Aktion  
  
- `dbQCrosstab` Kreuztabellenabfrage  
  
- `dbQDelete` Löschen  
  
- `dbQUpdate` Update  
  
- `dbQAppend` Anfügen  
  
- `dbQMakeTable` Tabelle erstellen  
  
- `dbQDDL` Datendefinition  
  
- `dbQSQLPassThrough` Pass-Through-  
  
- `dbQSetOperation` Union  
  
- `dbQSPTBulk` Mit verwendet `dbQSQLPassThrough` zum Angeben einer Abfrage, die keine Datensätze zurückgibt.  
  
> [!NOTE]
>  Um eine SQL-Pass-Through-Abfrage zu erstellen, legen Sie nicht die `dbSQLPassThrough` Konstanten. Dies wird automatisch von der Microsoft Jet-Datenbank-Engine festgelegt, wenn Sie ein Querydef-Objekt erstellt, und legen die Verbindungszeichenfolge fest.  
  
 Weitere Informationen zu SQL-Verbindungszeichenfolgen finden Sie unter [GetSQL](#getsql). Weitere Informationen zu Abfragetypen, finden Sie unter [Execute](#execute).  
  
##  <a name="isopen"></a>  CDaoQueryDef::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoQueryDef` Objekt ist momentan geöffnet.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoQueryDef` Objekt derzeit geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Querydef muss im geöffneten Zustand sein, bevor Sie ihn verwenden, rufen Sie [Execute](#execute) oder zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt. Ein Aufruf der Zustand "geöffnet" entweder eine Querydef abgelegt [erstellen](#create) (für eine neue Querydef) oder [öffnen](#open) (für eine vorhandene Querydef).  
  
##  <a name="m_pdatabase"></a>  CDaoQueryDef::m_pDatabase  
 Enthält einen Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt, das Querydef-Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Zeiger, wenn Sie direkt auf die Datenbank zugreifen müssen, z. B. zum Abrufen von Zeigern auf andere Querydef oder ein Recordset Objekte in der Datenbank-Sammlungen.  
  
##  <a name="m_pdaoquerydef"></a>  CDaoQueryDef::m_pDAOQueryDef  
 Enthält einen Zeiger auf die OLE-Schnittstelle für das zugrunde liegende DAO Querydef-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger wird auf Vollständigkeit und Konsistenz mit anderen Klassen bereitgestellt. Da MFC stattdessen vollständig DAO Querydefs kapselt, können Sie jedoch wahrscheinlich nicht benötigen. Wenn Sie es verwenden, holen Sie dies mit Vorsicht – insbesondere ändern den Wert des Zeigers nicht, wenn Sie wissen, was Sie tun.  
  
##  <a name="open"></a>  CDaoQueryDef::Open  
 Rufen Sie diese Memberfunktion zum Öffnen einer Querydef, die zuvor in der Datenbank QueryDefs-Auflistung gespeichert.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Eine Zeichenfolge mit dem Namen der gespeicherten Querydef zu öffnen. Sie können eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Querydef geöffnet ist, können Sie Aufrufen seiner [Execute](#execute) Memberfunktion oder verwenden Sie die Querydef zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt.  
  
##  <a name="setconnect"></a>  CDaoQueryDef::SetConnect  
 Rufen Sie diese Memberfunktion zum Festlegen der Verbindungszeichenfolge des Querydef-Objekts.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszConnect*  
 Eine Zeichenfolge, eine Verbindungszeichenfolge für das zugeordnete enthält [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Verbindungszeichenfolge wird zum Übergeben zusätzlicher Informationen auf ODBC und nach Bedarf bestimmte ISAM-Treiber verwendet. Er wird nicht für Microsoft Jet verwendet (. MDB)-Datenbanken.  
  
> [!TIP]
>  Die bevorzugte Methode zum Arbeiten mit ODBC-Tabellen, die sie zum Anfügen ist ein. MDB-Datenbank.  
  
 Legen Sie vor der Ausführung einer Querydef, die eine ODBC-Datenquelle eine SQL-Pass-Through-Abfrage darstellt, die Verbindungszeichenfolge mit `SetConnect` , und rufen Sie [SetReturnsRecords](#setreturnsrecords) angeben, ob die Abfrage gibt Datensätze zurück.  
  
 Weitere Informationen zur Struktur und Beispiele für die Verbindung die Komponenten der Verbindungszeichenfolge finden Sie im Thema "Verbinden der Eigenschaft" in-DAO-Hilfe.  
  
##  <a name="setname"></a>  CDaoQueryDef::SetName  
 Rufen Sie diese Memberfunktion auf, sollten Sie den Namen einer Querydef ändern, der nicht temporär ist.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Eine Zeichenfolge, der neue Name für eine temporäre Abfrage in der zugeordneten enthält [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 QueryDef sind eindeutige, den benutzerdefinierten Namen. Rufen Sie `SetName` vor Querydef Objekt der QueryDefs-Auflistung angefügt wird.  
  
##  <a name="setodbctimeout"></a>  CDaoQueryDef::SetODBCTimeout  
 Rufen Sie diese Memberfunktion, um das Zeitlimit festzulegen, bevor eine Abfrage mit einer ODBC-Datenquelle ein eintritt Timeout.  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>Parameter  
 *nODBCTimeout*  
 Die Anzahl der Sekunden, bevor eine Abfrage ist ein Timeout aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion können Sie die überschreiben Sie der Standardanzahl von Sekunden, bevor nachfolgende Vorgänge in der verbundenen Datenquelle "Timeout". Ein Vorgang kann aufgrund von Netzwerkproblemen für den Zugriff, übermäßige Abfrage Verarbeitungszeit und usw. Timeout. Rufen Sie `SetODBCTimeout` vor dem Ausführen einer Abfrage mit diesem Querydef, wenn Sie den Timeoutwert für Abfragen ändern möchten. (Wie ODBC Verbindungen wiederverwendet, ist der Timeoutwert für alle Clients auf die gleiche Verbindung.)  
  
 Der Standardwert für die Abfragetimeouts beträgt 60 Sekunden.  
  
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
 *Wert*  
 Der Name des Parameters, dessen Wert Sie festlegen möchten.  
  
 *varValue*  
 Der festzulegende Wert; finden Sie unter "Hinweise".  
  
 *nIndex*  
 Die Ordnungsposition des Parameters in der Querydef Parameters-Auflistung. Sie erhalten diesen Wert durch Aufrufe [GetParameterCount](#getparametercount) und [GetParameterInfo](#getparameterinfo).  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter muss bereits als Teil der SQL-Zeichenfolge des Querydef hergestellt haben. Sie können die Parameter nach Namen oder anhand ihrer Ordnungsposition in der Auflistung zugreifen.  
  
 Geben Sie den Wert für die festzulegende als eine `COleVariant` Objekt. Weitere Informationen zum Festlegen der gewünschten Wert und geben Sie Ihre `COleVariant` Objekt, finden Sie unter Klasse [COleVariant](../../mfc/reference/colevariant-class.md).  
  
##  <a name="setreturnsrecords"></a>  CDaoQueryDef::SetReturnsRecords  
 Rufen Sie diese Memberfunktion als Teil des Prozesses zum Einrichten einer SQL-Pass-Through-Abfrage an eine externe Datenbank.  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>Parameter  
 *bReturnsRecords*  
 Übergeben Sie "true", wenn die Abfrage auf einer externen Datenbank Datensätze zurückgibt; andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 In diesem Fall müssen Sie die Querydef erstellen und seine Eigenschaften mit anderen `CDaoQueryDef` Memberfunktionen. Eine Beschreibung der externe Datenbanken, finden Sie unter [SetConnect](#setconnect).  
  
##  <a name="setsql"></a>  CDaoQueryDef::SetSQL  
 Rufen Sie diese Memberfunktion zum Festlegen der SQL-Anweisung, die die Querydef ausgeführt wird.  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszSQL*  
 Eine Zeichenfolge mit der eine vollständige SQL-Anweisung, die für die Ausführung geeignet ist. Die Syntax dieser Zeichenfolge hängt vom DBMS, die Ihrer Abfrage angegeben. Eine Erläuterung der Syntax, die in der Microsoft Jet-Datenbank-Engine verwendet finden Sie im Thema "Erstellen von SQL-Anweisungen in Code" in-DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Ein typisches Einsatzgebiet von `SetSQL` ist das Einrichten einer Querydef-Objekt, für die Verwendung in einer SQL-Pass-Through-Abfrage. (Die Syntax der SQL-Pass-Through-Abfragen auf Ziel-DBMS, finden Sie in der Dokumentation für das DBMS).  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
