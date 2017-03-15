---
title: "Gewusst wie: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld | Microsoft Docs"
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
  - "MFC [C++], Hosten eines Windows Forms-Steuerelements"
  - "Windows Forms [C++], MFC-Unterstützung"
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# Gewusst wie: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei den Schritten in diesem Artikel wird angenommen, dass Sie ein dialogfeldbasiertes \([CDialog Class](../mfc/reference/cdialog-class.md)\) Microsoft Foundation Classes \(MFC\)\-Projekt erstellen. Sie können jedoch auch einem vorhandenen MFC\-Dialogfeld Unterstützung für ein Windows Forms\-Steuerelement hinzufügen.  
  
### So erstellen Sie das .NET\-Benutzersteuerelement  
  
1.  Erstellen Sie ein Steuerelement\-Bibliotheksprojekt für Visual C\# Windows Forms mit der Bezeichnung `WindowsFormsControlLibrary1`.  
  
     Klicken Sie im Menü **Datei** auf **Neu** und anschließend auf **Projekt**.  Wählen Sie im Ordner **Visual C\#** die Option **Windows Forms\-Steuerelementbibliothek** aus.  
  
     Akzeptieren Sie den `WindowsFormsControlLibrary1`\-Projektnamen durch Klicken auf **OK**.  
  
     Standardmäßig lautet der Name des .NET\-Steuerelements `UserControl1`.  
  
2.  Fügen Sie `UserControl1` untergeordnete Steuerelemente hinzu.  
  
     Öffnen Sie in der **Toolbox** die Liste **Alle Windows Forms**.  Ziehen Sie ein Steuerelement vom Typ **Schaltfläche** auf die `UserControl1`\-Entwurfsoberfläche.  
  
     Fügen Sie auch ein Steuerelement vom Typ **TextBox** hinzu.  
  
3.  Doppelklicken Sie im **Projektmappen\-Explorer** auf **UserControl1.Designer.cs**, um die Datei zur Bearbeitung zu öffnen.  Ändern Sie die Deklarationen des Textfelds und der Schaltfläche von `private` in `public`.  
  
4.  Erstellen Sie das Projekt.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
### So erstellen Sie die MFC\-Hostanwendung  
  
1.  Erstellen Sie ein MFC\-Anwendungsprojekt.  
  
     Klicken Sie im Menü **Datei** auf **Neu** und anschließend auf **Projekt**.  Wählen Sie im Ordner **Visual C\+\+** die Option **MFC\-Anwendung** aus.  
  
     Geben Sie im Feld **Name** den Text `MFC01` ein.  Ändern Sie die Projektmappeneinstellung in **Hinzufügen**.  Klicken Sie auf **OK**.  
  
     Wählen Sie im **MFC\-Anwendungs\-Assistenten** für den Anwendungstyp **Auf Dialogfeldern basierend** aus.  Akzeptieren Sie die restlichen Standardeinstellungen, und klicken Sie auf **Fertig stellen**.  Dadurch wird eine MFC\-Anwendung erstellt, die über ein MFC\-Dialogfeld verfügt.  
  
2.  Fügen Sie dem MFC\-Dialogfeld ein Platzhaltersteuerelement hinzu.  
  
     Klicken Sie im Menü **Ansicht** auf **Ressourcenansicht**.  Erweitern Sie in **Ressourcenansicht** den Ordner **Dialogfeld**, und doppelklicken Sie auf `IDD_MFC01_DIALOG`.  Die Dialogressource wird in **Ressourcen\-Editor** angezeigt.  
  
     Öffnen Sie in der **Toolbox** die Liste **Dialog\-Editor**.  Ziehen Sie das Steuerelement **Statischer Text** auf die Dialogressource.  Das Steuerelement **Statischer Text** dient als Platzhalter für das .NET Windows Forms\-Steuerelement.  Passen Sie die Größe des Steuerelements an, sodass sie mit der Größe des Windows Forms\-Steuerelements übereinstimmt.  
  
     Ändern Sie im Fenster **Eigenschaften** die **ID** des Steuerelements **Statischer Text** in `IDC_CTRL1`, und ändern Sie den Wert der **TabStop**\-Eigenschaft in **True**.  
  
