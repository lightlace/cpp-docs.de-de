---
title: 'Gewusst wie: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
ms.openlocfilehash: ccb7219b9c7b3a64da61a77097b147424a92a701
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649994"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>Gewusst wie: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld

Die Schritte in diesem Artikel wird davon ausgegangen, dass Sie ein dialogfeldbasiertes erstellen ([CDialog-Klasse](../mfc/reference/cdialog-class.md)) Microsoft Foundation Classes (MFC)-Projekt, aber Sie können auch Unterstützung für Hinzufügen eines Windows Forms-Steuerelements einem vorhandenen MFC-Dialogfeld.

### <a name="to-create-the-net-user-control"></a>So erstellen Sie das .NET-Benutzersteuerelement

1. Erstellen Sie ein Visual c# Windows Forms-Steuerelementbibliothek-Projekt mit dem Namen `WindowsFormsControlLibrary1`.

   Klicken Sie im Menü **Datei** auf **Neu** und anschließend auf **Projekt**. In der **Visual C#-** Ordner **Windows Forms-Steuerelementbibliothek**.

   Akzeptieren Sie die `WindowsFormsControlLibrary1` -Projektnamen durch Klicken auf **OK**.

   Standardmäßig lautet der Name des .NET-Steuerelements `UserControl1`.

1. Fügen Sie `UserControl1` untergeordnete Steuerelemente hinzu.

   In der **Toolbox**öffnen die **alle Windows Forms** Liste. Ziehen Sie eine **Schaltfläche** die Steuerung an die `UserControl1` Entwurfsoberfläche.

   Hinzufügen einer **Textfeld** Steuerelement.

1. In **Projektmappen-Explorer**, doppelklicken Sie auf **UserControl1.Designer.cs** um ihn zur Bearbeitung zu öffnen. Ändern Sie die Deklarationen des Textfelds und der Schaltfläche von `private` in `public`.

1. Erstellen Sie das Projekt.

   Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

### <a name="to-create-the-mfc-host-application"></a>So erstellen Sie die MFC-Hostanwendung

1. Erstellen Sie ein MFC-Anwendungsprojekt.

   Klicken Sie im Menü **Datei** auf **Neu** und anschließend auf **Projekt**. In der **Visual C++** Ordner **MFC-Anwendung**.

   Geben Sie im Feld **Name** `MFC01`ein. Ändern Sie die projektmappeneinstellung in **zu Projektmappe hinzufügen**. Klicken Sie auf **OK**.

   In der **MFS-Anwendungsassistenten**, wählen Sie für den Anwendungstyp **auf Dialogfeldern basierend**. Akzeptieren Sie die restlichen Standardeinstellungen, und klicken Sie auf **Fertig stellen**. Dadurch wird eine MFC-Anwendung erstellt, die über ein MFC-Dialogfeld verfügt.

1. Fügen Sie dem MFC-Dialogfeld ein Platzhaltersteuerelement hinzu.

   Auf der **Ansicht** Menü klicken Sie auf **Ressourcenansicht**. In **Ressourcenansicht**, erweitern Sie die **Dialogfeld** Ordner und doppelklicken Sie auf `IDD_MFC01_DIALOG`. Die Dialogressource wird in **Ressourcen-Editor-**.

   In der **Toolbox**öffnen die **Dialog-Editor** Liste. Ziehen Sie eine **statischer Text** Steuerelement auf die Dialogressource. Die **statischer Text** Steuerelement dient als Platzhalter für das .NET Windows Forms-Steuerelement. Passen Sie die Größe des Steuerelements an, sodass sie mit der Größe des Windows Forms-Steuerelements übereinstimmt.

   In der **Eigenschaften** Ändern der **ID** von der **statischer Text** die Steuerung an `IDC_CTRL1` , und ändern Sie die **TabStop** Eigenschaft **"True"**.

1. Konfigurieren Sie das Projekt für Common Language Runtime (CLR)-Unterstützung.

   In **Projektmappen-Explorer**mit der rechten Maustaste auf den MFC01-Projektknoten, und klicken Sie dann auf **Eigenschaften**.

   In der **Eigenschaftenseiten** Dialogfeld **Konfigurationseigenschaften**Option **allgemeine**. In der **Projektstandards** legen **Common Language Runtime-Unterstützung** zu **Common Language Runtime-Unterstützung (/ Clr)**.

   Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie **C/C++-** , und wählen Sie die **allgemeine** Knoten. Legen Sie **Debuginformationsformat** zu **Programmdatenbank (/ Zi)**.

   Wählen Sie die **Codegenerierung** Knoten. Legen Sie **minimale Neuerstellung aktivieren** zu **No (/ GM-)**. Legen Sie auch **vollständige Laufzeitüberprüfungen** zu **Standard**.

   Klicken Sie auf **OK** um die Änderungen zu übernehmen.

1. Fügen Sie dem .NET-Steuerelement einen Verweis hinzu.

   In **Projektmappen-Explorer**mit der rechten Maustaste auf den MFC01-Projektknoten, und klicken Sie dann auf **hinzufügen**, **Verweise**. Auf der **Eigenschaftenseite**, klicken Sie auf **neuen Verweis hinzufügen**Option **WindowsFormsControlLibrary1** (unter der **Projekte** Registerkarte), und klicken Sie auf **OK**. Dies fügt einen Verweis in Form einer [/FU](../build/reference/fu-name-forced-hash-using-file.md) -Compileroption, damit das Programm kompiliert wird. Dabei wird auch eine Kopie von "WindowsFormsControlLibrary1.dll" im Projektordner "\MFC01\" abgelegt, damit das Programm ausgeführt wird.

1. Suchen Sie in "stdafx.h" die folgende Zeile:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   Fügen Sie darüber die folgenden Zeilen ein:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Fügen Sie Code hinzu, um das verwaltete Steuerelement zu erstellen.

   Deklarieren Sie zunächst das verwaltete Steuerelement. Navigieren Sie in "MFC01Dlg.h" zur Deklaration der Dialogklasse, und fügen Sie im geschützten Bereich folgendermaßen einen Datenmember für das Benutzersteuerelement ein:

    ```
    class CMFC01Dlg : public CDialog
    {
       // ...
       // Data member for the .NET User Control:
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;
    ```

   Fügen Sie als Nächstes die Implementierung für das verwaltete Steuerelement ein. Fügen Sie in "MFC01Dlg.cpp" in der vom MFC-Anwendungs-Assistenten generierten Dialogfeldüberschreibung von `CMFC01Dlg::DoDataExchange` (nicht `CAboutDlg::DoDataExchange`, das in der gleichen Datei enthalten ist) den folgenden Code hinzu, um das verwaltete Steuerelement zu erstellen und es dem statischen Platzhalter "IDC_CTRL1" zuzuordnen:

    ```
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
    {
       CDialog::DoDataExchange(pDX);
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);
    }
    ```

1. Erstellen Sie das Projekt, und führen Sie es aus.

   In **Projektmappen-Explorer**, mit der rechten Maustaste **MFC01** , und klicken Sie dann auf **als Startprojekt festlegen**.

   Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

   Auf der **Debuggen** Menü klicken Sie auf **Starten ohne debugging**. Im MFC-Dialogfeld wird das Windows Forms-Steuerelement angezeigt.

## <a name="see-also"></a>Siehe auch

[Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)