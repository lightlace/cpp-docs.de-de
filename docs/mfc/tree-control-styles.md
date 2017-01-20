---
title: "Struktursteuerelementstile"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "TVS_SINGLEEXPAND"
  - "TVS_LINESATROOT"
  - "TVS_HASBUTTONS"
  - "TVS_NOTOOLTIPS"
  - "TVS_HASLINES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl-Klasse, Stile"
  - "Stile, CTreeCtrl"
  - "Stile, Struktursteuerelemente"
  - "Struktursteuerelemente, Stile"
  - "TVS_EDITLABELS"
  - "TVS_HASBUTTONS"
  - "TVS_HASLINES"
  - "TVS_LINESATROOT"
  - "TVS_NOTOOLTIPS"
  - "TVS_SINGLEEXPAND"
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Struktursteuerelementstile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Formate der Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) steuern Aspekte der Darstellung einer Strukturansicht.  Sie legen der ursprünglichen formatieren, sofern Sie die Strukturansicht erstellen.  Sie können die Stile abrufen und ändern, nachdem Sie das Struktursteuerelement erstellt haben, indem Sie die [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) und [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) verwenden Windows\-Funktionen und **GWL\_STYLE** für den `nIndex`\-Parameter angeben.  Eine vollständige Liste von Formaten, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Strukturansicht\-Steuerelement\-Fensterstile](http://msdn.microsoft.com/library/windows/desktop/bb760013).  
  
 Das **TVS\_HASLINES** Format erhöht die grafische Darstellung der Hierarchie einer Strukturansicht, indem Zeilen zeichnet, die untergeordnete Elemente zu den entsprechenden übergeordneten Element erstellen.  Dieses Format verknüpft Elemente nicht im Stamm der Hierarchie.  Hierzu, müssen Sie **TVS\_HASLINES** und **TVS\_LINESATROOT** Stile kombinieren.  
  
 Der Benutzer kann die Liste eines übergeordneten Elements der untergeordneten Elemente erweitern oder reduzieren, indem Sie auf das übergeordnete Element öffnen.  Eine Strukturansicht, das **TVS\_SINGLEEXPAND** Format hat, führt das Element, das ausgewählt werden, um sich selbst zu erweitern und das Element, das nicht aktiviert ist zu reduzieren.  Wenn die Maus z auf das ausgewählte Element verwendet wird und dieses Element geschlossen wird, wird es erweitert.  Wenn auf das ausgewählte Element einzel\-geklickt wird, wenn es geöffnet ist, wird sie reduziert.  
  
 Eine Strukturansicht, das **TVS\_HASBUTTONS** Format hat, eine Schaltfläche der linken Seite jedes übergeordneten Elements hinzu.  Der Benutzer kann auf die Schaltfläche klicken, um die untergeordneten Haltepunkte als Alternative zum Doppelklicken auf das übergeordnete Element zu erweitern oder zu reduzieren.  **TVS\_HASBUTTONS** fügt Schaltflächen nicht Elemente am Stamm der Hierarchie hinzu.  Hierzu, müssen Sie **TVS\_HASLINES**, **TVS\_LINESATROOT** und **TVS\_HASBUTTONS** kombinieren.  
  
 Das **TVS\_EDITLABELS** Format ermöglicht es, damit der Benutzer die Bezeichnungen von Strukturansicht\-Steuerelement\-Elementen bearbeitet.  Weitere Informationen über Bearbeitungsbezeichnungen, finden Sie unter [Strukturansicht\-Steuerelement\-Bezeichnungs\-Bearbeitung](../mfc/tree-control-label-editing.md) weiter unten in diesem Thema.  
  
 Das **TVS\_NOTOOLTIPS** Format deaktiviert die automatische QuickInfofunktion von Strukturansicht\-Steuerelementen.  Diese Funktion wird automatisch eine QuickInfo an und enthält den Titel des Elements unter dem Mauszeiger, wenn der gesamte Titel nicht gerade sichtbar ist.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)