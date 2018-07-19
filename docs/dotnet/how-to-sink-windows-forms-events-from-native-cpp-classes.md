---
title: 'Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0fec32bf179424b5ec0164e4511f74eae44f7320
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130424"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Gewusst wie: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen
Sie können systemeigene C++-Klassen um verwaltete Ereignisse ausgelöst, die von Windows Forms-Steuerelementen oder anderen Formularen mit dem MFC-Rückrufe zu empfangen. Auffangen von Ereignissen in Ansichten und Dialogfelder ist ähnlich wie die gleiche Aufgabe für Steuerelemente.  
  
 Zu diesem Zweck müssen Sie:  
  
-   Fügen Sie ein `OnClick` -Ereignishandler, um das Steuerelement mit [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate).  
  
-   Erstellen Sie ein Delegat Karte mit [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), und [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry).  
  
 In diesem Beispiel wird die Arbeit in fortgesetzt [Vorgehensweise: Führen Sie DDX-/DDV-Datenbindung mit Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).  
  
 Jetzt, verknüpfen Sie Ihr MFC-Steuerelement (`m_MyControl`) mit einem verwalteten Ereignishandlerdelegaten aufgerufen `OnClick` für den verwalteten <xref:System.Windows.Forms.Control.Click> Ereignis.  
  
### <a name="to-attach-the-onclick-event-handler"></a>So fügen Sie Ereignishandler für OnClick an  
  
1.  Fügen Sie den folgenden Code für die Implementierung von BOOL CMFC01Dlg:: OnInitDialog hinzu:  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  Fügen Sie den folgenden Code, mit dem öffentlichen Abschnitt in der Deklaration der Klasse CMFC01Dlg: öffentliche CDialog.  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  Fügen Sie schließlich die Implementierung für `OnClick` auf die Datei "CMFC01Dlg.cpp":  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)   
 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)   
 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)