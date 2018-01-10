---
title: Umschalten zwischen Dialogfeld-Steuerelemente und Code | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog editor, accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog editor, switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81f8ea53cf6c4428913ce7ebfa4183c135208024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="switching-between-dialog-box-controls-and-code"></a>Umschalten zwischen Dialogfeld-Steuerelementen und Code
In MFC-Anwendungen Doppelklicken Sie auf Dialogfeld-Steuerelemente Codeprobleme Handler springen soll, oder schnell Stub Handlerfunktionen erstellen.  
  
 Mit einem Steuerelement ausgewählt ist, klicken Sie auf die **Steuerelementereignisse** Schaltfläche oder die **Nachrichten** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) eine vollständige Liste der Windows-Nachrichten und Ereignisse anzeigen für das ausgewählte Element verfügbar. Wählen Sie aus der Liste zu erstellen oder Bearbeiten von Handlerfunktionen verknüpft.  
  
### <a name="to-jump-to-code-from-the-dialog-editor"></a>Springen zu Code aus dem Dialog-editor  
  
1.  Doppelklicken Sie auf ein Steuerelement in das Dialogfeld, um die Deklaration für die zuletzt implementierten Meldungsbehandlung-Funktion zu wechseln. (Für ATL-basierten Dialogfeldklassen springen Sie immer die Definition des Konstruktors.)  
  
### <a name="to-view-events-for-a-control"></a>So zeigen Sie Ereignisse für ein Steuerelement an  
  
1.  Mit einem Steuerelement ausgewählt ist, klicken Sie auf die **Steuerelementereignisse** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).  
  
    > [!NOTE]
    >  Klicken auf die **Steuerelementereignisse** Schaltfläche, wenn die *Dialogfeld* verfügt über eine Liste aller Steuerelemente, den Fokus verfügbar macht, im Dialogfeld, die Sie erweitern können, um die Ereignisse für die einzelnen Steuerelemente zu bearbeiten.  
  
     Wenn ein einzelnes Steuerelement im Dialogfeld den Fokus besitzt, können Sie Maustaste und wählen **Ereignishandler hinzufügen** aus dem Kontextmenü. Dadurch können Sie die Klasse an, die der Handler hinzugefügt wird. Weitere Informationen finden Sie unter [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md).  
  
### <a name="to-view-messages-for-a-dialog-box"></a>Zum Anzeigen von Nachrichten für eine (Dialogfeld)  
  
1.  Aktivieren Sie das Dialogfeld, und klicken Sie auf die **Nachrichten** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Dialog-Editor](../windows/dialog-editor.md)

