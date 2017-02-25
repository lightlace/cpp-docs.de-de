---
title: "Ausnahmeverarbeitung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (Datenzugriffsobjekte), Ausnahmen"
  - "Ausnahmemakros"
  - "Ausnahmen, MFC auslösende Funktionen"
  - "Ausnahmen, Verarbeiten"
  - "Makros, Ausnahmebehandlung"
  - "MFC, Ausnahmen"
  - "OLE-Ausnahmen, MFC-Funktionen"
  - "Terminierungsfunktion, MFC"
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Ausnahmeverarbeitung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn ein Programm ausgeführt wird, können einige der Regel abweichende Anforderungen und Fehler, die "Ausnahmen" bezeichnet werden, auftreten.  Diese enthalten möglicherweise ausgeführt, Ressourcenzuordnungsfehler genügend Arbeitsspeicher und Fehler ein, Dateien zu finden.  
  
 Die Microsoft Foundation Class\-Bibliothek verwendet ein Ausnahmebehandlungsschema, das eng nach dem modelliert wird, das vom ANSI\-Normungsausschuss für C\+\+ enthält.  Ein Ausnahmehandler muss installiert werden, bevor eine Funktion aufruft, die möglicherweise eine Regel abweichende Situation entdeckt.  Wenn die Funktion eine Regel abweichende Zustand auftritt, löst sie eine Ausnahme aus und Steuerelement wird z Ausnahmehandler übergeben.  
  
 Einige Makros, die mit der Microsoft Foundation Class\-Bibliothek enthalten sind, installieren Ausnahmehandler.  Einige andere globale Funktionen erleichtern, spezielle Ausnahmen auszulösen und Programme zu beenden, falls erforderlich.  Diese Makros und globalen Funktionen werden in die folgenden Kategorien:  
  
-   [Ausnahmemakros](#_mfc_exception_macros), die den Ausnahmehandler strukturieren.  
  
-   [Ausnahme\-Auslösen von Funktionen](#_mfc_exception.2d.throwing_functions), die Ausnahmen bestimmter Typen generieren.  
  
-   [Beendigungsfunktionen](#_mfc_termination_functions), die dass verursachen.  
  
 Beispiele und weitere Details finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### Ausnahme\-Makros  
  
|||  
|-|-|  
|[TRY](../Topic/TRY.md)|Legt einen Codeblock für die Ausnahmeverarbeitung fest.|  
|[CATCH](../Topic/CATCH.md)|Legt einen Codeblock für das Abfangen einer Ausnahme vom vorherigen **TRY**\-Block fest.|  
|[CATCH\_ALL](../Topic/CATCH_ALL.md)|Legt einen Codeblock für das Abfangen aller Ausnahmen vom vorherigen **TRY**\-Block fest.|  
|[AND\_CATCH](../Topic/AND_CATCH.md)|Legt einen Codeblock für ansprechende zusätzliche Ausnahmetypen vom vorherigen **TRY**\-Block fest.|  
|[AND\_CATCH\_ALL](../Topic/AND_CATCH_ALL.md)|Legt einen Codeblock für das Abfangen aller anderen zusätzliche Ausnahmetypen fest, die in einem vorherigen **TRY**\-Block ausgelöst werden.|  
|[END\_CATCH](../Topic/END_CATCH.md)|Beendet letzten **CATCH** oder den Codeblock `AND_CATCH`.|  
|[END\_CATCH\_ALL](../Topic/END_CATCH_ALL.md)|Beendet den letzten `CATCH_ALL` Codeblock.|  
|[THROW](../Topic/THROW%20\(MFC\).md)|Löst eine bestimmte Ausnahme aus.|  
|[THROW\_LAST](../Topic/THROW_LAST.md)|Löst die gerade behandelte Ausnahme dem folgenden äußeren Handler aus.|  
  
### Ausnahme\-Auslösen von Funktionen  
  
|||  
|-|-|  
|[AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)|Löst eine Archivausnahme aus.|  
|[AfxThrowFileException](../Topic/AfxThrowFileException.md)|Löst eine Dateiausnahme aus.|  
|[AfxThrowMemoryException](../Topic/AfxThrowMemoryException.md)|Löst eine Arbeitsspeicherausnahme aus.|  
|[AfxThrowNotSupportedException](../Topic/AfxThrowNotSupportedException.md)|Löst eine nicht unterstützte Ausnahme aus.|  
|[AfxThrowResourceException](../Topic/AfxThrowResourceException.md)|Löst eine Windows Ressource\-NOT\-gesuchte Ausnahme aus.|  
|[AfxThrowUserException](../Topic/AfxThrowUserException.md)|Löst eine Ausnahme in eine benutzerinitiierte Programmaktion aus.|  
  
 MFC stellt zwei Ausnahme\-auslösende Funktionen speziell für OLE\-Ausnahmen bereit:  
  
### OLE\-Ausnahme\-Funktionen  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md)|Löst eine Ausnahme in einer OLE\-Automatisierungs\-Funktion aus.|  
|[AfxThrowOleException](../Topic/AfxThrowOleException.md)|Löst eine OLE\-Ausnahme aus.|  
  
 Um Datenbankausnahmen zu unterstützen, stellen die Datenbankklassen zwei Ausnahmeklassen, `CDBException` und `CDaoException` sowie globale Funktionen um die Ausnahmetypen zu unterstützen:  
  
### DAO\-Ausnahme\-Funktionen  
  
|||  
|-|-|  
|[AfxThrowDAOException](../Topic/AfxThrowDaoException.md)|Löst einen [CDaoException](../../mfc/reference/cdaoexception-class.md) aus dem eigenen Code aus.|  
|[AfxThrowDBException](../Topic/AfxThrowDBException.md)|Löst einen [CDBException](../../mfc/reference/cdbexception-class.md) aus dem eigenen Code aus.|  
  
 MFC stellt die folgenden Beendigungsfunktion:  
  
### Beendigungs\-Funktionen  
  
|||  
|-|-|  
|[AfxAbort](../Topic/AfxAbort.md)|Wird aufgerufen, um eine Anwendung beendet, wenn ein schwer wiegender Fehler auftritt.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException Class](../../mfc/reference/cexception-class.md)