---
title: "Entwickeln eigener Hilfsfunktionen | Microsoft Docs"
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
  - "Hilfsfunktionen"
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Entwickeln eigener Hilfsfunktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Möglicherweise soll eine eigene Version der Routine bereitgestellt werden, um spezielle Verarbeitungsschritte durchzuführen, die vom Namen der DLL oder von Importen abhängen.  Hierzu stehen zwei Methoden zur Verfügung: eigene Codierung, die unter Umständen auf dem gelieferten Code basiert, oder ein Hook für die gelieferte Version mithilfe der bereits beschriebenen Benachrichtigungshooks erstellen.  
  
 Eigene Codierung  
 Dies ist sehr einfach, da der zur Verfügung gestellte Code als Vorlage für den neuen Code verwendet werden kann.  Selbstverständlich muss der Code den Aufrufkonventionen entsprechen, und er muss einen geeigneten Funktionszeiger als Rückgabewert verwenden, falls er zu den vom Linker generierten Thunks zurückkehrt.  Innerhalb des Codes selbst können beliebige Schritte unternommen werden, um den Aufruf zu erfüllen oder ihn zu verlassen.  
  
 Verwenden des Benachrichtigungshooks für Verarbeitungsbeginn  
 Am einfachsten ist es, einen neuen Zeiger auf eine benutzerdefinierte Benachrichtigungshookfunktion bereitzustellen, die dieselben Werte über die **dliStartProcessing**\-Benachrichtigung empfängt wie die Standardhilfsfunktion.  An dieser Stelle kann die Hookfunktion im Prinzip als neue Hilfsfunktion verwendet werden, da bei erfolgreicher Rückkehr zur Standardhilfsfunktion die weitere Verarbeitung in der Hilfsfunktion umgangen wird.  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)