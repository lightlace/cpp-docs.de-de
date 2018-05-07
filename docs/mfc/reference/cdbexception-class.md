---
title: CDBException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
dev_langs:
- C++
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 824ac88326042eb55ecb9667c39331d1ab5464e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdbexception-class"></a>CDBException-Klasse
Stellt eine Ausnahmebedingung dar, die von Datenbankklassen ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|Enthält einen Rückgabecode des Typs Open Database Connectivity (ODBC) **RETCODE**.|  
|[CDBException::m_strError](#m_strerror)|Enthält eine Zeichenfolge, die Beschreibung des Fehlers alphanumerische ausgedrückt.|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|Enthält eine Zeichenfolge, die Beschreibung des Fehlers im Hinblick auf die Fehlercodes, die von ODBC zurückgegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse enthält zwei öffentliche Datenmember, die Ursache der Ausnahme zu ermitteln oder eine Textnachricht Beschreibung der Ausnahme anzeigen verwendet werden können. `CDBException` Objekte werden erstellt und von Memberfunktionen von Datenbankklassen ausgelöst.  
  
> [!NOTE]
>  Diese Klasse ist eine der Klassen von MFC Open Database Connectivity (ODBC). Wenn Sie stattdessen die neueren Datenzugriffsobjekte (DAO) Klassen verwenden, verwenden Sie [CDaoException](../../mfc/reference/cdaoexception-class.md) stattdessen. Alle DAO-Klassennamen haben "CDao" als Präfix an. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Ausnahmen sind Fälle nicht ordnungsgemäße Ausführung, die im Zusammenhang mit Bedingungen außerhalb der Steuerung des Programms, z. B. Datenquelle oder Netzwerk-e/a-Fehler. Fehler, die zu erwarten, des normalen Betriebs der Ausführung des Programms angezeigt werden Ausnahmen in der Regel nicht berücksichtigt.  
  
 Sie können diese Objekte innerhalb des Bereichs der zugreifen eine **CATCH** Ausdruck. Sie können auch Auslösen `CDBException` Objekte aus Ihrem eigenen Code mit der `AfxThrowDBException` globale Funktion.  
  
 Weitere Informationen zur Ausnahmebehandlung im allgemeinen oder über `CDBException` Objekte finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="m_nretcode"></a>  CDBException::m_nRetCode  
 Enthält einen ODBC-Fehlercode des Typs **RETCODE** von einer ODBC-Anwendung Programmierung (Interface, API)-Funktion zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Typen fallen breitzeichenliteral mit dem SQL-Codes, die von ODBC definiert und mit dem Präfix AFX_SQL Codes, die von den Datenbankklassen definiert. Für eine `CDBException`, dieses Element enthält die folgenden Werte:  
  
- **AFX_SQL_ERROR_API_CONFORMANCE** der Treiber für eine `CDatabase::OpenEx` oder `CDatabase::Open` Aufruf entspricht nicht dem erforderlichen ODBC-API Konformitätsgrad 1 ( **SQL_OAC_LEVEL1**).  
  
- **AFX_SQL_ERROR_CONNECT_FAIL** Fehler bei Verbindung mit der Datenquelle. Sie übergeben ein **NULL** `CDatabase` Zeiger auf das Recordset-Konstruktor und dem anschließenden Versuch, eine Verbindung zu erstellen, die auf Basis `GetDefaultConnect` ist fehlgeschlagen.  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED** angeforderte mehr Daten, als Sie Speicher für eingegeben haben. Informationen zum Erhöhen des bereitgestellten Datenspeicher für `CString` oder `CByteArray` Datentypen finden Sie in der `nMaxLength` Argument für [RFX_Text](record-field-exchange-functions.md#rfx_text) und [RFX_Binary](record-field-exchange-functions.md#rfx_binary) unter "Makros und Globals."  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED ausgelöst** einen Aufruf von `CRecordset::Open` Fehler bei einem Dynaset anfordern. Dynasets werden vom Treiber nicht unterstützt.  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST** Sie haben versucht, eine Tabelle zu öffnen (oder Sie gegeben haben nicht gefunden, als Aufruf einer Prozedur oder **wählen** Anweisung), aber es keine Spalten-identifiziert Datensatzfeldaustausch (RFX sind) -Funktionsaufrufe in Ihre `DoFieldExchange` außer Kraft setzen.  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH** den Typ einer RFX-Funktion in Ihrer `DoFieldExchange` Außerkraftsetzung ist nicht kompatibel mit dem Datentyp der Spalte im Recordset.  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE** aufgerufen `CRecordset::Update` ohne Aufruf von zuvor `CRecordset::AddNew` oder `CRecordset::Edit`.  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** Ihre Anforderung zum Sperren von Datensätzen für das Update konnte nicht erfüllt werden, da Sperren der ODBC-Treiber nicht unterstützt wird.  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** aufgerufen `CRecordset::Update` oder **löschen** für eine Tabelle ohne eindeutigen Schlüssel und mehreren Datensätzen geändert.  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD** Sie haben versucht, bearbeiten oder Löschen einen zuvor gelöschten Datensatz. Sie müssen nach einem Löschvorgang zu einem neuen aktuellen Datensatz blättern.  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES** Ihre Anforderung für ein Dynaset nicht erfüllt werden konnte, da der ODBC-Treiber nicht unterstützt positionierte Updates.  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED** aufgerufen `CRecordset::Update` oder **löschen**, wenn der Vorgang begonnen hat der Datensatz konnte jedoch nicht mehr gefunden werden.  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** Versuch zum Laden der ODBC. Fehler bei der DLL; Windows konnte nicht gefunden werden, oder diese DLL konnte nicht geladen werden. Dieser Fehler ist schwerwiegend.  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED** Ihre Anforderung für ein Dynaset konnte nicht erfüllt werden, da ein Level 2-kompatibler ODBC-Treiber erforderlich ist.  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY** Versuch, einen Bildlauf war nicht erfolgreich, da die Datenquelle Bildlauf rückwärts nicht unterstützt.  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED** einen Aufruf von `CRecordset::Open` Anfordern einer Momentaufnahme ist fehlgeschlagen. Momentaufnahmen werden vom Treiber nicht unterstützt. (Dies sollte nur auftreten, wenn die ODBC-Cursorbibliothek ODBCCURS. DLL ist nicht vorhanden.)  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE** der Treiber für eine `CDatabase::OpenEx` oder `CDatabase::Open` Aufruf entspricht nicht dem erforderlichen ODBC SQL-Konformitätsgrad des "Minimum" ( **SQL_OSC_MINIMUM**).  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** der ODBC-Treiber konnte nicht an die Gesamtgröße des einem `CLongBinary` Datenwert. Vorgangsfehler wahrscheinlich ein globalen Speicherblock nicht vorab werden konnte.  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY** Sie versucht, ein schreibgeschütztes Recordset zu aktualisieren, oder die Datenquelle ist schreibgeschützt. Das Recordset können keine Updatevorgänge ausgeführt werden oder die `CDatabase` Objekt es zugeordnet ist.  
  
- **SQL_ERROR** Funktion fehlgeschlagen. Die Fehlermeldung, die von der ODBC-Funktion zurückgegebenen **SQLError** befindet sich in der **M_strError** -Datenmember.  
  
- **SQL_INVALID_HANDLE** Fehler bei der Funktion aufgrund einer ungültigen Umgebungshandle, Verbindungshandle oder Anweisungshandle. Hiermit wird einen Programmierfehler. Keine zusätzlichen Informationen aus der ODBC-Funktion steht **SQLError**.  
  
 Die breitzeichenliteral mit dem SQL-Codes werden vom ODBC definiert. Die Codes AFX mit dem Präfix sind in AFXDB definiert. H in MFC\INCLUDE gefunden.  
  
##  <a name="m_strerror"></a>  CDBException::m_strError  
 Enthält eine Zeichenfolge, die Beschreibung des Fehlers, der die Ausnahme verursacht hat.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge den Fehler beschreibt, alphanumerische ausgedrückt wird. Weitere Informationen und ein Beispiel finden Sie unter **M_strStateNativeOrigin**.  
  
##  <a name="m_strstatenativeorigin"></a>  CDBException::m_strStateNativeOrigin  
 Enthält eine Zeichenfolge, die Beschreibung des Fehlers, der die Ausnahme verursacht hat.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge weist das Format "Status: % s, systemeigene: %ld Ursprung: % s", auf, wobei die Formatcodes in der Reihenfolge, durch die Werte ersetzt werden, in denen beschrieben:  
  
-   Die **SQLSTATE**, eine Null-terminierte Zeichenfolge aus einen fünf Zeichen zurückgegebenen Fehlercode in der *SzSqlState* -Parameter der ODBC-Funktion **SQLError**. **SQLSTATE** Werte werden in Anhang A, aufgeführt [ODBC-Fehlercodes](https://msdn.microsoft.com/library/ms714687.aspx)in der *ODBC Programmer's Reference*. Beispiel: "S0022".  
  
-   Der systemeigene Fehlercode für die Datenquelle spezifischen zurückgegeben, der *PfNativeError* Parameter von der **SQLError** Funktion. Beispiel: 207.  
  
-   Der Text der Fehlermeldung zurückgegeben, die der *von SQLDiagRec()* Parameter von der **SQLError** Funktion. Diese Nachricht besteht aus mehreren in Klammern gesetzten Namen. Wie ein Fehler von der Quelle an den Benutzer übergeben wird, fügt jede ODBC-Komponente (Datenquelle, Treiber, Treiber-Manager) einen eigenen Namen an. Diese Informationen helfen, um den Ursprung des Fehlers zu ermitteln. Beispiel: [Microsoft] [ODBC SQL Server Driver] [SQLServer]  
  
 Das Framework interpretiert die Fehlerzeichenfolge und setzt seine Komponenten in **M_strStateNativeOrigin**; Wenn **M_strStateNativeOrigin** enthält Informationen für mehrere Fehler sind die Fehler durch getrennt Zeilenumbrüche. Das Framework setzt den alphanumerischen Fehlertext in **M_strError**.  
  
 Weitere Informationen zu dieser Zeichenfolge bilden verwendeten Codes finden Sie unter der [SQLError](https://msdn.microsoft.com/library/ms716312.aspx) -Funktion in der *ODBC Programmer's Reference*.  
  
### <a name="example"></a>Beispiel  
  Von ODBC: "State: S0022, systemeigene: 207, Ursprung: [Microsoft] [ODBC SQL Server Driver] [SQLServer] Ungültiger Spaltenname"ColName""  
  
 In **M_strStateNativeOrigin**: "State: S0022, systemeigene: 207, Ursprung: [Microsoft] [ODBC SQL Server Driver] [SQLServer]"  
  
 In **M_strError**: "Ungültiger Spaltenname"ColName""  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)   
 [CDBException-Klasse](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset:: Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)
