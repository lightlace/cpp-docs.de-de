---
title: "Angeben des Threadingmodells f&#252;r ein Projekt (ATL)"
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
  - "_ATL_APARTMENT_THREADED-Makro"
  - "_ATL_FREE_THREADED-Makro"
  - "_ATL_SINGLE_THREADED-Makro"
  - "ATL, Multithreading"
  - "Threading [ATL], Modelle"
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Angeben des Threadingmodells f&#252;r ein Projekt (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Makros sind verfügbar, das Threadingmodell eines ATL\-Projekts anzugeben:  
  
|Makro|Richtlinien für die Anwendung|  
|-----------|-----------------------------------|  
|\_ATL\_SINGLE\_THREADED|Definieren Sie, wenn alle Objekte das einzelne Threadingmodell verwenden.|  
|\_ATL\_APARTMENT\_THREADED|Definieren Sie, wenn eine oder mehrere der Objekte Apartmentthreading verwenden.|  
|\_ATL\_FREE\_THREADED|Definieren Sie wenn eine oder mehrere der freien Objektverwendung oder vom neutralen Threading.  Vorhandener Code enthält möglicherweise Verweise auf das entsprechenden Makro [\_ATL\_MULTI\_THREADED](../Topic/_ATL_MULTI_THREADED.md).|  
  
 Wenn Sie keine Makros für das Projekt definieren, ist \_ATL\_FREE\_THREADED wirksam.  
  
 Die Makros Laufzeitleistung beeinflussen, wie folgt:  
  
-   Das Angeben des Makros, das auf Objekte im Projekt entspricht, kann die Laufzeitleistung verbessern.  
  
-   Das Angeben weiterführende des Makros, wenn Sie \_ATL\_APARTMENT\_THREADED angeben, wenn alle Objekte singlethreaded sind, kompromittiert einige Laufzeitleistung.  
  
-   Das Angeben eines untergeordneten des Makros zum Beispiel wenn Sie \_ATL\_SINGLE\_THREADED angeben, wenn eine oder mehrere der Objekte Apartmentthreading oder freies Threading verwenden, kann die Anwendung verursachen, zur Laufzeit fehl.  
  
 Siehe [Optionen, ATL\-Assistent für einfache Objekte](../atl/reference/options-atl-simple-object-wizard.md) für eine Beschreibung der Threadingmodelle, die für ein ATL\-Objekt verfügbar sind.  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)