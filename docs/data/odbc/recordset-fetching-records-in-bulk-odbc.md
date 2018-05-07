---
title: 'Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC) | Microsoft Docs'
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
ms.openlocfilehash: 8ef8803459edeba98e472a0e7fd07e7f5daf2c4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Klasse `CRecordset` bietet Unterstützung für gesammelte, was bedeutet, dass mehrere Datensätze gleichzeitig beim Abrufen von einem Datensatz, anstatt eine einzelne Fetch zu einem Zeitpunkt aus der Datenquelle abgerufen werden können. Sie können das gesammelte Abrufen von Zeilen nur in einer abgeleiteten implementieren `CRecordset` Klasse. Der Vorgang der Übertragung von Daten aus der Datenquelle an das Recordset-Objekt wird Massen-Datensatzfeldaustausch (Bulk-RFX) genannt. Beachten Sie, dass, wenn Sie nicht massenzeilenabruf arbeiten in einem `CRecordset`-abgeleitete Klasse, die Daten werden per Datensatzfeldaustausch (RFX) übertragen. Weitere Informationen finden Sie unter [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Wie CRecordset unterstützt gesammelte](#_core_how_crecordset_supports_bulk_row_fetching).  
  
-   [Einige besondere Aspekte bei der Verwendung der Zeilenabruf](#_core_special_considerations).  
  
-   [Gewusst wie: Implementieren der Massen-Datensatzfeldaustausch](#_core_how_to_implement_bulk_record_field_exchange).  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> Wie CRecordset das gesammelte Abrufen von Zeilen unterstützt  
 Sie können vor dem Öffnen des Recordsetobjekts mit eine Rowsetgröße definieren die `SetRowsetSize` Memberfunktion. Die Größe des Rowsets gibt an, wie viele Datensätze während einer einzigen Abfrage abgerufen werden soll. Wenn gesammelte implementiert ist, ist die Standardgröße des Rowsets 25. Wenn Abrufens von Zeilen nicht implementiert wird, bleibt die Rowsetgröße auf 1 fest.  
  
 Nachdem Sie die Größe des Rowsets initialisiert haben, rufen die [öffnen](../../mfc/reference/crecordset-class.md#open) Memberfunktion. Hier müssen Sie die `CRecordset::useMultiRowFetch` -Option von der **OpenEx** Parameter gesammelte implementieren. Sie können außerdem festlegen, die **CRecordset:: userAllocMultiRowBuffers** Option. Der Mechanismus Bulk Record Field Exchange verwendet Arrays zum Speichern von der mehrere Zeilen mit Daten, die bei einem Abrufvorgang abgerufen. Diese Speicherpuffer automatisch vom Framework zugeordnet werden können, oder Sie können diese manuell zuordnen. Angeben der **CRecordset:: userAllocMultiRowBuffers** Option bedeutet, dass Sie die Zuweisung erfolgt.  
  
 Die folgende Tabelle enthält die Memberfunktionen von bereitgestellten `CRecordset` gesammelte unterstützen.  
  
|Member-Funktion|Beschreibung|  
|---------------------|-----------------|  
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|Virtuelle Funktion, die alle Fehler, die während des Abrufens auftreten behandelt.|  
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Implementiert den Sammel-Datensatzfeldaustausch. Automatisch aufgerufen, um Übertragungen mehrere Zeilen mit Daten aus der Datenquelle auf das Recordsetobjekt.|  
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Ruft die aktuelle Einstellung für die Größe des Rowsets ab.|  
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|Gibt an, wie viele Zeilen tatsächlich einem Abrufvorgang abgerufen wurden. In den meisten Fällen ist dies die Rowsetgröße, es sei denn, ein unvollständiges Rowset abgerufen wurde.|  
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|Gibt einen Fetch-Status für eine bestimmte Zeile innerhalb eines Rowsets zurück.|  
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Aktualisiert die Daten und den Status einer bestimmten Zeile innerhalb eines Rowsets.|  
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|Verschiebt den Cursor an einer bestimmten Zeile innerhalb eines Rowsets.|  
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Virtuelle Funktion, die die Einstellung für die Rowsetgröße auf den angegebenen Wert ändert.|  
  
##  <a name="_core_special_considerations"></a> Besonderheiten  
 Obwohl gesammelte einer Leistungssteigerung ist, arbeiten bestimmte Funktionen anders. Bevor Sie entscheiden, gesammelte implementieren, beachten Sie Folgendes:  
  
-   Ruft das Framework automatisch die `DoBulkFieldExchange` Memberfunktion zum Übertragen von Daten aus der Datenquelle auf das Recordsetobjekt. Allerdings werden Daten nicht aus dem Recordset zurück an die Datenquelle übertragen. Aufrufen der `AddNew`, **bearbeiten**, **löschen**, oder **Update** Ergebnissen der Member-Funktionen in einer fehlgeschlagenen Assertion. Obwohl `CRecordset` bieten derzeit keinen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen zu **SQLSetPos**, finden Sie unter der *ODBC SDK Programmer's Reference* in der MSDN-Dokumentation.  
  
-   Die Memberfunktionen `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty`, und `SetFieldNull` kann nicht in Recordsets, die gesammelte implementieren verwendet werden. Sie können jedoch aufrufen `GetRowStatus` anstelle von `IsDeleted`, und `GetODBCFieldInfo` anstelle von `IsFieldNullable`.  
  
-   Die **verschieben** -Operationen Recordset nach Rowsets. Nehmen Sie z. B. an, dass Sie ein Recordset öffnen, das 100 Datensätze mit einer anfänglichen Rowsetgröße von 10 verfügt. **Open** Zeilen 1 bis 10, mit dem aktuellen Datensatz positioniert für Zeile 1 abruft. Ein Aufruf von `MoveNext` Ruft das nächste Rowset, nicht auf die nächste Zeile ab. Dieses Rowset besteht aus den Zeilen 11 bis 20, mit dem aktuellen Datensatz in Zeile 11 positioniert. Beachten Sie, dass `MoveNext` und **Move (1)** sind kein Äquivalent, wenn gesammelte implementiert ist. **Verschieben von (1)** Ruft das Rowset, das 1 Zeile aus dem aktuellen Datensatz beginnt. In diesem Beispiel Aufrufen **Move (1)** nach dem Aufruf **öffnen** Ruft die Zeilen 2 bis 11, mit dem aktuellen Datensatz positioniert für Zeile 2 besteht Rowset ab. Weitere Informationen finden Sie unter der [verschieben](../../mfc/reference/crecordset-class.md#move) Memberfunktion.  
  
-   Im Gegensatz zu Datensatzfeldaustausch unterstützen die Assistenten Massen-Datensatzfeldaustausch. Dies bedeutet, dass müssen Sie manuell die Felddatenmember deklarieren und manuell überschreiben `DoBulkFieldExchange` durch Aufrufe der Bulk-RFX-Funktionen zu schreiben. Weitere Informationen finden Sie unter [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md) in der *Klassenbibliotheksreferenz*.  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> Gewusst wie: Implementieren der Massen-Datensatzfeldaustausch  
 Massen-Datensatzfeldaustausch überträgt ein Rowset von Daten aus der Datenquelle an das Recordsetobjekt. Die Bulk-RFX-Funktionen verwenden Arrays zum Speichern dieser Daten als auch Arrays, die die Länge jedes Elements Daten im Rowset zu speichern. In der Klasse müssen Sie die Felddatenmember als Zeiger auf die Arrays von Daten definieren. Darüber hinaus müssen Sie einen Satz von Zeigern auf Arrays der Längen definieren. Parameterdatenmember sollten nicht als Zeiger deklariert werden. Parameterdatenmember deklarieren, bei Verwendung der Massen-Datensatzfeldaustausch ist identisch mit der sie bei Verwendung von Datensatzfeldaustausch deklarieren. Der folgende Code zeigt ein einfaches Beispiel:  
  
```  
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
  
 Sie können diese Speicherpuffer manuell zuordnen oder vom Framework erledigen lassen. Um den Puffer selbst zuzuordnen, müssen Sie angeben der **CRecordset:: userAllocMultiRowBuffers** -Option von der **OpenEx** Parameter in der **öffnen** Memberfunktion. Achten Sie darauf, dass die Größe der Arrays mindestens die Rowsetgröße gleich festgelegt werden. Wenn Sie das Framework müssen die Zuordnung verwenden möchten, sollten Sie die Zeiger in initialisieren **NULL.** Dies geschieht normalerweise im Konstruktor des Recordset-Objekts:  
  
```  
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
  
 Schließlich müssen Sie überschreiben die `DoBulkFieldExchange` Memberfunktion. Rufen Sie die Bulk-RFX-Funktionen, für den Felddatenmembern; für alle Parameterdatenmember Aufrufen der RFX-Funktionen. Wenn Sie das Recordset geöffnet, durch das Übergeben einer SQL-Anweisung oder gespeicherte Prozedur **öffnen**, muss die Reihenfolge, in dem Sie die Bulk-RFX-Aufrufe, Reihenfolge der Spalten im Recordset entsprechen; Analog dazu verlangt die Reihenfolge der RFX-für Parameter müssen die Reihenfolge der Parameter in der SQL-Anweisung entsprechen oder die gespeicherte Prozedur.  
  
```  
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
>  Rufen Sie die **schließen** Memberfunktion vor Ihrer abgeleiteten `CRecordset` Klasse den Gültigkeitsbereich verlässt. Dadurch wird sichergestellt, dass durch das Framework zugewiesener Speicher freigegeben werden. Es gilt als guter Programmierstil immer explizit aufrufen **schließen**, unabhängig davon, ob Sie nun das gesammelte Abrufen von Zeilen implementiert haben.  
  
 Weitere Informationen zu den Datensatzfeldaustausch (RFX), finden Sie unter [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Weitere Informationen zur Verwendung von Parametern finden Sie unter [CFieldExchange::](../../mfc/reference/cfieldexchange-class.md#setfieldtype) und [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)   
 [CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)

