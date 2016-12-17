---
title: "Recordset: Abrufen von Datens&#228;tzen in einer Sammeloperation (ODBC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Sammel-Datensatzfeldaustausch"
  - "Sammel-RFX-Funktionen"
  - "Gesammeltes Abrufen von Zeilen"
  - "Gesammeltes Abrufen von Zeilen, Implementieren"
  - "DoBulkFieldExchange-Methode"
  - "Abrufen von ODBC-Datensätze in einer Sammeloperation"
  - "ODBC-Recordsets, Gesammeltes Abrufen von Zeilen"
  - "Recordsets, Gesammeltes Abrufen von Zeilen"
  - "RFX (ODBC), Gesammelt"
  - "RFX (ODBC), Gesammeltes Abrufen von Zeilen"
  - "Rowsets, Gesammeltes Abrufen von Zeilen"
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Abrufen von Datens&#228;tzen in einer Sammeloperation (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Die `CRecordset`\-Klasse unterstützt das gesammelte Abrufen von Zeilen. Bei diesem Prozess können in einer einzigen Abrufoperation mehrere Datensätze und nicht nur ein einziger Datensatz von der Datenquelle abgerufen werden.  Sie können das gesammelte Abrufen von Zeilen nur in einer von `CRecordset` abgeleiteten Klasse implementieren.  Der Prozess des Datentransfers von der Datenquelle in das Recordset\-Objekt wird als Sammel\-Datensatzfeldaustausch \(Bulk\-RFX\) bezeichnet.  Wenn Sie das gesammelte Abrufen von Zeilen in einer von `CRecordset` abgeleiteten Klasse nicht verwenden, werden die Daten per Datensatzfeldaustausch \(RFX\) übertragen.  Weitere Informationen hierzu finden Sie unter [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md).  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Wie CRecordset das gesammelte Abrufen von Zeilen unterstützt](#_core_how_crecordset_supports_bulk_row_fetching).  
  
