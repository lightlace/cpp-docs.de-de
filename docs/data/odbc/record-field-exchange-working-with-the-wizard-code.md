---
title: "Datensatzfeldaustausch: Arbeiten mit Assistenten-Code | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoFieldExchange-Methode, Überschreiben"
  - "Felddatenmember"
  - "Felddatenmember, Deklarieren"
  - "m_nFields-Datenmember"
  - "m_nFields-Datenmember, Initialisieren"
  - "m_nParams-Datenmember"
  - "m_nParams-Datenmember, Initialisieren"
  - "ODBC, RFX"
  - "Überschreiben, DoFieldExchange"
  - "RFX (ODBC), Implementieren"
  - "RFX (ODBC), Assistentencode"
  - "Unicode, Mit Datenbankklassen"
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Datensatzfeldaustausch: Arbeiten mit Assistenten-Code
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden der vom MFC\-Anwendungs\-Assistenten und von **Klasse hinzufügen** eingefügte Code zur Unterstützung von RFX erläutert \(wie beschrieben unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\). Des Weiteren wird dort erläutert, wie dieser Code geändert werden kann.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Beim gesammelten Abrufen von Zeilen wird der Sammel\-Datensatzfeldaustausch \(Bulk\-RFX\) implementiert.  Der Bulk\-RFX ist mit RFX vergleichbar.  Unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) werden die Unterschiede erläutert.  
  
 Wenn Sie mit dem MFC\-Anwendungs\-Assistenten oder **Klasse hinzufügen** eine Recordset\-Klasse erstellen, erstellt der Assistent auf der Basis der von Ihnen getroffenen Auswahl von Datenquelle, Tabelle und Spalte die folgenden RFX\-bezogenen Elemente:  
  
-   Deklarationen der Felddatenmember des Recordsets in der Recordset\-Klasse  
  
-   Überschreiben von `CRecordset::DoFieldExchange`  
  
-   Eine Initialisierung der Recordset\-Felddatenmember im Konstruktor der Recordset\-Klasse.  
  
##  <a name="_core_the_field_data_member_declarations"></a> Felddatenmember\-Deklarationen  
 Durch die Assistenten wird in eine H\-Datei eine Deklaration der Recordset\-Klasse geschrieben, die für die `CSections`\-Klasse wie folgt aussehen könnte:  
  
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
  
 Falls Sie Parameterdatenmember oder neue Felddatenmember hinzufügen möchten, die Sie selbst binden, fügen Sie diese hinter denen ein, die durch den Assistenten erstellt wurden.  
  
 Beachten Sie, dass der Assistent die **DoFieldExchange**\-Memberfunktion der **CRecordset\-**Klasse überschreibt.  
  
##  <a name="_core_the_dofieldexchange_override"></a> Überschreiben von DoFieldExchange  
 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) bildet das Kernstück von RFX.  `DoFieldExchange` wird durch das Framework immer dann aufgerufen, wenn Daten zwischen Datenquelle und Recordset transferiert werden müssen.  `DoFieldExchange` unterstützt darüber hinaus das Ermitteln von Informationen über Felddatenmember durch die [IsFieldDirty](../Topic/CRecordset::IsFieldDirty.md)\-Memberfunktion und die [IsFieldNull](../Topic/CRecordset::IsFieldNull.md)\-Memberfunktion.  
  
 Die folgende `DoFieldExchange`\-Überschreibung gilt der `CSections`\-Klasse.  Der Assistent fügt die Funktion in die CPP\-Datei der Recordset\-Klasse ein.  
  
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
  
 Beachten Sie bei dieser Funktion folgende, besonders wichtige Features:  
  
-   Dieser Abschnitt der Funktion wird als Feldzuordnung bezeichnet.  
  
-   Ein Aufruf von `CFieldExchange::SetFieldType` über den Zeiger `pFX`.  Durch diesen Aufruf wird festgelegt, dass alle RFX\-Funktionsaufrufe bis zum Ende von `DoFieldExchange` oder bis zum nächsten Aufruf von `SetFieldType` Ausgabespalten sind.  Weitere Informationen hierzu finden Sie unter [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md).  
  
-   Mehrere Aufrufe der globalen Funktion `RFX_Text`, und zwar ein Aufruf pro Felddatenmember \(die in diesem Beispiel alle `CString`\-Variablen sind\).  Durch diese Aufrufe wird die Beziehung zwischen einem Spaltennamen der Datenquelle und einem Felddatenmember festgelegt.  Die RFX\-Funktionen führen den eigentlichen Datentransfer durch.  Die Klassenbibliothek stellt für alle wichtigen Datentypen RFX\-Funktionen zur Verfügung.  Weitere Informationen über RFX\-Funktionen finden Sie unter [Datensatzfeldaustausch: Verwenden der RFX\-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).  
  
    > [!NOTE]
    >  Die Reihenfolge der Spalten in einem Resultset muss mit der Reihenfolge der RFX\-Funktionsaufrufe in `DoFieldExchange` übereinstimmen.  
  
-   Der Zeiger `pFX` verweist auf ein [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)\-Objekt, das vom Framework beim Aufruf von `DoFieldExchange` übergeben wird.  Das `CFieldExchange`\-Objekt gibt unter anderem an, welche Operation `DoFieldExchange` ausführen soll und in welcher Richtung der Datentransfer stattfindet.  
  
##  <a name="_core_the_recordset_constructor"></a> Recordset\-Konstruktor  
 Der von den Assistenten erstellte Recordset\-Konstruktor enthält zwei RFX\-bezogene Elemente:  
  
-   Eine Initialisierung für jeden Felddatenmember;  
  
-   Eine Initialisierung für den Datenmember [m\_nFields](../Topic/CRecordset::m_nFields.md), der die Anzahl der Felddatenmember enthält.  
  
 Der Konstruktor für das `CSections`\-Recordset\-Beispiel sieht wie folgt aus:  
  
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
>  Wenn Sie beliebige Felddatenmember von Hand hinzufügen, um z. B. neue Spalten dynamisch zu binden, müssen Sie `m_nFields` inkrementieren.  Verwenden Sie hierzu eine neue Codezeile wie die Folgende:  
  
```  
m_nFields += 3;  
```  
  
 Dieser Code bedeutet, dass drei neue Felder hinzugefügt werden.  Falls Sie Parameterdatenmember hinzufügen, müssen Sie den Datenmember [m\_nParams](../Topic/CRecordset::m_nParams.md) initialisieren, der die Anzahl der Parameterdatenmember enthält.  Fügen Sie die `m_nParams`\-Initialisierung außerhalb der Klammern ein.  
  
## Siehe auch  
 [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)