3.  Konfigurieren Sie das Projekt für Common Language Runtime \(CLR\)\-Unterstützung.  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den MFC01\-Projektknoten, und klicken Sie anschließend auf **Eigenschaften**.  
  
     Wählen Sie im Dialogfeld **Eigenschaftenseiten** unter **Konfigurationseigenschaften** die Kategorie **Allgemein** aus.  Legen Sie im Abschnitt **Projektstandards** die **Common Language Runtime\-Unterstützung** auf **Common Language Runtime\-Unterstützung \(\/clr\)** fest.  
  
     Erweitern Sie unter **Konfigurationseigenschaften** die Option **C\/C\+\+**, und wählen Sie anschließend den Knoten **Allgemein** aus.  Legen Sie **Debuginformationsformat** auf **Programmdatenbank \(\/Zi\)** fest.  
  
     Wählen Sie den Knoten **Codegenerierung** aus.  Legen Sie **Minimale Neuerstellung aktivieren** auf **Nein \(\/Gm\-\)** fest.  Legen Sie auch **Vollständige Laufzeitüberprüfungen** auf **Standard** fest.  
  
     Klicken Sie auf **OK**, um die Änderungen zu übernehmen.  
  
4.  Fügen Sie dem .NET\-Steuerelement einen Verweis hinzu.  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den MFC01\-Projektknoten, und klicken Sie anschließend auf **Hinzufügen** und auf **Verweise**.  Klicken Sie auf der **Eigenschaftenseite** auf **Neuen Verweis hinzufügen**, wählen Sie **WindowsFormsControlLibrary1** \(unter der Registerkarte **Projekte**\) aus, und klicken Sie auf **OK**.  Dadurch wird ein Verweis in Form einer [\/FU](../build/reference/fu-name-forced-hash-using-file.md)\-Compileroption hinzugefügt, damit das Programm kompiliert wird.  Dabei wird auch eine Kopie von "WindowsFormsControlLibrary1.dll" im Projektordner "\\MFC01\\" abgelegt, damit das Programm ausgeführt wird.  
  
5.  Suchen Sie in "stdafx.h" die folgende Zeile:  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     Fügen Sie darüber die folgenden Zeilen ein:  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  Fügen Sie Code hinzu, um das verwaltete Steuerelement zu erstellen.  
  
     Deklarieren Sie zunächst das verwaltete Steuerelement.  Navigieren Sie in "MFC01Dlg.h" zur Deklaration der Dialogklasse, und fügen Sie im geschützten Bereich folgendermaßen einen Datenmember für das Benutzersteuerelement ein:  
  
    ```  
    class CMFC01Dlg : public CDialog  
    {  
       // ...  
       // Data member for the .NET User Control:  
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;  
    ```  
  
     Fügen Sie als Nächstes die Implementierung für das verwaltete Steuerelement ein.  Fügen Sie in "MFC01Dlg.cpp" in der vom MFC\-Anwendungs\-Assistenten generierten Dialogfeldüberschreibung von `CMFC01Dlg::DoDataExchange` \(nicht `CAboutDlg::DoDataExchange`, das in der gleichen Datei enthalten ist\) den folgenden Code hinzu, um das verwaltete Steuerelement zu erstellen und es dem statischen Platzhalter "IDC\_CTRL1" zuzuordnen:  
  
    ```  
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
    {  
       CDialog::DoDataExchange(pDX);  
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);  
    }  
    ```  
  
7.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **MFC01**, und klicken Sie anschließend auf **Als Startprojekt festlegen**.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.  Im MFC\-Dialogfeld wird das Windows Forms\-Steuerelement angezeigt.  
  
## Siehe auch  
 [Hosten eines Windows Form\-Benutzersteuerelements in einem MFC\-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)