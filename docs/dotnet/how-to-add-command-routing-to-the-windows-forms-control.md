---
title: 'Vorgehensweise: Hinzufügen (Befehl) Befehlsrouting zum Windows Forms-Steuerelement | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c13b0bedf7c81431449aaed8d4fa8f067cdf3d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Gewusst wie: Hinzufügen von Befehlsrouting zum Windows Forms-Steuerelement
[CWinFormsView](../mfc/reference/cwinformsview-class.md) leitet Befehle und Update-befehlsmeldungen UI auf das Benutzersteuerelement, damit es MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann.  
  
 Das Benutzersteuerelement verwendet [ICommandTarget:: Initialize](../mfc/reference/icommandtarget-interface.md#initialize) zum Speichern eines Verweis auf das Befehlsquellobjekt in `m_CmdSrc`, wie im folgenden Beispiel gezeigt. Um `ICommandTarget` zu verwenden, müssen Sie einen Verweis auf mfcmifc80.dll hinzufügen.  
  
 Durch `CWinFormsView` werden einige der allgemeinen MFC-Anzeigenbenachrichtigungen verarbeitet, indem diese an das verwaltete Benutzersteuerelement weitergeleitet werden. Diese Benachrichtigungen umfassen die [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate), [OnUpdate](../mfc/reference/iview-interface.md#onupdate) und [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) Methoden.  
  
 In diesem Thema wird vorausgesetzt, Sie haben zuvor abgeschlossen [Vorgehensweise: Erstellen des Benutzersteuerelements und Host in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) und [Vorgehensweise: Erstellen des Benutzersteuerelements und MDI Hostansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>So erstellen Sie die MFC-Hostanwendung  
  
1.  Öffnen Sie Windows Forms-Steuerelementbibliothek im erstellten [Vorgehensweise: Erstellen des Benutzersteuerelements und Host in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
2.  Fügen Sie einen Verweis auf mfcmifc80.dll hinzu, indem Sie mit der rechten Maustaste des Projektknoten im **Projektmappen-Explorer**auswählen **hinzufügen**, **Verweis**, und klicken Sie dann auf Durchsuchen. Microsoft Visual Studio 10.0\VC\atlmfc\lib.  
  
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
  
7.  Öffnen Sie die MFC-Anwendung, die Sie erstellt, im haben [Vorgehensweise: Erstellen des Benutzersteuerelements und MDI Hostansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
8.  Fügen Sie eine Menüoption hinzu, die `singleMenuHandler` aufruft.  
  
     Wechseln Sie zu **Ressourcenansicht** (STRG + UMSCHALT + E), erweitern Sie die **Menü** Ordner, und doppelklicken Sie dann auf **IDR_MFC02TYPE**. Der Menü-Editor wird angezeigt.  
  
     Fügen Sie eine Menüoption am unteren Rand der **Ansicht** Menü. Beachten Sie die ID der Menüoption im die **Eigenschaften** Fenster. Speichern Sie die Datei.  
  
     In **Projektmappen-Explorer**Resource.h-Datei zu öffnen, kopieren Sie den ID-Wert für die soeben hinzugefügte Menüoption, und fügen Sie diesen Wert als erster Parameter an die `m_CmdSrc.AddCommandHandler` rufen Sie in der C#-Projekts `Initialize` Methode ( Ersetzen`32771` bei Bedarf).  
  
9. Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Auf der **Debuggen** Menü klicken Sie auf **Starten ohne Debuggen**.  
  
     Wählen Sie die hinzugefügte Menüoption aus. Beachten Sie, dass die Methode in der DLL aufgerufen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [ICommandSource-Schnittstelle](../mfc/reference/icommandsource-interface.md)   
 [ICommandTarget-Schnittstelle](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](http://msdn.microsoft.com/Library/22096734-e074-4aca-8523-4b15590109f9)