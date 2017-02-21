---
title: "Adding Controls to a Dialog Causes the Dialog to No Longer Function | Microsoft Docs"
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
  - "controls [C++], troubleshooting"
  - "common controls, troubleshooting"
  - "troubleshooting controls"
  - "dialog boxes, troubleshooting"
  - "dialog box controls, troubleshooting"
  - "InitCommonControls"
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Adding Controls to a Dialog Causes the Dialog to No Longer Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem einem Dialogfeld ein allgemeines oder RichEdit\-Steuerelement hinzugefügt wurde, wird das Steuerelement oder das Dialogfeld selbst beim Testen des Dialogfelds nicht angezeigt.  
  
 **Nachstellung des Problems**  
  
1.  Erstellen Sie ein Win32\-Projekt, und ändern Sie die Anwendungseinstellungen, um eine Windows\-Anwendung \(keine Konsolenanwendung\) zu erstellen.  
  
2.  Doppelklicken Sie in der [Ressourcenansicht](../windows/resource-view-window.md) auf die RC\-Datei.  
  
3.  Doppelklicken Sie unter der Dialogfeldoption auf das Feld **Info**.  
  
4.  Fügen Sie dem Dialogfeld ein **IP\-Adressensteuerelement** hinzu.  
  
5.  Speichern Sie, und wählen Sie **Alles neu erstellen**.  
  
6.  Führen Sie das Programm aus.  
  
7.  Klicken Sie im Menü **Hilfe** des Dialogfelds auf den Befehl **Info**. Es wird kein Dialogfeld angezeigt.  
  
 **Problemursache**  
  
 Code wird dem Projekt derzeit vom Dialog\-Editor nicht automatisch hinzugefügt, wenn Sie die folgenden allgemeinen oder RichEdit\-Steuerelemente mittels Drag & Drop in einem Dialogfeld ablegen.  Darüber hinaus wird in Visual Studio keine Fehler\- oder Warnmeldung ausgegeben, wenn dieses Problem auftritt.  Daher müssen Sie Code für das Steuerelement manuell hinzufügen.  
  
||||  
|-|-|-|  
|Schiebereglersteuerung|Strukturansicht|Datums\-\/Zeitauswahl|  
|Drehfeld\-Steuerelement|Registersteuerelement|Monatskalender|  
|Statuskontrolle|Animationssteuerung|IP\-Adressensteuerelement|  
|Abkürzungstaste\-Steuerelement|RichEdit\-Steuerelement|Erweitertes Kombinationsfeld|  
|Listensteuerelement|Rich\-Edit\-2.0\-Steuerelement|Benutzerdefiniertes Steuerelement|  
  
## Korrektur für allgemeine Steuerelemente  
 Damit allgemeine Steuerelemente in einem Dialogfeld verwendet werden können, muss vor dem Erstellen des Dialogfelds [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) oder **AFXInitCommonControls** aufgerufen werden.  
  
## Korrektur für RichEdit\-Steuerelemente  
 Für RichEdit\-Steuerelemente muss **LoadLibrary** aufgerufen werden.  Weitere Informationen finden Sie unter [Verwenden des RichEdit 1.0\-Steuerelements mit MFC](../mfc/using-the-richedit-1-0-control-with-mfc.md), [About Rich Edit Controls](http://msdn.microsoft.com/library/windows/desktop/bb787873) im [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] sowie unter [Übersicht über das RichEdit\-Steuerelement](../mfc/overview-of-the-rich-edit-control.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Troubleshooting the Dialog Editor](../mfc/troubleshooting-the-dialog-editor.md)   
 [Dialog Editor](../mfc/dialog-editor.md)