---
title: "ATL und der freethreaded Marshaller"
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
  - "ATL, Freethreaded Marshaler"
  - "Freethreaded Marshaler"
  - "FTM in ATL"
  - "Threading [ATL], Freethreaded Marshaler"
  - "Threading [C++], Marshaler in ATL"
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ATL und der freethreaded Marshaller
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Attributseite des ATL\-Assistenten für einfache Objekte enthält eine Option, die der Klasse ermöglicht, den Free\-Threaded Marshaller \(FTM\) zu aggregieren.  
  
 Der Assistent generiert Code, um eine Instanz des Free\-Threaded Marshallers in `FinalConstruct` zu erstellen und diese Instanz in `FinalRelease` freizugeben.  Ein `COM_INTERFACE_ENTRY_AGGREGATE`\-Makro wird automatisch der COM\-Zuordnung hinzugefügt, um sicherzustellen, dass `QueryInterface` Anforderungen für [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) durch den Marshaller Free\-Threaded bearbeitet wird.  
  
 Der Free\-Threaded Marshaller ermöglicht Direktzugriff auf Schnittstellen für das Objekt von jedem Thread im gleichen Prozess und beschleunigt apartmentübergreifenden Aufrufe.  Diese Option wird für Klassen ausgelöst, die beide Threadingmodell verwenden.  
  
 Wenn diese Option verwenden, müssen Klassen Verantwortung für Threadsicherheit ihrer Daten angewendet.  Außerdem Objekte, die den Free\-Threaded Marshaller aggregieren und Anforderung, Schnittstellenzeiger zu verwenden aus anderen Objekten muss zusätzliche Schritte unternehmen, um sicherzustellen, dass die abgerufenen Schnittstellen ordnungsgemäß gemarshallt werden.  In der Regel bedeutet dies, die Schnittstellenzeiger zu speichern in die globale Schnittstellentabelle \(GIT\) mit ein und den Zeiger vom GIT abzurufen, wenn es verwendet wird.  ATL stellt die Klasse [CComGITPtr](../atl/reference/ccomgitptr-class.md), die Ihnen helfen, die Schnittstellenzeiger zu verwenden, die im GIT gespeichert werden.  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [When to Use the Global Interface Table](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [In\-Process Server Threading Issues](http://msdn.microsoft.com/library/windows/desktop/ms687205)