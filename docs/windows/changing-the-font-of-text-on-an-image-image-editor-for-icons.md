---
title: "Changing the Font of Text on an Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonts, changing on an image"
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Changing the Font of Text on an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit der folgenden Prozedur wird die Vorgehensweise veranschaulicht:  
  
-   Hinzufügen von Text zu einem Symbol in einer Windows\-Anwendung  
  
-   Bearbeiten der Schriftart des Textes  
  
### So ändern Sie die Schriftart des Textes in einem Bild  
  
1.  Erstellen Sie eine C\+\+\-Windows Forms\-Anwendung.  Weitere Informationen finden Sie unter [Erstellen eines Windows\-Anwendungsprojekts](assetId:///b2f93fed-c635-4705-8d0e-cf079a264efa).  Die [Vorlage für Windows Forms\-Anwendung](assetId:///1babdebf-ab3f-4a64-a608-98499a5b9cea) fügt dem Projekt in der Standardeinstellung die Datei app.ico hinzu.  
  
2.  Doppelklicken Sie im Projektmappen\-Explorer auf die Datei app.ico.  Die [Bildbearbeitung](../mfc/image-editor-for-icons.md) wird geöffnet.  
  
3.  Wählen Sie im Menü **Bild** die Option **Extras** aus, und wählen Sie dann **Text\-Tool** aus.  Das [Dialogfeld "Text\-Tool"](../mfc/text-tool-dialog-box-image-editor-for-icons.md) wird angezeigt.  
  
4.  Geben Sie im Dialogfeld Text\-Tool im leeren Textbereich `C++` ein.  Dieser Text wird im Grafik\-Editor in Feld angezeigt, dessen Größe angepasst werden kann und das sich in der linken oberen Ecke von app.ico befindet.  
  
5.  Ziehen Sie im Grafik\-Editor das Feld mit der anpassbaren Größe in die Mitte von app.ico, damit der Text besser gelesen werden kann.  
  
6.  Klicken Sie im Dialogfeld Text\-Tool auf die Schaltfläche **Schriftart**.  Das [Dialogfeld "Schriftart für Texttool"](../mfc/text-tool-font-dialog-box-image-editor-for-icons.md) wird angezeigt.  
  
7.  Wählen Sie im Dialogfeld Schriftart für Texttool die Option **Times New Roman** aus der Liste der verfügbaren Schriftarten, die im Listenfeld **Schriftart** aufgeführt sind.  
  
8.  Wählen Sie aus der Liste der verfügbaren Schriftschnitte, die im Listenfeld **Schriftschnitt** aufgeführt sind, die Option **Fett** aus.  
  
9. Wählen Sie aus der Liste der verfügbaren Schriftgrade, die im Listenfeld **Schriftgrad** aufgelistet sind, die Option **10** aus.  
  
10. Klicken Sie auf die Schaltfläche **OK**.  Das Dialogfeld Schriftart für Texttool wird geschlossen, und die neuen Schriftarteinstellungen werden für den Text übernommen.  
  
11. Klicken Sie im Dialogfeld Text\-Tool auf die Schaltfläche **Schließen**.  Das Feld mit anpassbarer Größe um den Text wird im Grafik\-Editor ausgeblendet.  
  
## Siehe auch  
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Toolbar](../mfc/toolbar-image-editor-for-icons.md)