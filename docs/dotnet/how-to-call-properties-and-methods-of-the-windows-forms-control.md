---
title: "Gewusst wie: Aufrufen von Ereignissen und Methoden des Windows Forms-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Aufrufen von Methoden, Windows Forms-Steuerelemente"
  - "Aufrufen von Eigenschaften"
  - "Aufrufen von Eigenschaften, Windows Forms-Steuerelemente"
  - "Methodenaufrufe, Windows Forms"
  - "Steuerelemente für Windows Forms [C++], Methoden"
  - "Steuerelemente für Windows Forms [C++], Eigenschaften"
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Gewusst wie: Aufrufen von Ereignissen und Methoden des Windows Forms-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Da [CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md) einen Zeiger auf <xref:System.Windows.Forms.Control?displayProperty=fullName> und keinen Zeiger auf `WindowsControlLibrary1::UserControl1` zurückgibt, sollten Sie einen Member des Benutzersteuerelement\-Typs hinzufügen und diesen in [IView::OnInitialUpdate](../Topic/IView::OnInitialUpdate.md) initialisieren.  Jetzt können Sie Methoden und Eigenschaften mit `m_ViewControl` aufrufen.  
  
 In diesem Thema wird davon ausgegangen, dass Sie zuvor die Themen [Gewusst wie: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) und [Gewusst wie: Erstellen des Benutzersteuerelements und Hosten der MDI\-Ansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md) gelesen haben.  
  
### So erstellen Sie die MFC\-Hostanwendung  
  
1.  Öffnen Sie die MFC\-Anwendung, die Sie in [Gewusst wie: Erstellen des Benutzersteuerelements und Hosten der MDI\-Ansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md) erstellt haben.  
  
2.  Fügen Sie dem Abschnitt zu öffentlichen Überschreibungen der `CMFC02View`\-Klassendeklaration in MFC02View.h die folgende Zeile hinzu.  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  Fügen Sie eine Überschreibung für OnInitialupdate hinzu.  
  
     Zeigen Sie das **Eigenschaftenfenster** an \(F4\).  Wählen Sie in **Klassenansicht** \(STRG\+UMSCHALT\+C\) die CMFC02View\-Klasse aus.  Wählen Sie im **Eigenschaftenfenster** das Symbol für Überschreibungen aus.  Führen Sie einen Bildlauf in der Liste bis zu OnInitialUpdate aus.  Klicken Sie in der Dropdownliste ausgewählte \<\>und hinzufügen.  In "MFC02View.cpp" Stellen Sie sicher, dass der Text der OnInitialUpdate\-Funktion, wie folgt:  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.  
  
     Beachten Sie, dass das Textfeld jetzt initialisiert ist.  
  
## Siehe auch  
 [Hosten eines Windows Forms\-Benutzersteuerelements als MFC\-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)