---
title: "Wortumbr&#252;che in RichEdit-Steuerelementen"
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
  - "Trennung von Wörtern in CRichEditCtrl"
  - "CRichEditCtrl-Klasse, Worttrennung in"
  - "Rich-Edit-Steuerelemente, Worttrennung in"
  - "Worttrennung"
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Wortumbr&#252;che in RichEdit-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Rich\-Edit\-Steuerelement \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) ruft eine Funktion auf, die eine "Wortumbruchprozedur", um Timeouts zwischen Wörtern zu suchen und bestimmen aufgerufen wird, wenn es Unterbrechungslinien kann.  Das Steuerelement verwendet diese Informationen, wenn es Zeilenumbruchvorgänge und wenn sie verarbeitet, STRG\+NACH\-LINKS und die STRG\+NACH\-RECHTS\-TASTEen\-Kombinationen ausführt.  Auf eine Anwendung kann Meldungen in ein Rich\-Edit\-Steuerelement senden, um die Standardwortbruchprozedur zu ersetzen, Wortbruchinformationen abzurufen, und festzustellen, welche Zeile ein angegebenes Zeichen liegt.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)