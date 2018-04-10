---
title: 'Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2dd3778dad837ffe23d17b58b4e579844dc71f40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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