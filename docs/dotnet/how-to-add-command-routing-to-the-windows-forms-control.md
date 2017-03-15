---
title: "Gewusst wie: Hinzuf&#252;gen von Befehlsrouting zum Windows Forms-Steuerelement | Microsoft Docs"
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
  - "Befehlsrouting [C++], hinzufügen zu Windows Forms-Steuerelementen"
  - "Windows Forms-Steuerelemente [C++], Befehl routing"
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Gewusst wie: Hinzuf&#252;gen von Befehlsrouting zum Windows Forms-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinFormsView](../mfc/reference/cwinformsview-class.md) Befehle und Update-Befehl UI Nachrichten weiterleitet, auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann.  
  
 Das Benutzersteuerelement verwendet [ICommandTarget:: Initialize](../Topic/ICommandTarget::Initialize.md) einen Verweis auf das Befehlsquellobjekt zu speichern `m_CmdSrc`, wie im folgenden Beispiel gezeigt. Um `ICommandTarget` zu verwenden, müssen Sie einen Verweis auf mfcmifc80.dll hinzufügen.  
  
 Durch `CWinFormsView` werden einige der allgemeinen MFC-Anzeigenbenachrichtigungen verarbeitet, indem diese an das verwaltete Benutzersteuerelement weitergeleitet werden. Diese Benachrichtigungen schließen die [OnInitialUpdate](../Topic/IView::OnInitialUpdate.md), [OnUpdate](../Topic/IView::OnUpdate.md) und [OnActivateView](../Topic/IView::OnActivateView.md) Methoden die [iView-Schnittstelle](../mfc/reference/iview-interface.md).  
  
 Vorausgesetzt, Sie haben zuvor [Gewusst wie: Erstellen des Benutzersteuerelements und Host in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) und [wie: Erstellen des Benutzersteuerelements und Host MDI View](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>So erstellen Sie die MFC-Hostanwendung  
  
1.  Öffnen Sie Windows Forms-Steuerelementbibliothek-in Erstellung [Gewusst wie: Erstellen des Benutzersteuerelements und Host in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
2.  Fügen Sie einen Verweis auf mfcmifc80.dll hinzu, indem Sie mit der rechten Maustaste des Projektknoten im **Projektmappen-Explorer**, wählen **Hinzufügen**, **Verweis**, und klicken Sie dann auf Microsoft Visual Studio 10.0\VC\atlmfc\lib navigieren.  
  
3.  Öffnen Sie UserControl1.Designer.cs, und fügen Sie die folgende using-Anweisung hinzu:  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  Ändern Sie außerdem in UserControl1.Designer.cs die folgende Zeile:  
  
    ```  
    partial class UserControl1  
    ```  
  
     in:  
  
    ```  
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget  
    ```  
  
5.  Fügen Sie diese Zeile als erste Zeile der Klassendefinition für `UserControl1` hinzu:  
  
    ```  
    private ICommandSource m_CmdSrc;  
    ```  
  
6.  Fügen Sie die folgenden Methodendefinitionen zu `UserControl1` hinzu (die ID des MFC-Steuerelements wird im nächsten Schritt erstellt):  
  
    ```  
    public void Initialize (ICommandSource cmdSrc)  
    {  
       m_CmdSrc = cmdSrc;  
       // need ID of control in MFC dialog and callback function   
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));  
    }  
  
    private void singleMenuHandler (uint cmdUI)  
    {  
       // User command handler code  
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");  
    }  
    ```  
  
7.  Öffnen Sie die MFC-Anwendung, die Sie erstellt, in haben [Gewusst wie: Erstellen des Benutzersteuerelements und Host MDI View](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
8.  Fügen Sie eine Menüoption hinzu, die `singleMenuHandler` aufruft.  
  
     Wechseln Sie zu **Ressourcenansicht** (STRG + UMSCHALT + E), erweitern Sie die **Menü** Ordner, und doppelklicken Sie dann auf **IDR_MFC02TYPE**. Der Menü-Editor wird angezeigt.  
  
     Fügen Sie eine Menüoption hinzu, am unteren Rand der **Ansicht** Menü. Beachten Sie die ID der Menüoption in der **Eigenschaften** Fenster. Speichern Sie die Datei.  
  
     In **Projektmappen-Explorer**, öffnen Sie die Datei Resource.h, kopieren Sie den ID-Wert für die soeben hinzugefügte Menüoption und fügen Sie den Wert als der erste Parameter für die `m_CmdSrc.AddCommandHandler` Aufrufen des C#-Projekts `Initialize` Methode (ersetzt `32771` bei Bedarf).  
  
9. Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Auf der **Debuggen** Menü klicken Sie auf **Starten ohne Debuggen**.  
  
     Wählen Sie die hinzugefügte Menüoption aus. Beachten Sie, dass die Methode in der DLL aufgerufen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [ICommandSource-Schnittstelle](../mfc/reference/icommandsource-interface.md)   
 [ICommandTarget-Schnittstelle](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)