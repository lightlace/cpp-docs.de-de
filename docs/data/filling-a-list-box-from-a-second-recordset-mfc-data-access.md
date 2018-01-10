---
title: "Füllen eines Listenfelds aus einem zweiten Recordset (MFC-Datenzugriff) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views, filling list boxes
- list boxes, filling from second recordset
- recordsets [C++], filling list boxes or combo boxes
- CComboBox class, filling object from second rowset
- ODBC recordsets [C++], filling list boxes or combo boxes
- combo boxes [C++], filling from second recordset
- CListCtrl class, filling from second recordset
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6e411ebcf40099a2236048dd8f151b438fe5b947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="filling-a-list-box-from-a-second-recordset--mfc-data-access"></a>Füllen eines Listenfelds aus einem zweiten Recordset MFC-(Datenzugriff)
Standardmäßig ist eine Datensatzansicht mit einem einzigen Recordset-Objekt verknüpft, dessen Felder den Steuerelementen der Datensatzansicht zugeordnet sind. Manchmal möchten Sie ein Listenfeld- oder Kombinationsfeld-Steuerelement in die Datensatzansicht einfügen und mit Werten aus einem zweiten Recordset-Objekt füllen. Der Benutzer kann das Listenfeld zur Auswahl einer neuen Kategorie von Informationen verwenden, die in der Datensatzansicht angezeigt werden sollen. In diesem Thema wird beschrieben, wie und wann Sie dies tun sollten.  
  
> [!TIP]
>  Beachten Sie, dass das Füllen eines Listen- oder Kombinationsfelds aus einer Datenquelle langsam sein kann. Treffen Sie Vorsichtsmaßnahmen, um zu vermeiden, dass ein Steuerelement mit einer großen Anzahl von Datensätzen aus einem Recordset gefüllt wird.  
  
 Das Modell für dieses Thema besteht aus einem primären Recordset, das die Steuerelemente des Formulars füllt. Mit einem sekundären Recordset wird ein Listen- oder Kombinationsfeld gefüllt. Die Auswahl einer Zeichenfolge im Listenfeld veranlasst das Programm, das primäre Recordset basierend auf der Auswahl abzufragen. In der folgenden Prozedur wird ein Kombinationsfeld verwendet, sie ist jedoch auch auf ein Listenfeld anwendbar.  
  
#### <a name="to-fill-a-combo-box-or-list-box-from-a-second-recordset"></a>So füllen Sie ein Kombinations- oder Listenfeld aus einem zweiten Recordset  
  
1.  Erstellen Sie das Recordsetobjekt ([CRecordset](../mfc/reference/crecordset-class.md).  
  
2.  Abrufen eines Zeigers auf die [CComboBox](../mfc/reference/ccombobox-class.md) Objekt für ein Kombinationsfeld-Steuerelement.  
  
3.  Löschen Sie vorherige Inhalte aus dem Kombinationsfeld.  
  
4.  Navigieren Sie durch alle Datensätze im Recordset Aufrufen [CComboBox:: AddString](../mfc/reference/ccombobox-class.md#addstring) für jede Zeichenfolge des aktuellen Datensatzes, die Sie im Kombinationsfeld hinzufügen möchten.  
  
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
  
 Diese Funktion verwendet das zweites Recordset `m_courseSet`, das einen Datensatz für jeden angebotenen Kurs enthält, sowie ein `CComboBox`-Steuerelement, `m_ctlCourseList`, das in der Datensatzansichtsklasse gespeichert ist.  
  
 Die Funktion ruft `m_courseSet` aus dem Dokument ab und öffnet sie. Anschließend leert sie `m_ctlCourseList` und scrollt durch `m_courseSet`. Die Funktion ruft für jeden Datensatz die `AddString`-Memberfunktion des Kombinationsfelds auf, um den Kurs-ID-Wert aus dem Datensatz hinzuzufügen. Abschließend legt der Code die Auswahl des Kombinationsfelds fest.  
  
## <a name="see-also"></a>Siehe auch  
 [Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)