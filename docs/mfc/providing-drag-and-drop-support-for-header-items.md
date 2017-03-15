---
title: "Bereitstellen von Drag &amp; Drop-Unterst&#252;tzung f&#252;r Headerelemente | Microsoft Docs"
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
  - "CHeaderCtrl-Klasse, Drag & Drop-Unterstützung"
  - "HDN_-Benachrichtigungen"
  - "HDS_DRAGDROP-Stil"
  - "Headerelemente in Headersteuerelementen"
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Bereitstellen von Drag &amp; Drop-Unterst&#252;tzung f&#252;r Headerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um Drag & Drop\-Unterstützung für Kopfzeilenelemente bereitzustellen, geben Sie den `HDS_DRAGDROP` Format an.  Drag & Drop\-Unterstützung für Kopfzeilenelemente gibt der Benutzer die Möglichkeit, die Kopfzeilenelemente eines Header\-Steuerelements neu anzuordnen.  Das Standardverhalten bietet ein Ziehbild halbtransparentes des Kopfzeilenelements, das gezogen wird und eine visuelle Zähler der neuen Position angezeigt, wenn HeaderItem abgelegt wird.  
  
 Wie mit allgemeiner Drag & Drop\-Funktion, können Sie das Standard\-Drag & Drop\-Verhalten erweitern, indem Sie die **HDN\_BEGINDRAG** und **HDN\_ENDDRAG** Benachrichtigungen behandeln.  Sie können die Darstellung des Ziehbilds auch anpassen, indem Sie die [CHeaderCtrl::CreateDragImage](../Topic/CHeaderCtrl::CreateDragImage.md)\-Memberfunktion überschreiben.  
  
> [!NOTE]
>  Wenn Sie Drag & Drop\-Unterstützung für ein eingebettetes Header\-Steuerelement in einem Listensteuerelement bereitstellen, finden Sie im Abschnitt des erweiterten Stils im Thema [Ändern von Listensteuerelement\-Formaten](../mfc/changing-list-control-styles.md).  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)