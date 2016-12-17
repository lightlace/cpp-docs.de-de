---
title: "Gewusst wie: DDX-/DDV-Datenbindung mit Windows Forms"
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
  - "MFC [C++], Hosten eines Windows Forms-Steuerelements"
  - "Windows Forms [C++], MFC-Unterstützung"
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: DDX-/DDV-Datenbindung mit Windows Forms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[DDX\_ManagedControl](../Topic/DDX_ManagedControl.md) ruft [CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md) auf, um ein Steuerelement zu erstellen, das der ID des Ressourcensteuerelements entspricht.  Wenn Sie `DDX_ManagedControl` für ein `CWinFormsControl`\-Steuerelement verwenden \(in durch den Assistenten erstelltem Code\), sollte `CreateManagedControl` nicht explizit für das gleiche Steuerelement aufgerufen werden.  
  
 Rufen Sie in [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md) `DDX_ManagedControl` auf, um aus Ressourcen\-IDs Steuerelemente zu erstellen.  Für den Datenaustausch ist es nicht notwendig, die DDX\/DDV\-Funktionen mit Windows Forms\-Steuerelementen zu verwenden.  Stattdessen können Sie in der `DoDataExchange`\-Methode der Dialog\- oder Ansichtsklasse Code platzieren, um auf die Eigenschaften des verwalteten Steuerelements zuzugreifen. Dies wird im folgenden Beispiel erläutert.  
  
 Im folgenden Beispiel wird gezeigt, wie eine systemeigene C\+\+\-Zeichenfolge an ein .NET\-Benutzersteuerelement gebunden wird.  
  
## Beispiel  
 Es folgt ein Beispiel einer DDX\/DDV\-Datenbindung einer MFC\-Zeichenfolge `m_str` mit einer benutzerdefinierten `NameText`\-Eigenschaft eines .NET\-Benutzersteuerelements.  
  
 Das Steuerelement wird erstellt, wenn `CMyDlg::DoDataExchange` zum ersten Mal durch [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md) aufgerufen wird. Deshalb muss jeder Code, der auf `m_UserControl` verweist, nach dem `DDX_ManagedControl`\-Aufruf platziert werden.  
  
 Sie können diesen Code in der MFC01\-Anwendung implementieren, die Sie in [Gewusst wie: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) erstellt haben.  
  
 Fügen Sie den folgenden Code in die Deklaration von CMFC01Dlg ein:  
  
```  
class CMFC01Dlg : public CDialog  
{  
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;  
   CString m_str;  
};  
```  
  
## Beispiel  
 Fügen Sie den folgenden Code in die Implementierung von CMFC01Dlg ein:  
  
```  
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
{  
   CDialog::DoDataExchange(pDX);  
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);  
  
   if (pDX->m_bSaveAndValidate) {  
      m_str = m_MyControl->textBox1->Text;  
   } else  
   {  
      m_MyControl->textBox1->Text = gcnew System::String(m_str);  
   }  
}  
```  
  
## Beispiel  
 Nun wird die Handlermethode für einen Klick auf die Schaltfläche OK hinzugefügt.  Klicken Sie auf die Registerkarte **Ressourcenansicht**.  Doppelklicken Sie in der Ressourcenansicht auf `IDD_MFC01_DIALOG`.  Die Dialogressource wird in Ressourcen\-Editor angezeigt.  Doppelklicken Sie dann auf die Schaltfläche OK.  
  
 Definieren Sie den Handler wie folgt.  
  
```  
void CMFC01Dlg::OnBnClickedOk()  
{  
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));  
   OnOK();  
}  
```  
  
## Beispiel  
 Fügen Sie der Implementierung von BOOL CMFC01Dlg::OnInitDialog\(\) die folgende Zeile hinzu.  
  
```  
m_MyControl.GetControl()->textBox1->Text = "hello";  
```  
  
 Sie können die Anwendung jetzt erstellen und ausführen.  Beachten Sie, dass der Text im Textfeld beim Schließen der Anwendung in einem Popupmeldungsfeld angezeigt wird.  
  
## Siehe auch  
 [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md)   
 [DDX\_ManagedControl](../Topic/DDX_ManagedControl.md)   
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)