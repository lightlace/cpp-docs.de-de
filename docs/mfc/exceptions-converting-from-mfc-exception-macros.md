---
title: "Ausnahmen: Umwandeln von MFC-Ausnahmemakros | Microsoft Docs"
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
  - "catch-Blöcke, Begrenzung"
  - "CException-Klasse, Löschen von CException-Klassenobjekten"
  - "Konvertierungen, mit MFC-Makros geschriebener Code"
  - "Konvertieren von Ausnahmen"
  - "Ausnahmebehandlung, Konvertieren von Ausnahmen"
  - "Ausnahmeobjekte"
  - "Ausnahmeobjekte, Löschen"
  - "Ausnahmen, Konvertieren"
  - "Ausnahmen, Löschen von Ausnahmeobjekten"
  - "Schlüsselwörter [C++], Makros"
  - "Makros, C++-Schlüsselwörter"
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ausnahmen: Umwandeln von MFC-Ausnahmemakros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dies ist ein fortgeschrittenes Thema.  
  
 Dieser Artikel beschreibt, wie Sie den vorhandenen Code konvertiert, der mit Microsoft Foundation Class\-Makros geschrieben \- **TRY**, **CATCH**, **THROW** usw. \-. um die C\+\+\-Ausnahmebehandlungsschlüsselworte **try**, **catch** und `throw`.  Folgende Themen werden behandelt:  
  
-   [Konvertierungsvorteile](#_core_advantages_of_converting)  
  
-   [Konvertieren von Code mit Ausnahmemakros, um C\+\+\-Ausnahmen zu verwenden](#_core_doing_the_conversion)  
  
##  <a name="_core_advantages_of_converting"></a> Vorteile des Konvertierens  
 Sie wahrscheinlich nicht, um vorhandenen Code konvertieren, obwohl Sie Unterschiede zwischen den Makroimplementierungen in MFC 3.0 und den Implementierungen in früheren Versionen berücksichtigen sollten.  Diese Unterschiede und folgenden Änderungen im Codeverhalten werden in [Ausnahmen: Änderungen an den Ausnahme\-Makros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) erläutert.  
  
 Die Hauptgründe Vorteile des Konvertierens sind:  
  
-   Code, der die C\+\+\-Ausnahmebehandlungsschlüsselworte kompiliert zu einem etwas kleineren EXE oder einem DLL\-Datei verwendet.  
  
-   Die C\+\+\-Ausnahmebehandlungsschlüsselworte sind vielseitiger: Sie können Ausnahmen beliebigen Datentyps behandeln, die kopiert werden können \(`int`, **float**, `char`, z.\), während die Makros Ausnahmen nur der Klasse `CException` und Klassen, die von dieser abgeleiteten werden behandeln.  
  
 Der Hauptunterschied zwischen Makros und den Schlüsselwörtern Code ist mithilfe von Makros "automatisch" wird gelöscht eine abgefangene Ausnahme, wenn die Ausnahme den Bereich verlässt.  Code mit der Schlüsselwörter jedoch nicht, müssen Sie eine abgefangene Ausnahme explizit löschen.  Weitere Informationen finden Sie im Artikel [Ausnahmen: Ausnahmen abfangen und Löschen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Ein anderer Unterschied ist Syntax.  Die Syntax für Makros und Schlüsselwörter weicht in drei Punkten:  
  
1.  Makroargumente und Ausnahmedeklarationen:  
  
     Ein **CATCH**\-Makroaufruf hat die folgende Syntax:  
  
     **CATCH\(** *exception\_class*, *exception\_object\_pointer\_name* **\)**  
  
     Beachten Sie das Komma zwischen dem Klassennamen und dem Objektzeigernamen.  
  
     Die Ausnahmedeklaration für das **catch**\-Schlüsselwort verwendet diese Syntax:  
  
     **catch\(** *exception\_type* *exception\_name***\)**  
  
     Diese Ausnahmedeklarationsanweisung gibt den Typ der Ausnahme die catch\-Blocks\-Handles an.  
  
2.  Begrenzung von catch\-Blöcken:  
  
     Mit Makros beginnt das **CATCH** \(Makro mit den Argumenten\) den ersten catch\-Block; das Makro `AND_CATCH` beginnt folgenden catch\-Blöcke, und das Makro `END_CATCH` die Sequenz beendet von catch\-Blöcken.  
  
     Mit den Schlüsselwörtern beginnt das **catch**\-Schlüsselwort \(mit seiner Ausnahmedeklaration\) einen catch\-Block.  Es gibt keine Entsprechung zum `END_CATCH`\-Makro; die catch\-Blocks\-Enden mit einer schließenden Klammer.  
  
3.  Der Wurfsausdruck:  
  
     Die Makros verwenden `THROW_LAST`, um die aktuelle Ausnahme erneut auslösen.  Das Schlüsselwort `throw`, ohne Argument, hat den gleichen Effekt.  
  
##  <a name="_core_doing_the_conversion"></a> Auf der Konvertierung  
  
#### So Code mit der Makros konvertieren, um die C\+\+\-Ausnahmebehandlungsschlüsselworte zu verwenden  
  
1.  Suchen Sie alle Vorkommen der MFC\-Makros **TRY**, **CATCH**, `AND_CATCH`, `END_CATCH`, **THROW** und `THROW_LAST`.  
  
2.  Ersetzen Sie alle Vorkommen der folgenden Makros:  
  
     **TRY** \(ersetzen Sie sie durch **try**\)  
  
     **CATCH** \(ersetzen Sie sie durch **catch**\)  
  
     `AND_CATCH` \(ersetzen Sie sie durch **catch**\)  
  
     `END_CATCH` \(Löschen es\)  
  
     **THROW** \(ersetzen Sie diese durch `throw`\)  
  
     `THROW_LAST` \(ersetzen Sie diese durch `throw`\)  
  
3.  Ändern Sie die Makroargumente, damit sie gültige Ausnahmedeklarationen bilden.  
  
     Beispielsweise Änderung  
  
     [!CODE [NVC_MFCExceptions#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#6)]  
  
     auf  
  
     [!CODE [NVC_MFCExceptions#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#7)]  
  
4.  Ändern Sie den Code in catch\-Blöcken, damit er Ausnahmeobjekte ggf. gelöscht.  Weitere Informationen finden Sie im Artikel [Ausnahmen: Ausnahmen abfangen und Löschen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Im Folgenden ein Beispiel für Ausnahmebehandlungscodes mithilfe der MFC\-Ausnahmemakros.  Beachten Sie, dass, da der Code im folgenden Beispiel die Makros verwendet, Ausnahme `e` automatisch deaktiviert ist:  
  
 [!CODE [NVC_MFCExceptions#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#8)]  
  
 Der Code im folgenden Beispiel verwendet die C\+\+\-Ausnahme\-Schlüsselworte, daher muss die Ausnahme explizit gelöscht werden:  
  
 [!CODE [NVC_MFCExceptions#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#9)]  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Verwenden MFC\-Makros und C\+\+\-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)