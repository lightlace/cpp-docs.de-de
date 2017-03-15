---
title: "Position eines Elements im Struktursteuerelement | Microsoft Docs"
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
  - "CTreeCtrl-Klasse, Elementposition"
  - "Elementposition in Struktursteuerelementen"
  - "Position, CTreeCtrl-Elemente"
  - "Struktursteuerelemente, Elementposition"
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Position eines Elements im Struktursteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Anfangsposition eines Elements wird festgelegt, wenn das Element wird hinzugefügt Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) mithilfe der `InsertItem`\-Memberfunktion verwendet.  Der Memberfunktionsaufruf gibt das Handle des übergeordneten Elements und das Handle des Elements an, nachdem soll das neue Element eingefügt werden.  Das zweite Handle muss jedes ein untergeordnetes Element des dem angegebenen übergeordneten oder dieser Werte identifizieren: `TVI_FIRST`, `TVI_LAST` oder `TVI_SORT`.  
  
 Wenn `TVI_FIRST` oder `TVI_LAST` angegeben wird, platziert das Struktursteuerelement das neue Element am Anfang oder Ende der angegebenen Liste des übergeordneten Elements der untergeordneten Elemente.  Wenn `TVI_SORT` angegeben ist, fügt das Struktursteuerelement das neue Element in die Liste mit untergeordneten Elementen in alphabetischer Reihenfolge nach den Text der Elementbezeichnungen ein.  
  
 Sie können die Liste eines übergeordneten Elements der untergeordneten Elemente in die alphabetische Reihenfolge stellen, indem Sie die Memberfunktion [SortChildren](../Topic/CTreeCtrl::SortChildren.md) aufrufen.  Diese Funktion enthält einen Parameter, der angibt, dass alle Ebenen von untergeordneten Elementen, die vom angegebenen übergeordneten Element abgeleitet, in alphabetischer Reihenfolge sortiert werden.  
  
 Die Memberfunktion [SortChildrenCB](../Topic/CTreeCtrl::SortChildrenCB.md) ermöglicht die Sortierungsuntergeordneten gelöschte auf Grundlage Kriterien, die Sie definieren.  Wenn Sie diese Funktion aufrufen, geben Sie eine anwendungsdefinierte Rückruffunktion an, die das Struktursteuerelement aufrufen können, sobald die relative Position von zwei untergeordneten Elemente festgelegt werden muss.  Die Rückruffunktion empfängt zwei anwendungsdefinierte 32\-Bit\-Werte für Elemente, die verglichen werden und ein dritter 32\-Bit\-Wert, die Sie angeben, wenn Sie `SortChildrenCB` aufrufen.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)