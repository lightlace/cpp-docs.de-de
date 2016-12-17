---
title: "Threading Models and Critical Sections Classes"
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
  - "vc.atl.threads.models"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, critical sections"
  - "ATL, Multithreading"
  - "critical sections"
  - "Threading [ATL], Modelle"
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Threading Models and Critical Sections Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Klassen definieren ein Threadingmodell und einen kritischen Abschnitt:  
  
-   [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) implementiert ein mit Threadpool, ApartmentModell COM\-Server.  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) stellt Methoden zum Implementieren eines mit Threadpool, ApartmentModell COM\-Server bereit.  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) stellt threadsichere Methoden zum Erhöhen und Verringern einer Variablen bereit.  Stellt einen kritischen Abschnitt bereit.  
  
-   [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) stellt threadsichere Methoden zum Erhöhen und Verringern einer Variablen bereit.  Stellt keinen kritischen Abschnitt bereit.  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) stellt Methoden zum Erhöhen und Verringern einer Variablen bereit.  Stellt keinen kritischen Abschnitt bereit.  
  
-   [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) bestimmt die entsprechende Threadingmodellklasse für eine einzelne Objektklasse.  
  
-   [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) bestimmt die entsprechende Threadingmodellklasse für ein Objekt, das global verfügbar ist.  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) enthält Methoden zum Abrufen und Freigeben eines kritischen Abschnitts.  Der kritischen Abschnitt wird automatisch initialisiert.  
  
-   [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) enthält Methoden zum Abrufen und Freigeben eines kritischen Abschnitts.  Der kritischen Abschnitt muss explizit initialisiert werden.  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) führt die Methoden in `CComCriticalSection`, ohne einen kritischen Abschnitt bereitzustellen.  Die Methoden in `CComFakeCriticalSection` bleiben wirkungslos.  
  
-   [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) stellt die Erstellungsfunktion für einen CRT\-Thread bereit.  Verwenden Sie diese Klasse, wenn der Thread CRT\-Funktionen verwendet.  
  
-   [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) stellt die Erstellungsfunktion für einen Windows\-Thread bereit.  Verwenden Sie diese Klasse, wenn der Thread nicht CRT\-Funktionen verwendet.  
  
## Siehe auch  
 [Class Overview](../atl/atl-class-overview.md)