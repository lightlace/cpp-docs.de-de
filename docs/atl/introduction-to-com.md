---
title: "Einf&#252;hrung in COM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM"
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Einf&#252;hrung in COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM ist das grundlegende "Objektmodell" auf, welche ActiveX\-Steuerelemente und OLE erstellt werden.  COM können Objekte, seine Funktionalität für andere Komponenten und Hostanwendungen verfügbar machen.  Es definiert, wie sich das Objekt verfügbar macht und wie diese Art prozessübergreifend und über Netzwerken funktioniert.  COM definiert auch den Lebenszyklus des Objekts.  
  
 Grundlage für COM sind diese Konzepte:  
  
-   [Schnittstellen](../atl/interfaces-atl.md) \- Mechanismus, durch den ein Objekt seine Funktionalität bereitstellt.  
  
-   [IUnknown](../atl/iunknown.md) \- die Basisschnittstelle, auf der alle anderen basieren.  Sie implementiert die Verweiszählung und die Schnittstelle, die die Mechanismen abgefragt werden, die über COM ausgeführt werden.  
  
-   [Verweiszählung](../atl/reference-counting.md) \- die Technik, durch die ein Objekt \(oder ausschließlich eine Schnittstelle\) entscheidet, wenn nicht mehr verwendet wird und daher entscheiden, zu entfernen.  
  
-   [QueryInterface](../atl/queryinterface.md)\-Methode verwendet, um ein Objekt für eine bestimmte Schnittstelle abzufragen.  
  
-   [Marshalling](../atl/marshaling.md) \- der Mechanismus, der die über aktiviert, Prozess und Thread Netzwerkgrenzen verwendet werden, um Objekte, Standortunabhängigkeit zu.  
  
-   [Aggregation](../atl/aggregation.md) \- eine Methode, in welchem Objekt kann andere ausnutzen.  
  
## Siehe auch  
 [Introduction to COM and ATL](../atl/introduction-to-com-and-atl.md)   
 [The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)