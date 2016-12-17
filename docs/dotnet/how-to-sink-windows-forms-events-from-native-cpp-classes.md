---
title: "Gewusst wie: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ereignisbehandlung, .NET/systemeigenes Interop"
  - "Ereignisbehandlung, Verwaltetes/systemeigenes Interop"
  - "Ereignisbehandlung, Auffangen von .NET in C++"
  - "Ereignisbehandlung, Windows Forms in C++"
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Systemeigene C\+\+\-Klassen sind in der Lage, Rückrufe von verwalteteten Ereignissen zu empfangen, die von Windows Forms\-Steuerelementen oder anderen Formularen mit dem MFC\-Makrozuordnungsformat ausgelöst wurden.  Das Auffangen von Ereignissen in Anzeigen und Dialogfeldern entspricht der Vorgehensweise bei Steuerelementen.  
  
 Verfahren Sie dazu wie folgt:  
  
-   Fügen Sie dem Steuerelement mit [MAKE\_DELEGATE](../Topic/MAKE_DELEGATE.md) einen `OnClick`\-Ereignishandler hinzu.  
  
-   Erstellen Sie mit [BEGIN\_DELEGATE\_MAP](../Topic/BEGIN_DELEGATE_MAP.md), [END\_DELEGATE\_MAP](../Topic/END_DELEGATE_MAP.md) und [EVENT\_DELEGATE\_ENTRY](../Topic/EVENT_DELEGATE_ENTRY.md) eine Delegatzuordnung.  
  
 In diesem Beispiel wird die Arbeit aus [Gewusst wie: DDX\-\/DDV\-Datenbindung mit Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md) fortgesetzt.  
  
 Nun verknüpfen Sie Ihr MFC\-Steuerelement \(`m_MyControl`\) mit einem verwalteten Ereignishandlerdelegaten mit dem Namen `OnClick` für das verwaltete <xref:System.Windows.Forms.Control.Click>\-Ereignis.  
  
### So fügen Sie den OnClick\-Ereignishandler an  
  
1.  Fügen Sie der Implementierung von "BOOL CMFC01Dlg::OnInitDialog" den folgenden Code hinzu:  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  Fügen Sie dem öffentlichen Abschnitt in der Deklaration der CMFC01Dlg : public CDialog\-Klasse den folgenden Code hinzu:  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  Fügen Sie abschließend der Datei "CMFC01Dlg.cpp" die Implementierung für `OnClick` hinzu:  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## Siehe auch  
 [MAKE\_DELEGATE](../Topic/MAKE_DELEGATE.md)   
 [BEGIN\_DELEGATE\_MAP](../Topic/BEGIN_DELEGATE_MAP.md)   
 [END\_DELEGATE\_MAP](../Topic/END_DELEGATE_MAP.md)   
 [EVENT\_DELEGATE\_ENTRY](../Topic/EVENT_DELEGATE_ENTRY.md)