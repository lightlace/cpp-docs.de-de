---
title: CDBException Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CDBException class
- exceptions [C++], database
- database exceptions [C++]
- ODBC classes [C++], exceptions
- errors [C++], database
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fc3bf7be273bf509dd1ee79fb42e69050070e830
ms.lasthandoff: 02/24/2017

---
# <a name="cdbexception-class"></a>CDBException-Klasse
Stellt eine Ausnahmebedingung dar, die von Datenbankklassen ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|Enthält einen Rückgabecode vom Typ Open Database Connectivity (ODBC) **RETCODE**.|  
|[CDBException::m_strError](#m_strerror)|Enthält eine Zeichenfolge, die alphanumerische bezüglich der Fehler beschrieben wird.|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|Enthält eine Beschreibung des Fehlers im Hinblick auf die Fehlercodes, die von ODBC zurückgegebene Zeichenfolge.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse enthält zwei öffentliche Datenmember, die Sie verwenden können, um die Ursache der Ausnahme zu ermitteln oder eine Textnachricht, die Beschreibung der Ausnahme anzuzeigen. `CDBException`Objekte werden erstellt und von Memberfunktionen von Datenbankklassen ausgelöst.  
  
> [!NOTE]
>  Diese Klasse ist einer der Klassen von MFC Open Database Connectivity (ODBC). Wenn Sie stattdessen die neueren Datenzugriffsobjekte (DAO)-Klassen verwenden, verwenden Sie [CDaoException](../../mfc/reference/cdaoexception-class.md) stattdessen. Alle DAO-Klassennamen ist "CDao" als Präfix. Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Ausnahmen wurden nicht normale Ausführung im Zusammenhang mit Bedingungen außerhalb der Steuerung des Programms, z. B. Datenquelle oder Netzwerk-e/a-Fehler. Fehler, die Sie möglicherweise erwarten, während der normalen Ausführung Ihrer Anwendung finden Sie unter Ausnahmen in der Regel nicht berücksichtigt.  
  
 Sie können diese Objekte innerhalb des Bereichs zugreifen ein **CATCH** Ausdruck. Sie können auch Auslösen `CDBException` Objekte aus Ihrem eigenen Code mit der `AfxThrowDBException` globale Funktion.  
  
 Weitere Informationen zur Behandlung von Ausnahmen in allgemeinen oder etwa `CDBException` von Objekten finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="m_nretcode"></a>CDBException::m_nRetCode  
 ODBC-Fehler vom Typ enthält **RETCODE** von einer ODBC-Anwendung programming Interface (API)-Funktion zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Typ enthält, mit dem Präfix SQL-Codes, die von ODBC definiert und mit dem Präfix AFX_SQL Fehlercodes, die von den Datenbankklassen. Für eine `CDBException`, dieses Element enthält die folgenden Werte:  
  
- **AFX_SQL_ERROR_API_CONFORMANCE** der Treiber für ein `CDatabase::OpenEx` oder `CDatabase::Open` Aufruf entspricht nicht dem erforderlichen ODBC API Konformitätsgrad 1 ( **SQL_OAC_LEVEL1**).  
  
- **AFX_SQL_ERROR_CONNECT_FAIL** Fehler bei der Verbindung mit der Datenquelle. Sie übergeben ein **NULL** `CDatabase` Zeiger auf den recordsetkonstruktor und dem anschließenden Versuch, eine Verbindung zu erstellen, basierend auf `GetDefaultConnect` ist fehlgeschlagen.  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED** angeforderte mehr Daten, als Sie Speicher für bereitgestellt haben. Informationen zum Erhöhen des bereitgestellten Datenspeicher für `CString` oder `CByteArray` Datentypen finden Sie in der `nMaxLength` Argument für [RFX_Text](http://msdn.microsoft.com/library/de3c7581-d26c-40cb-81f3-c492ef4809f6) und [RFX_Binary](http://msdn.microsoft.com/library/908ff945-3ad0-43a1-9932-cdcdc8b14915) unter "Makros und Globals."  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED ausgelöst** einen Aufruf von `CRecordset::Open` anfordern ein Dynaset ist fehlgeschlagen. Dynasets werden vom Treiber nicht unterstützt.  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST** Sie haben versucht, eine Tabelle zu öffnen (oder was eingegebene konnte nicht als Prozeduraufruf identifiziert oder **auswählen** Anweisung), aber es keine Spalten identifizierten Datensatz Feld Datensatzfeldaustausch (RFX) Funktionsaufrufen in sind Ihre `DoFieldExchange` außer Kraft setzen.  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH** den Typ einer RFX-Funktion in Ihrer `DoFieldExchange` Außerkraftsetzung ist nicht kompatibel mit dem Datentyp der Spalte im Recordset.  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE** aufgerufen `CRecordset::Update` ohne zuvor `CRecordset::AddNew` oder `CRecordset::Edit`.  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** Ihre Anfrage zum Sperren von Datensätzen für das Update konnte nicht ausgeführt werden, da Sperren der ODBC-Treiber nicht unterstützt wird.  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** aufgerufen `CRecordset::Update` oder **löschen** für eine Tabelle ohne eindeutigen Schlüssel und mehreren Datensätzen geändert.  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD** Sie haben versucht, eine zuvor gelöschte Datensätze bearbeiten bzw. löschen. Sie müssen zu einem neuen aktuellen Datensatz nach einem Löschvorgang blättern.  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES** Ihre Anforderung für ein Dynaset konnte nicht ausgeführt werden, weil der ODBC-Treiber nicht unterstützt positionierte Updates.  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED** aufgerufen `CRecordset::Update` oder **löschen**, Beginn des Vorgangs der Datensatz konnte jedoch nicht mehr gefunden werden.  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** Versuch zum Laden der ODBC. Fehler bei der DLL; Windows konnte nicht gefunden werden oder diese DLL nicht laden konnte. Dieser Fehler ist schwerwiegend.  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED** für ein Dynaset Ihre Anforderung konnte nicht ausgeführt werden, da ein Level 2-kompatiblen ODBC-Treiber erforderlich ist.  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY** Versuch, einen Bildlauf war nicht erfolgreich, da die Datenquelle Bildlauf rückwärts nicht unterstützt.  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED** einen Aufruf von `CRecordset::Open` Fehler beim Anfordern einer momentaufnahmes. Momentaufnahmen werden vom Treiber nicht unterstützt. (Dies sollte nur auftreten, wenn die ODBC-Cursorbibliothek Â €"ODBCCURS. DLL Â €"ist nicht vorhanden.)  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE** der Treiber für ein `CDatabase::OpenEx` oder `CDatabase::Open` Aufruf entspricht nicht dem erforderlichen ODBC SQL-Konformitätsgrad des "Minimum" ( **SQL_OSC_MINIMUM**).  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** der ODBC-Treiber konnte nicht an die Gesamtgröße des einem `CLongBinary` Datenwert. Der Fehler bei Vorgang wahrscheinlich ein globalen Arbeitsspeicher-Block nicht vorab werden konnte.  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY** Sie haben versucht, ein schreibgeschütztes Recordset zu aktualisieren oder die Datenquelle ist schreibgeschützt. Keine Update-Operationen können mit dem Recordset ausgeführt werden oder die `CDatabase` Objekt es zugeordnet ist.  
  
- **SQL_ERROR** Funktion fehlgeschlagen. Die Fehlermeldung, die von der ODBC-Funktion zurückgegebene **SQLError** befindet sich in der **M_strError** -Datenmember.  
  
- **SQL_INVALID_HANDLE** Funktion aufgrund einer ungültigen Umgebungshandle Verbindungshandle oder Anweisungshandle fehlgeschlagen ist. Hiermit wird einen Programmierfehler. Keine zusätzlichen Informationen aus der ODBC-Funktion steht **SQLError**.  
  
 Die mit dem Präfix SQL-Codes werden von ODBC definiert. Die Codes AFX Präfix sind in AFXDB definiert. H in MFC\INCLUDE gefunden.  
  
##  <a name="m_strerror"></a>CDBException::m_strError  
 Enthält eine Zeichenfolge, die Beschreibung des Fehlers, der die Ausnahme verursacht hat.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge beschreibt den Fehler alphanumerische ausgedrückt. Weitere Informationen und ein Beispiel finden Sie unter **M_strStateNativeOrigin**.  
  
##  <a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin  
 Enthält eine Zeichenfolge, die Beschreibung des Fehlers, der die Ausnahme verursacht hat.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge hat das Format "Status: % s, einheitlichen: % ld, Ursprung: % s", bei der Formatcodes, die in der Reihenfolge, durch die Werte ersetzt werden, in denen beschrieben:  
  
-   Die **SQLSTATE**, eine Null-terminierte Zeichenfolge mit einer fünfstelligen zurückgegebenen Fehlercode in der *SzSqlState* -Parameter der ODBC-Funktion **SQLError**. **SQLSTATE** Werte sind in Anhang A aufgeführt [ODBC-Fehlercodes](https://msdn.microsoft.com/library/ms714687.aspx)in der *ODBC Programmer's Reference*. Beispiel: "S0022".  
  
-   Der systemeigene Fehlercode für die Datenquelle zurückgegeben wird, der *PfNativeError* Parameter von der **SQLError** Funktion. Beispiel: 207.  
  
-   Der Text der Fehlermeldung zurückgegeben, die der *von SQLDiagRec()* Parameter von der **SQLError** Funktion. Diese Nachricht besteht aus mehreren in Klammern gesetzten Namen. Wie ein Fehler von der Quelle an den Benutzer übergeben wird, fügt jeder ODBC-Komponente (Data Source, Treiber, Treiber-Manager) den eigenen Namen. Diese Informationen helfen, um den Ursprung des Fehlers zu ermitteln. Beispiel: [Microsoft] [ODBC SQL Server Driver] [SQLServer]  
  
 Das Framework die Fehlerzeichenfolge interpretiert und setzt seine Komponenten in **M_strStateNativeOrigin**Wenn **M_strStateNativeOrigin** enthält Informationen für mehr als einen Fehler, die Fehler durch Zeilenumbrüche getrennte sind. Das Framework setzt den alphanumerischen Fehlertext in **M_strError**.  
  
 Weitere Informationen zu den Codes verwendet, um diese Zeichenfolge zu erstellen, finden Sie unter der [SQLError](https://msdn.microsoft.com/library/ms716312.aspx) -Funktion in der *ODBC Programmer's Reference*.  
  
### <a name="example"></a>Beispiel  
  Von ODBC: "State: S0022, einheitlichen:&207;, Ursprung: [Microsoft] [ODBC SQL Server Driver] [SQLServer] Ungültiger Spaltenname 'ColName'"  
  
 In **M_strStateNativeOrigin**: "State: S0022, einheitlichen:&207;, Ursprung: [Microsoft] [ODBC SQL Server Driver] [SQLServer]"  
  
 In **M_strError**: "Ungültiger Spaltenname 'ColName'"  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)   
 [CDBException-Klasse](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset:: Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)

