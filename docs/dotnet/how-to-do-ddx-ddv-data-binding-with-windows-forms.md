---
title: 'Vorgehensweise: DDX DDV-Datenbindung in Windows Forms | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2f6992aa0c7238d2dc89a8084c7b870dae23067a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131659"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Gewusst wie: DDX-/DDV-Datenbindung mit Windows Forms
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) Aufrufe [CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) Erstellen eines Steuerelements mit der Ressource Steuerelement-ID übereinstimmt. Bei Verwendung von `DDX_ManagedControl` für eine `CWinFormsControl` -Steuerelement (in vom Assistenten generierten Code), rufen Sie nicht `CreateManagedControl` explizit für das Steuerelement.  
  
 Rufen Sie `DDX_ManagedControl` in [Ddx_managedcontrol](../mfc/reference/cwnd-class.md#dodataexchange) So erstellen Sie Steuerelemente aus der Ressourcen-IDs. Für den Datenaustausch müssen Sie nicht die DDX-/DDV-Funktionen mit Windows Forms-Steuerelemente verwenden. Platzieren Sie stattdessen Code für den Zugriff auf die Eigenschaften des verwalteten Steuerelements in der `DoDataExchange` -Methode einer Klasse Dialogfeld (oder Sicht), wie im folgenden Beispiel gezeigt.  
  
 Im folgende Beispiel wird gezeigt, wie eine systemeigene C++-Zeichenfolge in einem Benutzersteuerelement .NET gebunden wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden ist ein Beispiel der DDX-/DDV-Datenbindung eine MFC-Zeichenfolge `m_str` mit der benutzerdefinierte `NameText` Eigenschaft eines Benutzersteuerelements .NET.  
  
 Das Steuerelement wird erstellt, wenn [CDialog::](../mfc/reference/cdialog-class.md#oninitdialog) Aufrufe `CMyDlg::DoDataExchange` zum ersten Mal daher keinen Code, der Verweise `m_UserControl` müssen nach stammen die `DDX_ManagedControl` aufrufen.  
  
 Sie können diesen Code implementieren, in der MFC01-Anwendung, die Sie erstellt, im haben [Vorgehensweise: Erstellen des Benutzersteuerelements und Host in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
 Platzieren Sie den folgenden Code in der Deklaration der CMFC01Dlg:  
  
```  
class CMFC01Dlg : public CDialog  
{  
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;  
   CString m_str;  
};  
```  
  
## <a name="example"></a>Beispiel  
 Platzieren Sie den folgenden Code in der Implementierung der CMFC01Dlg:  
  
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
  
## <a name="example"></a>Beispiel  
 Jetzt werden wir die Handlermethode für mit einem Klick auf die Schaltfläche "OK" hinzufügen. Klicken Sie auf die **Ressourcenansicht** Registerkarte. Doppelklicken Sie in der Ressourcenansicht auf `IDD_MFC01_DIALOG`. Die Dialogressource wird in den Ressourcen-Editor angezeigt. Klicken Sie dann Doppelklicken auf die Schaltfläche "OK"...  
  
 Definieren Sie den Ereignishandler wie folgt.  
  
```  
void CMFC01Dlg::OnBnClickedOk()  
{  
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));  
   OnOK();  
}  
```  
  
## <a name="example"></a>Beispiel  
 Ein, und fügen Sie die folgende Zeile auf die Implementierung von BOOL CMFC01Dlg::OnInitDialog().  
  
```  
m_MyControl.GetControl()->textBox1->Text = "hello";  
```  
  
 Sie können jetzt erstellen, und führen Sie die Anwendung. Beachten Sie, dass der gesamte Text im Textfeld in einem Popup-Meldungsfeld angezeigt wird, wenn die Anwendung geschlossen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [CWinFormsControl-Klasse](../mfc/reference/cwinformscontrol-class.md)   
 [DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)   
 [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)