---
title: "F&#252;llen eines Listenfelds aus einem zweiten Recordset MFC-(Datenzugriff)"
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
  - "CComboBox-Klasse, Füllen eines Objekts aus zweitem Rowset"
  - "CListCtrl-Klasse, Füllen aus zweitem Recordset"
  - "Kombinationsfelder [C++], Füllen aus zweitem Recordset"
  - "DAO-Recordsets"
  - "DAO-Recordsets, Füllen von Listen- oder Kombinationsfeldern"
  - "Füllen von Listen- oder Kombinationsfeldern"
  - "Listenfelder, Füllen aus zweitem Recordset"
  - "Mehrere Recordsets in Datensatzansichten"
  - "ODBC-Recordsets [C++], Füllen von Listen- oder Kombinationsfeldern"
  - "Datensatzansichten, Füllen von Listenfeldern"
  - "Recordsets [C++], Füllen von Listen- oder Kombinationsfeldern"
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# F&#252;llen eines Listenfelds aus einem zweiten Recordset MFC-(Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig ist eine Datensatzansicht mit einem einzigen Recordset\-Objekt verknüpft, dessen Felder den Steuerelementen der Datensatzansicht zugeordnet sind.  Manchmal möchten Sie ein Listenfeld\- oder Kombinationsfeld\-Steuerelement in die Datensatzansicht einfügen und mit Werten aus einem zweiten Recordset\-Objekt füllen.  Der Benutzer kann das Listenfeld zur Auswahl einer neuen Kategorie von Informationen verwenden, die in der Datensatzansicht angezeigt werden sollen.  In diesem Thema wird beschrieben, wie und wann Sie dies tun sollten.  
  
> [!TIP]
>  Beachten Sie, dass das Füllen eines Listen\- oder Kombinationsfelds aus einer Datenquelle langsam sein kann.  Treffen Sie Vorsichtsmaßnahmen, um zu vermeiden, dass ein Steuerelement mit einer großen Anzahl von Datensätzen aus einem Recordset gefüllt wird.  
  
 Das Modell für dieses Thema besteht aus einem primären Recordset, das die Steuerelemente des Formulars füllt. Mit einem sekundären Recordset wird ein Listen\- oder Kombinationsfeld gefüllt.  Die Auswahl einer Zeichenfolge im Listenfeld veranlasst das Programm, das primäre Recordset basierend auf der Auswahl abzufragen.  In der folgenden Prozedur wird ein Kombinationsfeld verwendet, sie ist jedoch auch auf ein Listenfeld anwendbar.  
  
#### So füllen Sie ein Kombinations\- oder Listenfeld aus einem zweiten Recordset  
  
1.  Erstellen Sie das Recordset\-Objekt \([CRecordset](../mfc/reference/crecordset-class.md) für ODBC, [CDaoRecordset](../mfc/reference/cdaorecordset-class.md) für DAO\).  
  
2.  Rufen Sie einen Zeiger auf das [CComboBox](../mfc/reference/ccombobox-class.md)\-Objekt für das Kombinationsfeld\-Steuerelement ab.  
  
3.  Löschen Sie vorherige Inhalte aus dem Kombinationsfeld.  
  
4.  Navigieren Sie durch alle Datensätze im Recordset, rufen Sie [CComboBox::AddString](../Topic/CComboBox::AddString.md) für jede Zeichenfolge des aktuellen Datensatzes auf, den Sie zum Kombinationsfeld hinzufügen möchten.  
  
5.  Initialisieren Sie die Auswahl im Kombinationsfeld.  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
    // ...  
  
    // Fill the combo box with all of the courses  
    CENROLLDoc* pDoc = GetDocument();  
    if (!pDoc->m_courseSet.Open())  
        return;  
  
    // ...  
  
    m_ctlCourseList.ResetContent();  
    if (pDoc->m_courseSet.IsOpen())  
    {   
        while (!pDoc->m_courseSet.IsEOF() )  
        {  
            m_ctlCourseList.AddString(  
                pDoc->m_courseSet.m_CourseID);  
            pDoc->m_courseSet.MoveNext();  
        }  
    }  
    m_ctlCourseList.SetCurSel(0);  
}  
```  
  
 Diese Funktion verwendet das zweites Recordset `m_courseSet`, das einen Datensatz für jeden angebotenen Kurs enthält, sowie ein `CComboBox`\-Steuerelement, `m_ctlCourseList`, das in der Datensatzansichtsklasse gespeichert ist.  
  
 Die Funktion ruft `m_courseSet` aus dem Dokument ab und öffnet sie.  Anschließend leert sie `m_ctlCourseList` und scrollt durch `m_courseSet`.  Die Funktion ruft für jeden Datensatz die `AddString`\-Memberfunktion des Kombinationsfelds auf, um den Kurs\-ID\-Wert aus dem Datensatz hinzuzufügen.  Abschließend legt der Code die Auswahl des Kombinationsfelds fest.  
  
## Siehe auch  
 [Datensatzansichten \(MFC\-Datenzugriff\)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md)