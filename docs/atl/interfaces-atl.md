---
title: "Interfaces (ATL) | Microsoft Docs"
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
  - "COM-Schnittstellen"
  - "Schnittstellen, COM"
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Interfaces (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle ist die Methode, in der ein Objekt seine Funktionen der Außenwelt verfügbar macht.  In COM ist eine Schnittstelle eine Tabelle von Zeigern \(\(beispielsweise eine vtable\) auf Funktionen, die durch das Objekt implementiert werden.  Die Tabelle stellt die Schnittstelle dar, und die Funktionen auf der es verweist, sind die Methoden dieser Schnittstelle.  Ein Objekt kann bis zu Schnittstellen verfügbar machen, es auswählt.  
  
 Jede Schnittstelle basiert auf die grundlegende COM\-Schnittstelle, [IUnknown](../atl/iunknown.md).  Die Methoden von **IUnknown** ermöglichen die Navigation zu anderen Schnittstellen, die vom Objekt verfügbar gemacht werden.  
  
 Außerdem wird jede Schnittstelle eindeutigen Schnittstellen\-ID \(IID\) zugewiesen.  Diese Eindeutigkeit erleichtert es, Schnittstellenversionsverwaltung zu unterstützen.  Eine neue Version einer Schnittstelle ist einfach eine neue Schnittstelle, mit einem neuen IID.  
  
> [!NOTE]
>  IID für den standardmäßigen COM und OLE\-Schnittstellen werden vordefiniert.  
  
## Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [COM Objects and Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms690343)