---
title: "Gewusst wie: Erstellen des Benutzersteuerelements und Hosten der MDI-Ansicht | Microsoft Docs"
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
  - "MFC [C++], Windows Forms-Steuerelemente"
  - "Windows Forms [C++], MFC-Unterstützung"
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# Gewusst wie: Erstellen des Benutzersteuerelements und Hosten der MDI-Ansicht
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In den folgenden Schritten wird das Erstellen eines .NET Framework\-Benutzersteuerelements und das Erstellen des Steuerelements in einer Steuerelementklassenbibliothek \(speziell in einem Projekt einer Windows\-Steuerelementbibliothek\) sowie das Kompilieren des Projekts in eine Assembly veranschaulicht.  Anschließend kann das Steuerelement aus einer MFC\-Anwendung heraus verwendet werden, die von [CView Class](../mfc/reference/cview-class.md) und [CWinFormsView Class](../mfc/reference/cwinformsview-class.md) abgeleitete Klassen verwendet.  
  
 Informationen, wie Sie ein Windows Forms\-Benutzersteuerelement und eine Steuerelementklassenbibliothek erstellen, finden Sie unter [Gewusst wie: Erstellen von Benutzersteuerelementen](../Topic/How%20to:%20Author%20Composite%20Controls.md).  
  
> [!NOTE]
>  In einigen Fällen verhalten sich Windows Forms\-Steuerelemente, z. B. ein Datenblattsteuerelement eines Drittanbieters, nicht zuverlässig, wenn sie in einer MFC\-Anwendung gehostet werden.  Um dies zu umgehen, wird empfohlen, ein Windows Forms\-Benutzersteuerelement in der MFC\-Anwendung und das Datenblattsteuerelement des Drittanbieters innerhalb des Benutzersteuerelements zu platzieren.  
  
 Voraussetzung für diese Prozedur ist, dass Sie ein Windows Forms\-Steuerelementbibliothek\-Projekt mit dem Namen WindowsFormsControlLibrary1 wie in der Vorgehensweise unter [Gewusst wie: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) erstellt haben.  
  
### So erstellen Sie die MFC\-Hostanwendung  
  
1.  Erstellen Sie ein MFC\-Anwendungsprojekt.  
  
     Klicken Sie im Menü **Datei** auf **Neu** und dann auf **Projekt**.  Wählen Sie im Ordner **Visual C\+\+** die Option **MFC\-Anwendung** aus.  
  
     Geben Sie im Feld **Name** die Zeichenfolge `MFC02` ein, und ändern Sie die Einstellung **Projektmappe** in **Hinzufügen**.  Klicken Sie auf **OK**.  
  
     Übernehmen Sie im **MFC\-Anwendungs\-Assistent** alle Standardeinstellungen, und klicken Sie dann auf **Fertig stellen**.  Dies erstellt eine MFC\-Anwendung mit einem MDI \(Multiple Document Interface\).  
  
2.  Konfigurieren Sie das Projekt für Common Language Runtime \(CLR\)\-Unterstützung.  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektknoten `MFC01`, und wählen Sie dann im Kontextmenü **Eigenschaften** aus.  Das Dialogfeld **Eigenschaftenseiten** wird angezeigt.  
  
     Wählen Sie unter **Konfigurationseigenschaften** die Option **Allgemein** aus.  Legen Sie unter **Projektstandards** die **Common Language Runtime\-Unterstützung** auf **Common Language Runtime\-Unterstützung \(\/clr\)** fest.  
  
     Erweitern Sie unter **Konfigurationseigenschaften** die Option **C\/C\+\+**, und klicken Sie anschließend auf den Knoten **Allgemein**.  Legen Sie **Debuginformationsformat** auf **Programmdatenbank \(\/Zi\)** fest.  
  
     Klicken Sie auf den Knoten **Codegenerierung**.  Legen Sie **Minimale Neuerstellung aktivieren** auf **Nein \(\/Gm\-\)** fest.  Legen Sie auch **Vollständige Laufzeitüberprüfungen** auf **Standard** fest.  
  
     Klicken Sie auf **OK**, um die Änderungen zu übernehmen.  
  
3.  Fügen Sie in der Datei "stdafx.h" die folgende Zeile hinzu.  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
4.  Fügen Sie dem .NET\-Steuerelement einen Verweis hinzu.  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektknoten `MFC02`, und wählen Sie **Hinzufügen** und **Verweise** aus.  Klicken Sie in der **Eigenschaftenseite** auf **Neuen Verweis hinzufügen**, wählen Sie WindowsFormsControlLibrary1 \(unter der Registerkarte **Projekte**\) aus, und klicken Sie auf **OK**.  Dies fügt einen Verweis in Form einer [\/FU](../build/reference/fu-name-forced-hash-using-file.md)\-Compileroption hinzu, damit das Programm kompiliert wird; außerdem wird "WindowsFormsControlLibrary1.dll" in das Projektverzeichnis `MFC02` kopiert, damit das Programm ausgeführt werden kann.  
  
5.  Suchen Sie in stdafx.h folgende Zeile:  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     Fügen Sie davor folgende Zeilen ein:  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  Ändern Sie die Ansichtsklasse so, dass sie von [CWinFormsView](../mfc/reference/cwinformsview-class.md) erbt.  
  
     Ersetzen Sie in MFC02View.h [CView](../mfc/reference/cview-class.md) durch [CWinFormsView](../mfc/reference/cwinformsview-class.md), sodass der Code folgendermaßen aussieht:  
  
    ```  
    class CMFC02View : public CWinFormsView  
    {  
    };  
    ```  
  
     Wenn Sie der MDI\-Anwendung weitere Ansichten hinzufügen möchten, müssen Sie für jede einzelne zu erstellende Ansicht [CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md) aufrufen.  
  
7.  Ändern Sie in der Datei MFC02View.cpp im IMPLEMENT\_DYNCREATE\-Makro und in der Meldungszuordnung CView in CWinFormsView um, und ersetzen Sie den vorhandenen leeren Konstruktor durch den folgenden:  
  
    ```  
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)  
  
    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)   
    {  
    }  
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)  
    //leave existing body as is  
    END_MESSAGE_MAP()  
    ```  
  
8.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf MFC02, und wählen Sie **Als Startprojekt festlegen**.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.  
  
## Siehe auch  
 [Hosten eines Windows Forms\-Benutzersteuerelements als MFC\-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)