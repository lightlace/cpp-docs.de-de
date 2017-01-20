---
title: "Beispiel: Anzeigen eines Dialogfelds mit einem Men&#252;befehl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dialogfelder, MFC"
  - "Beispiele [MFC], Dialogfelder"
  - "Menüelemente, Beispiele"
  - "MFC-Dialogfelder, Anzeigen"
  - "MFC-Dialogfelder, Beispiele"
  - "Modale Dialogfelder, Anzeigen"
  - "Nicht modale Dialogfelder, Anzeigen"
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Beispiel: Anzeigen eines Dialogfelds mit einem Men&#252;befehl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema enthält Prozeduren:  
  
-   Zeigen Sie ein modales Dialogfeld durch einen Menübefehl an.  
  
-   Zeigen Sie ein nicht modales Dialogfeld durch einen Menübefehl an.  
  
 Beide Beispielprozeduren sind für MFC\-Anwendungen und in einer Anwendung arbeiten, die Sie mit dem [MFC\-Anwendungs\-Assistent](../mfc/reference/mfc-application-wizard.md) erstellen.  
  
 Die Prozeduren verwenden die folgenden Namen und Werte:  
  
|Element|Name oder Wert|  
|-------------|--------------------|  
|Anwendung|DisplayDialog|  
|Menübefehl|Testbefehl auf Menü Ansicht; Befehls\-ID \= ID\_VIEW\_TEST|  
|Dialogfeld|Testdialogfeld; Klasse CTestDialog \=; Headerdatei \= TestDialog.h; Variable \= testdlg, ptestdlg|  
|Befehlshandler|OnViewTest|  
  
### So ein modales Dialogfeld anzeigen  
  
1.  Erstellen Sie den Menübefehl; finden Sie unter [Erstellen von Menüs oder von Menüelementen](../windows/creating-a-menu.md).  
  
2.  Stellen Sie das Dialogfeld erstellt; finden Sie unter [Starten des Dialog\-Editors](../mfc/creating-a-new-dialog-box.md).  
  
3.  Fügen Sie eine Klasse für das Dialogfeld hinzu.  Weitere Informationen finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md).  
  
4.  Wählen Sie im **Klassenansicht** die Dokumentklasse aus \(CDisplayDialogDoc\).  Im Fenster **Eigenschaften** klicken Sie auf die Schaltfläche **Ereignisse** .  Doppelklicken Sie auf die ID des Menübefehls \(ID\_VIEW\_TEST\) im linken Bereich des Fensters **Eigenschaften** und wählen Sie **Befehl** aus.  Klicken Sie im rechten Bereich auf den Pfeil nach unten und wählen Sie **\<Add\> OnViewTest** aus.  
  
     Wenn Sie dem Menübefehl zu den Mainframen einer MDI\-Anwendung hinzugefügt haben, wählen Sie die Anwendungsklasse \(CDisplayDialogApp\) aus.  
  
5.  Fügen Sie die folgende CDisplayDialogDoc.cpp include\-Anweisung \(oder CDisplayDialogApp.cpp\) nach vorhandenen Include\-Anweisungen hinzu:  
  
     [!CODE [NVC_MFCControlLadenDialog#42](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#42)]  
  
6.  Fügen Sie `OnViewTest` folgenden Code hinzu, um die Funktion zu implementieren:  
  
     [!CODE [NVC_MFCControlLadenDialog#43](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#43)]  
  
### Um ein nicht modales Dialogfeld anzeigen  
  
1.  Führen Sie die ersten vier Schritte, um ein modales Dialogfeld, außer Text anzuzeigen die Ansichtsklasse \(CDisplayDialogView\) in Schritt 4.  
  
2.  Bearbeiten DisplayDialogView.h:  
  
    -   Deklarieren Sie die Deklaration der Dialogklasse, die der ersten Klasse vor:  
  
         [!CODE [NVC_MFCControlLadenDialog#44](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#44)]  
  
    -   Deklarieren Sie einen Zeiger auf das Dialogfeld, nachdem dem öffentlichen Abschnitt der Attribute:  
  
         [!CODE [NVC_MFCControlLadenDialog#45](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#45)]  
  
3.  Bearbeiten DisplayDialogView.cpp:  
  
    -   Fügen Sie die folgende include\-Anweisung nach vorhandenen Include\-Anweisungen hinzu:  
  
         [!CODE [NVC_MFCControlLadenDialog#42](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#42)]  
  
    -   Fügen Sie dem Konstruktor folgenden Code hinzu:  
  
         [!CODE [NVC_MFCControlLadenDialog#46](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#46)]  
  
    -   Fügen Sie den folgenden Code dem Destruktor hinzu:  
  
         [!CODE [NVC_MFCControlLadenDialog#47](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#47)]  
  
    -   Fügen Sie `OnViewTest` folgenden Code hinzu, um die Funktion zu implementieren:  
  
         [!CODE [NVC_MFCControlLadenDialog#48](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#48)]  
  
 Außerdem finden Sie im folgenden Knowledge Base\-Artikel:  
  
-   Q251059: HOWTO: Geben Sie einen eigenen Fensterklassen\-Namen für ein MFC\-Dialogfeld an  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Modale und nicht modale Dialogfelder](../mfc/modal-and-modeless-dialog-boxes.md)