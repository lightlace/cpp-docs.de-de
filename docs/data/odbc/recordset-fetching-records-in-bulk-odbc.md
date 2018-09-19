---
title: 'Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bulk row fetching, implementing
- ODBC recordsets, bulk row fetching
- bulk record field exchange
- bulk row fetching
- bulk RFX functions
- recordsets, bulk row fetching
- DoBulkFieldExchange method
- fetching ODBC records in bulk
- RFX (ODBC), bulk
- rowsets, bulk row fetching
- RFX (ODBC), bulk row fetching
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0dce69b180a00ca44fdb2916136ac8107a4d94dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103920"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
Klasse `CRecordset` bietet Unterstützung für das gesammelte, was bedeutet, dass mehrere Datensätze auf einmal beim Abrufen von einem Datensatz, anstatt einen einzelnen Abruf zu einem Zeitpunkt aus der Datenquelle abgerufen werden können. Sie können das gesammelte Abrufen von Zeilen nur in einer abgeleiteten implementieren `CRecordset` Klasse. Der Prozess der Übertragung von Daten aus der Datenquelle an das Recordset-Objekt wird Massen-Datensatzfeldaustausch (Bulk-RFX) aufgerufen. Beachten Sie, dass Sie nicht verwenden massenzeilenabruf in einem `CRecordset`-abgeleiteten Klasse, die Daten werden per Datensatzfeldaustausch (RFX) übertragen. Weitere Informationen finden Sie unter [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
In diesem Thema wird Folgendes erläutert:  
  
- [Wie CRecordset unterstützt gesammelte](#_core_how_crecordset_supports_bulk_row_fetching).  
  
- [Einige besondere Überlegungen zur Verwendung der Zeilenabruf](#_core_special_considerations).  
  
- [Gewusst wie: Implementieren der massenaustausch](#_core_how_to_implement_bulk_record_field_exchange).  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> Wie unterstützt CRecordset gesammelte  

Vor dem Öffnen des Recordset-Objekts an, Sie können die Größe eines Rowsets mit definieren die `SetRowsetSize` Member-Funktion. Die Größe des Rowsets gibt an, wie viele Datensätze, die während einer einzigen Abfrage abgerufen werden soll. Wenn massenzeilenabruf implementiert ist, ist die Standardgröße des Rowsets 25. Wenn gesammelte nicht implementiert wird, bleibt die Rowsetgröße 1 behoben.  
  
Nachdem Sie die Größe des Rowsets initialisiert haben, rufen Sie die [öffnen](../../mfc/reference/crecordset-class.md#open) Member-Funktion. Hier müssen Sie die `CRecordset::useMultiRowFetch` Möglichkeit, die *DwOptions* Parameter massenzeilenabruf implementiert. Sie können außerdem festlegen, die `CRecordset::userAllocMultiRowBuffers` Option. Der Mechanismus Bulk Record Field Exchange verwendet Arrays zum Speichern der mehrere Zeilen von Daten, die bei einem Abrufvorgang abgerufen. Diese Speicherpuffer vom Framework automatisch zugeordnet werden können, oder Sie können diese manuell zuordnen. Angeben der `CRecordset::userAllocMultiRowBuffers` Option bedeutet, dass Sie die Zuordnung werden.  
  
Die folgende Tabelle enthält die Member-Funktionen, die von bereitgestellte `CRecordset` gesammelte unterstützen.  
  
|Member-Funktion|Beschreibung|  
|---------------------|-----------------|  
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|Virtuelle Funktion, die alle Fehler, die während des Abrufens auftreten behandelt.|  
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Implementiert den Sammel-Datensatzfeldaustausch. Automatisch aufgerufen, um Übertragungen mehrere Zeilen mit Daten aus der Datenquelle des Recordset-Objekts.|  
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Ruft die aktuelle Einstellung für die Größe des Rowsets ab.|  
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|Gibt an, wie viele Zeilen tatsächlich einem Abrufvorgang abgerufen wurden. In den meisten Fällen ist dies die Größe des Rowsets, es sei denn, ein unvollständiges Rowset abgerufen wurde.|  
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|Gibt einen Fetch-Status für eine bestimmte Zeile in ein Rowset zurück.|  
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Aktualisiert die Daten und den Status einer bestimmten Zeile in einem Rowset.|  
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|Verschiebt den Cursor zu einer bestimmten Zeile in einem Rowset.|  
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Virtuelle Funktion, die die Einstellung für die Rowsetgröße mit dem angegebenen Wert zu ändern.|  
  
##  <a name="_core_special_considerations"></a> Besondere Überlegungen  

Obwohl gesammelte einen Leistungsgewinn ist, gehen bestimmte Funktionen anders vor. Bevor Sie die gesammelte implementieren möchten, beachten Sie Folgendes:  
  
- Ruft das Framework automatisch die `DoBulkFieldExchange` Member-Funktion zum Übertragen von Daten aus der Datenquelle auf das Recordsetobjekt. Allerdings werden Daten nicht aus dem Recordset zurück an die Datenquelle übertragen. Aufrufen der `AddNew`, `Edit`, `Delete`, oder `Update` Ergebnissen der Member-Funktionen in eine fehlgeschlagene Assertion. Obwohl `CRecordset` derzeit keinen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, indem Sie mithilfe der ODBC-API-Funktion `SQLSetPos`. Weitere Informationen zu `SQLSetPos`, finden Sie unter den *ODBC SDK-Programmierreferenz* in der MSDN-Dokumentation.  
  
- Die Memberfunktionen `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty`, und `SetFieldNull` kann nicht in Recordsets, die gesammelte implementieren verwendet werden. Sie können jedoch aufrufen `GetRowStatus` anstelle von `IsDeleted`, und `GetODBCFieldInfo` anstelle von `IsFieldNullable`.  
  
- Die `Move` -Operationen Recordset nach Rowsets. Nehmen wir beispielsweise an, dass Sie ein Recordset mit öffnen 100 Datensätze mit einem anfänglichen Rowsetgröße von 10. `Open` Ruft die Zeilen 1 bis 10 mit den aktuellen Datensatz in Zeile 1 ist. Ein Aufruf von `MoveNext` des nächsten Rowsets, nicht die nächste Zeile abgerufen. Dieses Rowset besteht aus Zeilen 11 bis 20, mit dem aktuellen Datensatz in Zeile 11 positioniert. Beachten Sie, dass `MoveNext` und `Move( 1 )` einander nicht entsprechen, wenn die massenzeilenabruf implementiert ist. `Move( 1 )` Ruft das Rowset, das 1 Zeile aus dem aktuellen Datensatz beginnt ab. In diesem Beispiel Aufrufen `Move( 1 )` nach dem Aufruf `Open` abruft, das Rowset aus den Zeilen 2 bis 11, mit dem aktuellen Datensatz positioniert für Zeile 2 besteht. Weitere Informationen finden Sie unter den [verschieben](../../mfc/reference/crecordset-class.md#move) Member-Funktion.  
  
- Im Gegensatz zu Datensatzfeldaustausch unterstützen die Assistenten keine massenaustausch. Dies bedeutet, dass müssen Sie manuell die Felddatenmember deklarieren und manuell überschreiben `DoBulkFieldExchange` durch Aufrufe der Bulk-RFX-Funktionen zu schreiben. Weitere Informationen finden Sie unter [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md) in die *Klassenbibliotheksreferenz*.  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> Gewusst wie: Implementieren der Massen-Datensatzfeldaustausch  

Massenaustausch überträgt ein Rowset von Daten aus der Datenquelle, auf das Recordset-Objekt. Die Bulk-RFX-Funktionen verwenden Sie Arrays zum Speichern dieser Daten als auch Arrays, die die Länge der einzelnen Datenelemente in das Rowset zu speichern. In der Klassendefinition müssen Sie Ihre Felddatenmember als Zeiger auf die Arrays von Daten definieren. Darüber hinaus müssen Sie einen Satz von Zeigern auf Arrays mit Längen definieren. Parameterdatenmember sollten nicht als Zeiger deklariert werden. Parameterdatenmember deklarieren, bei Verwendung der massenaustausch ist identisch mit der sie bei Verwendung von Datensatzfeldaustausch deklarieren. Der folgende Code zeigt ein einfaches Beispiel:  
  
```cpp  
class MultiRowSet : public CRecordset  
{  
public:  
   // Field/Param Data  
      // field data members  
      long* m_rgID;  
      LPSTR m_rgName;  
  
      // pointers for the lengths  
      // of the field data  
      long* m_rgIDLengths;  
      long* m_rgNameLengths;  
  
      // input parameter data member  
      CString m_strNameParam;  
  
   .  
   .  
   .  
}  
```  
  
Sie können diese Speicherpuffer manuell zuordnen oder das Framework erledigen müssen. Um die Puffer selbst zuordnen, müssen Sie angeben der `CRecordset::userAllocMultiRowBuffers` Möglichkeit, die *DwOptions* Parameter in der `Open` Member-Funktion. Achten Sie darauf, dass Sie die Größe der Arrays entspricht mindestens die Größe des Rowsets fest. Wenn Sie das Framework die Zuordnung vornehmen möchten, sollten Sie die Zeiger auf NULL initialisieren. Dies erfolgt normalerweise im Konstruktor des Recordset-Objekts:  
  
```cpp  
MultiRowSet::MultiRowSet( CDatabase* pDB )  
   : CRecordset( pDB )  
{  
   m_rgID = NULL;  
   m_rgName = NULL;  
   m_rgIDLengths = NULL;  
   m_rgNameLengths = NULL;  
   m_strNameParam = "";  
  
   m_nFields = 2;  
   m_nParams = 1;  
  
   .  
   .  
   .  
}  
```  
  
Abschließend müssen Sie überschreiben die `DoBulkFieldExchange` Member-Funktion. Rufen Sie die Bulk-RFX-Funktionen, für den Felddatenmembern; Rufen Sie für alle Datenmember der Parameter der RFX-Funktionen. Wenn Sie das Recordset geöffnet haben, übergeben Sie eine SQL-Anweisung oder gespeicherte Prozedur, `Open`, muss die Reihenfolge, in dem Sie die Bulk-RFX-Aufrufe vornehmen, Reihenfolge der Spalten im Recordset entsprechen; die Reihenfolge der RFX-Analog dazu verlangt wird, für die Parameter entsprechen müssen Reihenfolge der Parameter in der SQL-Anweisung oder gespeicherten Prozedur.  
  
```cpp  
void MultiRowSet::DoBulkFieldExchange( CFieldExchange* pFX )  
{  
   // call the Bulk RFX functions  
   // for field data members  
   pFX->SetFieldType( CFieldExchange::outputColumn );  
   RFX_Long_Bulk( pFX, _T( "[colRecID]" ),  
                  &m_rgID, &m_rgIDLengths );  
   RFX_Text_Bulk( pFX, _T( "[colName]" ),  
                  &m_rgName, &m_rgNameLengths, 30 );  
  
   // call the RFX functions for  
   // for parameter data members  
   pFX->SetFieldType( CFieldExchange::inputParam );  
   RFX_Text( pFX, "NameParam", m_strNameParam );  
}  
```  
  
> [!NOTE]
>  Rufen Sie die `Close` Memberfunktion, bevor Sie Ihre abgeleiteten `CRecordset` Klasse den Gültigkeitsbereich verlässt. Dadurch wird sichergestellt, dass durch das Framework zugewiesener Speicher freigegeben werden. Es empfiehlt sich immer explizit aufrufen, `Close`, unabhängig davon, ob massenzeilenabruf implementiert haben.  
  
Weitere Informationen zu den Datensatzfeldaustausch (RFX), finden Sie unter [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Weitere Informationen zur Verwendung von Parametern finden Sie unter [CFieldExchange::](../../mfc/reference/cfieldexchange-class.md#setfieldtype) und [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)

