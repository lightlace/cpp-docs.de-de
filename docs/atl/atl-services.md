---
title: "ATL-Dienste"
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
  - "CServiceModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Dienste"
  - "COM-Objekte, ATL"
  - "CServiceModule-Klasse"
  - "Dienste, ATL"
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-Dienste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um das ATL COM\-Objekt erstellen damit es in einen Dienst ausgeführt wird, wählen Sie einfach Dienst \(EXE\) aus der Liste von Serveroptionen im ATL\-Projekt\-Assistenten aus.  Der Assistent erstellt anschließend eine Klasse, die von `CAtlServiceModuleT` abgeleitet wird, um den Dienst zu implementieren.  
  
 Wenn das ATL COM\-Objekt als Dienst erstellt wird, wird es nur als lokaler Server registriert, und es wird nicht in der Liste der Dienste in der Systemsteuerung.  Dies ist, da es einfacher ist, den Dienst als lokaler Server als Dienst zu debuggen.  Um es als Dienst zu installieren, führen Sie an der Eingabeaufforderung aus:  
  
 `YourEXE` `.exe /Service`  
  
 Um sie zu deinstallieren, führen Sie Folgendes aus:  
  
 `YourEXE` `.exe /UnregServer`  
  
 Die ersten vier Themen in diesem Abschnitt behandeln die Aktionen, die während der Ausführung von `CAtlServiceModuleT`\-Memberfunktionen auftreten.  Diese Themen werden in derselben Reihenfolge, die die Funktionen in der Regel aufgerufen werden.  Um das Verständnis dieser Themen zu verbessern, empfiehlt es sich den Quellcode zu verwenden, der vom ATL\-Projekt\-Assistenten als Verweis generiert wird.  Diese ersten vier Themen sind:  
  
-   [Die CAtlServiceModuleT::Start\-Funktion](../atl/catlservicemodulet-start-function.md)  
  
-   [Die CAtlServiceModuleT::ServiceMain\-Funktion](../atl/catlservicemodulet-servicemain-function.md)  
  
-   [Die CAtlServiceModuleT::Run\-Funktion](../atl/catlservicemodulet-run-function.md)  
  
-   [Die CAtlServiceModuleT::Handler\-Funktion](../atl/catlservicemodulet-handler-function.md)  
  
 Die letzten drei Themen werden die Konzepte, die zur Entwicklung eines Diensts verknüpft werden:  
  
-   [Registrierungseinträge](../atl/registry-entries.md) für ATL\-Dienstleistungen  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [Tipps zum Debuggen](../atl/debugging-tips.md) für ATL\-Dienstleistungen  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)