---
title: "&#220;berschreiben einer virtuellen Funktion (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.virtualfunc.override"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Basisklassen, Überschreiben virtueller Funktionen in"
  - "Eigenschaftenfenster, Überschreiben virtueller Funktionen in"
  - "Virtuelle Funktionen, Überschreiben"
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;berschreiben einer virtuellen Funktion (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können virtuelle Funktionen, die über das [Eigenschaftenfenster](../Topic/Properties%20Window.md) von Visual Studio in einer Basisklasse definiert werden, überschreiben.  
  
### So überschreiben Sie eine virtuelle Funktion im Eigenschaftenfenster  
  
1.  Klicken Sie in der Klassenansicht auf die Klasse.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Überschreibungen**.  
  
    > [!NOTE]
    >  Die Schaltfläche **Überschreibungen** ist verfügbar, wenn Sie entweder den Klassennamen in der Klassenansicht markieren oder wenn Sie auf eine beliebige Stelle im Quellcodefenster klicken.  
  
     In der linken Spalte sind die virtuellen Funktionen aufgeführt.  Erscheint der Name einer virtuellen Funktion außerdem in der rechten Spalte, wurde bereits eine Überschreibung implementiert.  
  
3.  Wenn die Funktion keine Überschreibung enthält, klicken Sie auf die Zelle in der rechten Spalte des Eigenschaftenfensters, um den von der Funktionsüberschreibung vorgeschlagenen Namen als \<add\>*FuncName* anzuzeigen.  
  
4.  Klicken Sie auf den vorgeschlagenen Namen, um der Funktion Stubcode hinzuzufügen.  
  
5.  Um eine Überschreibungsfunktion zu bearbeiten, doppelklicken Sie in der Klassenansicht auf den Funktionsnamen und bearbeiten den Code im Quellcodefenster.  
  
 Um eine Überschreibung zu entfernen, klicken Sie in der rechten Spalte auf den Namen der Überschreibungsfunktion und wählen \<delete\>*FuncName*.  Der Funktionscode wird auskommentiert.  
  
## Siehe auch  
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC\-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../ide/navigating-the-class-structure-visual-cpp.md)