-   [Was Sie beim gesammelten Abrufen von Zeilen beachten müssen](#_core_special_considerations).  
  
-   [Wie Sie den Sammel\-Datensatzfeldaustausch implementieren](#_core_how_to_implement_bulk_record_field_exchange).  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> Wie CRecordset das gesammelte Abrufen von Zeilen unterstützt  
 Vor dem Öffnen des Recordset\-Objekts können Sie mit der `SetRowsetSize`\-Memberfunktion die Größe eines Rowsets festlegen.  Die Größe des Rowsets gibt an, wie viele Datensätze während einer einzigen Abfrage abgerufen werden.  Wenn das gesammelte Abrufen von Zeilen implementiert ist, beträgt die Standardgröße des Rowsets 25.  Wenn das gesammelte Abrufen von Zeilen dagegen nicht implementiert ist, beträgt die Größe des Rowsets immer 1.  
  
 Nachdem Sie die Größe des Rowsets initialisiert haben, rufen Sie die [Open](../Topic/CRecordset::Open.md)\-Memberfunktion auf.  Übergeben Sie dabei im Parameter **dwOptions** den Wert `CRecordset::useMultiRowFetch`, damit das gesammelte Abrufen von Zeilen implementiert wird.  Sie können außerdem die Option **CRecordset::userAllocMultiRowBuffers** angeben.  Der Mechanismus für den Sammel\-Datensatzaustausch verwendet Arrays zum Speichern der abgefragten Datenzeilen.  Diese Speicherpuffer kann das Framework automatisch belegen. Sie können sie jedoch auch von Hand belegen.  Wenn Sie die Option **CRecordset::userAllocMultiRowBuffers** angeben, teilen Sie dem Framework mit, dass Sie den Speicher selbst belegen möchten.  
  
 Die folgende Tabelle führt die Memberfunktionen auf, die `CRecordset` für die Unterstützung des gesammelten Abrufens von Zeilen zur Verfügung stellt.  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)|Virtuelle Funktion zur Verarbeitung aller Fehler, die während des Abrufens auftreten.|  
|[DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)|Implementiert den Sammel\-Datensatzfeldaustausch.  Wird automatisch aufgerufen, um mehrere Datenzeilen von der Datenquelle in das Recordset\-Objekt zu übertragen.|  
|[GetRowsetSize](../Topic/CRecordset::GetRowsetSize.md)|Ruft die aktuelle Einstellung für die Größe des Rowsets ab.|  
|[GetRowsFetched](../Topic/CRecordset::GetRowsFetched.md)|Gibt darüber Auskunft, wie viele Zeilen bei einem Abrufvorgang tatsächlich abgefragt wurden.  In den meisten Fällen ist dies die Größe des Rowsets, sofern kein unvollständiges Rowset abgerufen wurde.|  
|[GetRowStatus](../Topic/CRecordset::GetRowStatus.md)|Gibt den Abrufstatus für eine bestimmte Zeile innerhalb eines Rowsets zurück.|  
|[RefreshRowset](../Topic/CRecordset::RefreshRowset.md)|Aktualisiert die Daten und den Status einer bestimmten Zeile innerhalb eines Rowsets.|  
|[SetRowsetCursorPosition](../Topic/CRecordset::SetRowsetCursorPosition.md)|Bewegt den Cursor auf eine bestimmte Zeile innerhalb eines Rowsets.|  
|[SetRowsetSize](../Topic/CRecordset::SetRowsetSize.md)|Virtuelle Funktion, mit der die Größeneinstellung des Rowsets in den angegebenen Wert geändert wird.|  
  
##  <a name="_core_special_considerations"></a> Spezielle Überlegungen  
 Das gesammelte Abrufen von Zeilen erhöht zwar die Leistung, einige Funktionen arbeiten dabei aber anders.  Bevor Sie sich dafür entscheiden, das gesammelte Abrufen von Zeilen zu implementieren, sollten Sie folgende Überlegungen anstellen:  
  
-   Das Framework ruft die `DoBulkFieldExchange`\-Memberfunktion automatisch auf, um Daten von der Datenquelle in das Recordset\-Objekt zu übertragen.  Es werden allerdings keine Daten vom Recordset zurück in die Datenquelle übertragen.  Ein Aufruf der Memberfunktion `AddNew`, **Edit**, **Delete** oder **Update** löst eine Assertionsmeldung aus.  `CRecordset` unterstützt derzeit keinen Mechanismus zur gesammelten Aktualisierung von Datenzeilen. Sie können jedoch unter Verwendung der ODBC\-API\-Funktion **SQLSetPos** eigene Funktionen schreiben.  Weitere Informationen zu **SQLSetPos** finden Sie in *ODBC SDK Programmer's Reference* in der MSDN\-Dokumentation.  
  
-   Die Memberfunktionen `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty` und `SetFieldNull` können nicht in Recordsets eingesetzt werden, bei denen das gesammelte Abrufen von Zeilen implementiert ist.  Sie können statt `IsDeleted` allerdings `GetRowStatus` aufrufen und `GetODBCFieldInfo` statt `IsFieldNullable`.  
  
-   Die **Move**\-Operationen verschieben das Recordset nach Rowsets.  Angenommen, Sie öffnen ein Recordset, das 100 Datensätze enthält, deren ursprüngliche Rowsetgröße 10 beträgt.  **Open** ruft nun die Zeilen 1 bis 10 ab, der aktuelle Datensatz ist auf Zeile 1 eingestellt.  Bei einem Aufruf von `MoveNext` wird das nächste Rowset abgerufen und nicht die nächste Zeile.  Dieses Rowset besteht aus den Zeilen 11 bis 20, wobei der aktuelle Datensatz auf Zeile 11 positioniert ist.  Beachten Sie, dass `MoveNext` und **Move\( 1 \)** nicht äquivalent sind, wenn das gesammelte Abrufen von Zeilen implementiert ist.  **Move\( 1 \)** ruft das Rowset ab, das 1 Zeile nach dem aktuellen Datensatz beginnt.  Wenn Sie in diesem Beispiel gleich nach dem **Open**\-Aufruf **Move\( 1 \)** aufrufen, wird das Rowset abgerufen, das aus den Zeilen 2 bis 11 besteht.  Weitere Informationen hierzu finden Sie in der Dokumentation der [Move](../Topic/CRecordset::Move.md)\-Memberfunktion.  
  
-   Anders als beim Datensatzfeldaustausch bieten Assistenten keine Unterstützung für den Sammel\-Datensatzfeldaustausch.  Dies bedeutet, dass Sie die Felddatenmember explizit deklarieren müssen. Sie müssen auch `DoBulkFieldExchange` manuell überschreiben, indem Sie Aufrufe der Bulk\-RFX\-Funktionen schreiben.  Weitere Informationen finden Sie unter [Datensatzfeldaustausch\-Funktionen](../../mfc/reference/record-field-exchange-functions.md) in der *Class Library Reference*.  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> Implementieren des Sammel\-Datensatzfeldaustauschs  
 Der Sammel\-Datensatzfeldaustausch überträgt die Daten eines Rowsets von der Datenquelle in das Recordset\-Objekt.  Die Sammel\-RFX\-Funktionen verwenden Arrays, um diese Daten sowie die Länge jedes Datenelements im Rowset zu speichern.  In der Klassendefinition müssen Sie die Felddatenmember als Zeiger definieren, um Zugriff auf die Datenarrays zu erhalten.  Zusätzlich müssen Sie eine Gruppe von Zeigern für den Zugriff auf die Arrays mit den Längenangaben definieren.  Parameterdatenmember dürfen Sie nicht als Zeiger deklarieren. Wenn Sie den Sammel\-Datensatzfeldaustausch verwenden, deklarieren Sie Parameterdatenmember genauso wie beim normalen Datensatzfeldaustausch.  Der folgende Code zeigt ein einfaches Beispiel:  
  
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
  
 Sie können diese Speicherpuffer entweder manuell belegen oder diese Aufgabe vom Framework erledigen lassen.  Wenn Sie die Puffer selbst belegen möchten, müssen Sie im Parameter **dwOptions** der **Open**\-Memberfunktion die **CRecordset::userAllocMultiRowBuffers**\-Option angeben.  Stellen Sie sicher, dass die Arrays mindestens so groß sind wie das Rowset.  Wenn Sie möchten, dass das Framework den Speicher belegt, müssen Sie die Zeiger mit dem Wert **NULL** initialisieren. Hierfür wird normalerweise der Konstruktor des Recordset\-Objekts verwendet:  
  
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
  
 Schließlich müssen Sie noch die `DoBulkFieldExchange`\-Memberfunktion überschreiben.  Rufen Sie für alle Felddatenmember die Sammel\-RFX\-Funktionen auf. Rufen Sie für Parameterdatenmember die RFX\-Funktionen auf.  Wenn Sie beim Öffnen des Recordsets eine SQL\-Anweisung oder eine gespeicherte Prozedur an **Open** übergeben haben, muss die Reihenfolge, in der Sie die Sammel\-RFX\-Funktionen aufrufen, der Reihenfolge der Spalten im Recordset entsprechen. Ebenso muss die Reihenfolge der RFX\-Parameteraufrufe der Reihenfolge der Parameter der SQL\-Anweisung oder der gespeicherten Prozedur entsprechen.  
  
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
>  Sie müssen die **Close**\-Memberfunktion aufrufen, bevor die von `CRecordset` abgeleitete Klasse den aktuellen Gültigkeitsbereich verlässt.  So stellen Sie sicher, dass der gesamte vom Framework belegte Speicher freigegeben wird.  Es empfiehlt sich, **Close** immer explizit aufzurufen, ob Sie nun das gesammelte Abrufen von Zeilen implementiert haben oder nicht.  
  
 Weitere Informationen über Datensatzfeldaustausch \(RFX\) finden Sie unter [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  Weitere Informationen über den Einsatz von Parametern finden Sie unter [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md) und [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::m\_nFields](../Topic/CRecordset::m_nFields.md)   
 [CRecordset::m\_nParams](../Topic/CRecordset::m_nParams.md)