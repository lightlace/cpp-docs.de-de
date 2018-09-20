---
title: 'Vorgehensweise: DDX-/ DDV-Datenbindung mit Windows Forms | Microsoft-Dokumentation'
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
ms.openlocfilehash: 87e6eb6e845a7e900568494ed2834f23b9f6c175
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418048"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Gewusst wie: DDX-/DDV-Datenbindung mit Windows Forms

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) Aufrufe [CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) zum Erstellen eines Steuerelements mit der Resource-Steuerelement-ID übereinstimmt. Bei Verwendung von `DDX_ManagedControl` für eine `CWinFormsControl` Control (im Assistenten generierte Code), sollten Sie nicht aufrufen `CreateManagedControl` explizit für das Steuerelement.

Rufen Sie `DDX_ManagedControl` in [Ddx_managedcontrol](../mfc/reference/cwnd-class.md#dodataexchange) zum Erstellen von Steuerelementen aus Ressourcen-IDs. Für den Datenaustausch verwendet müssen Sie nicht die DDX-/DDV-Funktionen mit Windows Forms-Steuerelemente verwenden. Sie können stattdessen fügen Sie Code für den Zugriff auf die Eigenschaften des verwalteten Steuerelements in der `DoDataExchange` Methode der Klasse Dialogfeld (oder Ansicht), wie im folgenden Beispiel gezeigt.

Das folgende Beispiel zeigt, wie eine systemeigene C++-Zeichenfolge in ein Benutzersteuerelement .NET gebunden wird.

## <a name="example"></a>Beispiel

Im folgenden ist ein Beispiel der DDX-/DDV-Datenbindung einer MFC-Zeichenfolge `m_str` mit der benutzerdefinierten `NameText` Eigenschaft eines Steuerelements .NET.

Das Steuerelement wird erstellt, wenn [CDialog::](../mfc/reference/cdialog-class.md#oninitdialog) Aufrufe `CMyDlg::DoDataExchange` zum ersten Mal also keinen Code, der auf verweist `m_UserControl` müssen stammen, nachdem die `DDX_ManagedControl` aufrufen.

Sie können diesen Code implementieren, in den MFC01-Anwendung, die Sie erstellt, in haben [Vorgehensweise: Erstellen des Benutzersteuerelements und Hosten in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

Platzieren Sie den folgenden Code in der Deklaration der CMFC01Dlg:

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example"></a>Beispiel

Platzieren Sie den folgenden Code in der Implementierung von CMFC01Dlg:

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

Nun fügen wir die Handlermethode für einen Klick auf "OK". Klicken Sie auf die **Ressourcenansicht** Registerkarte. Doppelklicken Sie in der Ressourcenansicht auf `IDD_MFC01_DIALOG`. Die Dialogressource wird in Ressourcen-Editor angezeigt. Klicken Sie dann Doppelklicken auf die Schaltfläche "OK"...

Definieren Sie wie folgt des Handlers.

```
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example"></a>Beispiel

Und die Implementierung von "bool" CMFC01Dlg::OnInitDialog() fügen die folgende Zeile hinzu.

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

Sie können jetzt erstellen und Ausführen der Anwendung. Beachten Sie, dass es sich bei einem beliebigen Text in das Textfeld in einem Popup-Meldungsfeld angezeigt wird, wenn die Anwendung geschlossen wird.

## <a name="see-also"></a>Siehe auch

[CWinFormsControl-Klasse](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)