---
title: "Multiple Dual Interfaces | Microsoft Docs"
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
  - "COM_INTERFACE_ENTRY_IID macro"
  - "COM_INTERFACE_ENTRY2 macro"
  - "duale Schnittstellen, exposing multiple"
  - "IDispatchImpl-Klasse, multiple dual interfaces"
  - "multiple dual interfaces"
  - "multiple dual interfaces, exposing with ATL"
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Multiple Dual Interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie sollten die Vorteile einer dualen Schnittstelle \(das heißt, die Flexibilität von der vtable und späte Bindung, die Klasse so zu so für Skriptsprachen und C\+\+\), mit der Mehrfachvererbung kombinieren.  
  
 Obwohl es möglich ist, mehrere duale Schnittstellen auf einem einzelnen COM\-Objekt verfügbar zu machen, wird es nicht empfohlen.  Wenn mehrere duale Schnittstellen vorhanden ist, muss es nur eine `IDispatch` verfügbar gemachte Schnittstelle geben.  Die Techniken, die, sicherzustellen, dass verfügbar sind, dies der Fall ist, wenden Strafen wie Funktionsverlust oder verbesserte Codekomplexität.  Der Entwickler, der diesen Ansatz betrachtet, sollte die Vor\- und Nachteile sorgfältig abwägen.  
  
## Verfügbar machen einer einzelnen IDispatch\-Schnittstelle  
 Es ist möglich, mehrere duale Schnittstellen auf einem einzelnen Objekt verfügbar zu machen, indem abgeleitet von zwei oder mehr Spezialisierungen von `IDispatchImpl`.  Wenn Sie jedoch Clients zur Abfrage die `IDispatch`\-Schnittstelle zulassen, müssen Sie das Makro [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) \(oder\) verwenden [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md) um anzugeben das für die Implementierung von `IDispatch` zu verwenden, die Basisklasse.  
  
 [!CODE [NVC_ATL_COM#23](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#23)]  
  
 Da nur eine `IDispatch`\-Schnittstelle verfügbar gemacht wird, sind Clients, die auf die Objekte über die `IDispatch`\-Schnittstelle nur zugreifen können, nicht, Methoden oder Eigenschaften in einer anderen zuzugreifen herstellen.  
  
## Kombination mehrerer duale Schnittstellen in eine einzelne Implementierung von IDispatch  
 ATL bietet keine Unterstützung für die Kombination mehrerer duale Schnittstellen in eine einzelne Implementierung von `IDispatch`.  Es gibt jedoch einige bekannte Ansätze zu Schnittstellen, die das Erstellen einer Vorlage gebildete Klasse manuell kombinieren, die Union der separaten `IDispatch`\-Schnittstellen enthält, ein neues Objekt erstellt, um die `QueryInterface`\-Funktion auszuführen, oder eine typeinfo\-basierte Implementierung von geschachtelten Objekte, um die `IDispatch`\-Schnittstelle erstellt.  
  
 Diese Vorgehensweisen haben Probleme mit möglichen Namespacekonflikten sowie Code Komplexität und Verwaltbarkeit.  Es wird nicht empfohlen, mehrere duale Schnittstellen erstellen.  
  
## Siehe auch  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)