---
title: "Deklarieren einer auf der neuen Steuerelementklasse basierenden Variablen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes.control.variable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], Deklarieren von Variablen basierend auf"
  - "Steuerelementklassen, Variablen"
  - "Variablen, Steuerelementklassen"
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Deklarieren einer auf der neuen Steuerelementklasse basierenden Variablen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie eine MFC\-Steuerelementklasse erstellt haben, können Sie auf deren Grundlage eine Variable deklarieren.  Um einen Kontext für die neue Variable zur Verfügung zu stellen, müssen Sie den Dialog\-Editor öffnen und das Dialogfeld bearbeiten, in dem Sie das wiederverwendbare Steuerelement verwenden möchten.  Darüber hinaus muss bereits eine Klasse mit dem Dialogfeld verbunden sein.  Weitere Informationen zur Verwendung des Dialog\-Editors finden Sie unter [Dialog\-Editor](../../mfc/dialog-editor.md).  
  
### So deklarieren Sie eine Variable auf der Basis der wiederverwendbaren Klasse  
  
1.  Während Sie das Dialogfeld bearbeiten, ziehen Sie ein Steuerelement, dessen Typ dem Typ der Basisklasse des neuen Steuerelements entspricht, von der Steuerelement\-Symbolleiste in das Dialogfeld.  
  
2.  Positionieren Sie den Mauszeiger über dem abgelegten Steuerelement.  
  
3.  Während Sie die STRG\-TASTE gedrückt halten, doppelklicken Sie auf das Steuerelement.  
  
     Das Dialogfeld [Membervariable hinzufügen](../../ide/add-member-variable-wizard.md) wird angezeigt.  
  
4.  Wählen Sie im Feld **Zugriff** die richtige Zugriffsart für das Steuerelement aus.  
  
5.  Klicken Sie auf das Kontrollkästchen **Steuerelementvariable**.  
  
6.  Geben Sie im Feld **Variablenname** einen Namen ein.  
  
7.  Klicken Sie unter **Kategorie** auf **Steuerelement**.  
  
8.  Wählen Sie in der Liste **Steuerelement\-ID** das hinzugefügte Steuerelement aus.  In der Liste **Variablentyp** sollte der richtige Variablentyp und im Feld **Steuerelementtyp** der richtige Steuerelementtyp enthalten sein.  
  
9. Fügen Sie im Feld **Anmerkung** eine Anmerkung hinzu, die im Code angezeigt werden soll.  
  
10. Klicken Sie auf **OK**.  
  
## Siehe auch  
 [Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC\-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)