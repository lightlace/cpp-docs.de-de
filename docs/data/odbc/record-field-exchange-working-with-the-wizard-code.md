---
title: 'Datensatzfeldaustausch: Arbeiten mit Assistenten-Code | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DoFieldExchange method, overriding
- Unicode, with database classes
- field data members, declaring
- RFX (ODBC), wizard code
- RFX (ODBC), implementing
- field data members
- ODBC, RFX
- m_nParams data member, initializing
- m_nFields data member
- m_nParams data member
- overriding, DoFieldExchange
- m_nFields data member, initializing
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d4f817ebfc3e6bb72865b4fc71fd5c5ebe5f671
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Datensatzfeldaustausch: Arbeiten mit Assistenten-Code
In diesem Thema wird erläutert, den Code, der MFC-Anwendung-Assistent und **Klasse hinzufügen** (wie in beschrieben [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) zur Unterstützung von RFX und wie Sie möchten möglicherweise ändern, Code zu schreiben.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von abgeleiteten Klassen `CRecordset` in denen der gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, wird der Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk RFX ähnelt RFX. Um die Unterschiede zu verstehen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Wenn Sie eine Recordset-Klasse erstellen, mit der MFC-Anwendungs-Assistenten oder **Klasse hinzufügen**, schreibt der Assistent die folgenden RFX-bezogene Elemente basierend auf der Datenquelle, Tabelle und die Auswahl von Spalten, die Sie im Assistenten vornehmen:  
  
-   Deklarationen von der Recordset-Felddatenmember der Recordset-Klasse  
  
-   Eine Überschreibung der `CRecordset::DoFieldExchange`  
  
-   Initialisierung der Recordset-Felddatenmember im Konstruktor Recordset-Klasse  
  
##  <a name="_core_the_field_data_member_declarations"></a> Feld Datenmemberdeklarationen  
 Die Assistenten schreiben eine Klassendeklaration Recordset in einem .h-Datei, die folgender Klasse ähnelt `CSections`:  
  
```  
class CSections : public CRecordset  
{  
public:  
   CSections(CDatabase* pDatabase = NULL);  
   DECLARE_DYNAMIC(CSections)  
  
// Field/Param Data  
   CString   m_strCourseID;  
   CString   m_strInstructorID;  
   CString   m_strRoomNo;  
   CString   m_strSchedule;  
   CString   m_strSectionNo;  
  
// Overrides  
   // Wizard generated virtual function overrides  
   protected:  
   virtual CString GetDefaultConnect();  // Default connection string  
   virtual CString GetDefaultSQL();      // Default SQL for Recordset  
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support  
  
// Implementation  
#ifdef _DEBUG  
   virtual void AssertValid() const;  
   virtual void Dump(CDumpContext& dc) const;  
#endif  
  
};  
```  
  
 Sie fügen Parameterdatenmember oder neue Felddatenmember, die Sie selbst binden, fügen sie nach dem vom Assistenten generierten diejenigen hinzu.  
  
 Beachten Sie, die der Assistent überschreibt die `DoFieldExchange` Memberfunktion der Klasse `CRecordset`.  
  
##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange-Überschreibung  

 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) bildet das Kernstück von RFX. Das Framework ruft `DoFieldExchange` jederzeit Daten aus der Datenquelle zum Recordset transferiert werden muss. `DoFieldExchange` Außerdem unterstützt das Abrufen von Informationen über Felddatenmember durch die [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) und [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) Memberfunktionen.  
  
 Die folgenden `DoFieldExchange` Außerkraftsetzung ist für die `CSections` Klasse. Der Assistent schreibt die Funktion in der CPP-Datei für die Recordsetklasse.  
  
```  
void CSections::DoFieldExchange(CFieldExchange* pFX)  
{  
   pFX->SetFieldType(CFieldExchange::outputColumn);  
   RFX_Text(pFX, "CourseID", m_strCourseID);  
   RFX_Text(pFX, "InstructorID", m_strInstructorID);  
   RFX_Text(pFX, "RoomNo", m_strRoomNo);  
   RFX_Text(pFX, "Schedule", m_strSchedule);  
   RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 Beachten Sie die folgenden Hauptfunktionen der Funktion:  
  
-   Dieser Abschnitt der Funktion wird die feldzuordnung aufgerufen.  
  
-   Ein Aufruf von `CFieldExchange::SetFieldType`, bis die `pFX` Zeiger. Dieser Aufruf gibt an, dass alle RFX-Funktion an das Ende des aufruft, oben `DoFieldExchange` oder beim nächsten Aufruf von `SetFieldType` Ausgabespalten sind. Weitere Informationen finden Sie unter [CFieldExchange::](../../mfc/reference/cfieldexchange-class.md#setfieldtype).  
  
-   Mehrere Aufrufe der `RFX_Text` globale Funktion – eine pro felddatenelement (alle sind `CString` Variablen im Beispiel). Diese Aufrufe geben die Beziehung zwischen den Namen einer Spalte in der Datenquelle und einen Datenmember des Felds. Die RFX-Funktionen sind die tatsächlichen Daten übertragen. Die Klassenbibliothek stellt RFX-Funktionen für die allgemeine Datentypen. Weitere Informationen über RFX-Funktionen finden Sie unter [Datensatzfeldaustausch: Verwenden der RFX-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).  
  
    > [!NOTE]
    >  Die Reihenfolge der Spalten im Resultset muss die Reihenfolge der RFX-Funktionsaufrufe in entsprechen `DoFieldExchange`.  
  
-   Die `pFX` Zeiger auf eine [CDBException](../../mfc/reference/cfieldexchange-class.md) -Objekt, das das Framework beim Aufruf übergeben wird `DoFieldExchange`. Die `CFieldExchange` Objekt gibt an, den Vorgang, `DoFieldExchange` ausführen, der die Richtung der Übertragung und andere Kontextinformationen ist.  
  
##  <a name="_core_the_recordset_constructor"></a> Recordset-Konstruktor  
 Der recordsetkonstruktor, den die Assistenten schreiben enthält zwei Dinge, die im Zusammenhang mit RFX:  
  
-   Eine Initialisierung für jedes felddatenelement  
  
-   Eine Initialisierung für die [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields) Datenmember, die die Anzahl der Felddatenmember enthält.  
  
 Der Konstruktor für die `CSections` Recordsetbeispiel sieht wie folgt aus:  
  
```  
CSections::CSections(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
   m_strCourseID = "";  
   m_strInstructorID = "";  
   m_strRoomNo = "";  
   m_strSchedule = "";  
   m_strSectionNo = "";  
   m_nFields = 5;  
}  
```  
  
> [!NOTE]
>  Wenn Sie alle Felddatenmember manuell hinzufügen, wie z. B. neue Spalten dynamisch zu binden, erhöhen Sie `m_nFields`. Klicken Sie dazu eine andere Zeile des Codes, wie z. B. anfügen:  
  
```  
m_nFields += 3;  
```  

 Dies ist der Code für die drei neue Felder hinzufügen. Wenn Sie alle Parameterdatenmember hinzufügen, müssen Sie initialisieren die [M_nParams](../../mfc/reference/crecordset-class.md#m_nparams) Datenmember, die die Anzahl der Parameterdatenmember enthält. Versetzen der `m_nParams` Initialisierung außerhalb der Klammern.  

  
## <a name="see-also"></a>Siehe auch  
 [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)