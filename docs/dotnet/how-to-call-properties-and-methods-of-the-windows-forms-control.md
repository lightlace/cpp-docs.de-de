---
title: 'Vorgehensweise: Aufrufen von Ereignissen und Methoden des Windows Forms-Steuerelements'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
ms.openlocfilehash: 61b565839b3f3c24670819fdcf2dde558e3461ac
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743767"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>Vorgehensweise: Aufrufen von Ereignissen und Methoden des Windows Forms-Steuerelements

Da [CWinFormsView::](../mfc/reference/cwinformsview-class.md#getcontrol) gibt einen Zeiger auf <xref:System.Windows.Forms.Control?displayProperty=fullName>, und nicht auf einen Zeiger auf `WindowsControlLibrary1::UserControl1`, ist es ratsam, ein Mitglied des Steuerelementtyps Benutzer hinzufügen und initialisieren Sie es in [iView:: OnInitialUpdate ](../mfc/reference/iview-interface.md#oninitialupdate). Nachdem Sie die Methoden und Eigenschaften, die mit aufrufen können `m_ViewControl`.

In diesem Thema wird vorausgesetzt, Sie haben zuvor [Vorgehensweise: Erstellen des Benutzersteuerelements und Hosten in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) und [Vorgehensweise: Erstellen des Benutzersteuerelements und Hosten MDI-Ansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

### <a name="to-create-the-mfc-host-application"></a>So erstellen Sie die MFC-Hostanwendung

1. Öffnen Sie die MFC-Anwendung, die Sie erstellt, im haben [Vorgehensweise: Erstellen des Benutzersteuerelements und Hosten MDI-Ansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

1. Fügen Sie die folgende Zeile Abschnitt Öffentliche Außerkraftsetzungen der `CMFC02View` -Klassendeklaration in MFC02View.h.

   `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`

1. Fügen Sie eine Außerkraftsetzung für OnInitialupdate hinzu.

   Anzeigen der **Eigenschaften** Fenster (F4). In **Klassenansicht** (STRG + UMSCHALT + C), wählen Sie CMFC02View-Klasse. In der **Eigenschaften** Fenster, wählen Sie das Symbol für Außerkraftsetzungen. Scoll nach unten zu OnInitialUpdate. Klicken Sie auf die Dropdownliste aus, und wählen Sie \<hinzufügen >. In MFC02View.cpp. Stellen Sie sicher, dass der Text der Funktion OnInitialUpdate wie folgt:

    ```
    CWinFormsView::OnInitialUpdate();
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());
    m_ViewControl->textBox1->Text = gcnew System::String("hi");
    ```

1. Erstellen Sie das Projekt, und führen Sie es aus.

   Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

   Auf der **Debuggen** Menü klicken Sie auf **Starten ohne debugging**.

   Beachten Sie, dass das Textfeld jetzt initialisiert wird.

## <a name="see-also"></a>Siehe auch

[Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
