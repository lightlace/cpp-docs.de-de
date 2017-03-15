---
title: "Ereignishandler-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.eventhandler.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ereignishandler-Assistent [C++]"
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ereignishandler-Assistent
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Assistent fügt einer ausgewählten Klasse einen Ereignishandler für ein Dialogfeld\-Steuerelement hinzu.  Wenn Sie einen Ereignishandler mithilfe des [Eigenschaftenfensters](../Topic/Properties%20Window.md) hinzufügen, können Sie ihn nur der Klasse hinzufügen, durch die das Dialogfeld implementiert wird.  Weitere Informationen finden Sie unter [Hinzufügen von Ereignishandlern für Dialogfeld\-Steuerelemente](../mfc/adding-event-handlers-for-dialog-box-controls.md).  
  
 **Befehlsname**  
 Kennzeichnet das ausgewählte Steuerelement, dem der Ereignishandler hinzugefügt wird.  Dieses Feld ist nicht verfügbar.  
  
 **Meldungstyp**  
 Zeigt die Liste der aktuell für das markierte Steuerelement verfügbaren Meldungshandler an.  
  
 **Funktionshandlername**  
 Zeigt den Namen der Funktion an, die zur Ereignisbehandlung hinzugefügt wird.  Der Name setzt sich standardmäßig aus einem vorangestellten "On" sowie dem Meldungstyp und dem Befehl zusammen.  Für die Schaltfläche mit dem Namen `IDC_BUTTON1` zeigt der Meldungstyp `BN_CLICKED` beispielsweise den Funktionshandlernamen `OnBnClickedButton1` an.  
  
 **Klassenliste**  
 Zeigt die verfügbaren Klassen an, denen ein Ereignishandler hinzugefügt werden kann.  Die Klasse für das ausgewählte Dialogfeld wird rot angezeigt.  
  
 **Handlerbeschreibung**  
 Liefert eine Beschreibung des im Feld **Meldungstyp** markierten Elements.  Dieses Feld ist nicht verfügbar.  
  
 **Hinzufügen und bearbeiten**  
 Fügt der ausgewählten Klasse oder dem ausgewählten Objekt den Meldungshandler hinzu und öffnet dann den Text\-Editor für die Funktion, sodass Sie den Handlercode für die Steuerelementbenachrichtigung eingeben können.  
  
 **Code bearbeiten**  
 Öffnet den Text\-Editor für die ausgewählte, bereits vorhandene Funktion, sodass Sie den Handlercode für die Steuerelementbenachrichtigung hinzufügen oder bearbeiten können.  
  
## Siehe auch  
 [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md)