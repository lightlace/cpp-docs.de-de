---
title: "Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen"
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
  - "catch-Blöcke, explizit Code löschen in"
  - "catch-Blöcke, Gemischt"
  - "Ausnahmebehandlung, MFC"
  - "Ausnahmebehandlung, Gemischte Sprache"
  - "Ausnahmeobjekte"
  - "Ausnahmeobjekte, Löschen"
  - "Ausnahmen, MFC-Makros und C++Schlüsselwörter"
  - "Beschädigung des Heap"
  - "Speicherverluste, Ausnahmeobjekt nicht gelöscht"
  - "Geschachtelte Catch-Blöcke"
  - "Geschachtelte Try-Blöcke"
  - "try-catch-Ausnahmebehandlung, Mischen von MFC-Makros und C++-Schlüsselwörtern"
  - "try-catch-Ausnahmebehandlung, Geschachtelte Try-Blöcke"
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden Überlegungen zum Schreiben von Code, der die MFC\-Ausnahmebehandlungsmakros und die C\+\+\-Ausnahmebehandlungsschlüsselworte verwendet.  
  
 Dieser Artikel enthält die folgenden Themen:  
  
-   [Mixingausnahmeschlüsselworte und Makros](#_core_mixing_exception_keywords_and_macros)  
  
-   [Try\-Blöcke innerhalb der catch\-Blöcke](#_core_try_blocks_inside_catch_blocks)  
  
##  <a name="_core_mixing_exception_keywords_and_macros"></a> Mixing\-Ausnahme\-Schlüsselworte und Makros  
 Sie können MFC\-Ausnahmemakros und C\+\+\-Ausnahme\-Schlüsselworte im selben Programm kombinieren.  Sie können jedoch mit C\+\+\-Ausnahme\-Schlüsselworten MFC\-Makros im gleichen Block nicht kombinieren, da die Makros Ausnahmeobjekte automatisch löschen, wenn sie den Gültigkeitsbereich verlassen, während Code mit der Ausnahmebehandlungsschlüsselworte hingegen nicht.  Weitere Informationen finden Sie im Artikel [Ausnahmen: Ausnahmen abfangen und Löschen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Der Hauptunterschied zwischen Makros und den Schlüsselwörtern ist, dass die Makros "automatisch" eine abgefangene Ausnahme löschen, wenn die Ausnahme den Bereich verlässt.  Code mit der Schlüsselwörter jedoch nicht; die Ausnahmen, die in einem catch\-Block abgefangen wurden, müssen explizit gelöscht werden.  Mixingmakros und C\+\+\-Ausnahme\-Schlüsselworte können Speicherverluste, wenn ein Ausnahmeobjekt nicht gelöscht wird, oder auf Beschädigungen verursachen, wenn eine Ausnahme zweimal gelöscht wird.  
  
 Im folgenden Code z macht den Ausnahmezeiger ungültig:  
  
 [!CODE [NVC_MFCExceptions#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#10)]  
  
 Das Problem tritt auf, da `e` gelöscht wird, wenn die Ausführung des inneren" **CATCH** "Block abgeschlossen ist.  Verwenden des Makros `THROW_LAST` anstelle der **THROW**\-Anweisung bewirkt den äußeren" **CATCH** "Block, einen gültigen Zeiger zu erhalten:  
  
 [!CODE [NVC_MFCExceptions#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#11)]  
  
##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try\-Blöcke innerhalb der Blöcke  
 Sie können die aktuelle Ausnahme nicht aus einem **try**\-Block erneut auslösen, der innerhalb eines Blocks **CATCH** ist.  Im folgenden Beispiel ist NULL:  
  
 [!CODE [NVC_MFCExceptions#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#12)]  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Untersuchungsausnahme\-Inhalt](../mfc/exceptions-examining-exception-contents.md).  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)