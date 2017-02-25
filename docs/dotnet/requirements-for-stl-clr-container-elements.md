---
title: "Anforderungen f&#252;r STL/CLR-Containerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Container, STL"
  - "Container, STL/CLR"
  - "C++-Standardbibliothek, Vorlangenklassencontainer"
  - "STL/CLR, Container"
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Anforderungen f&#252;r STL/CLR-Containerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Alle Referenztypen, die in STL\/CLR\-Container eingefügt werden, müssen mindestens die folgenden Elemente enthalten:  
  
-   Ein öffentlicher Kopierkonstruktor.  
  
-   Ein Operator der öffentlichen Zweckbestimmung.  
  
-   Ein öffentlicher Destruktor.  
  
 Darüber hinaus müssen assoziative Container wie [Festlegen](../dotnet/set-stl-clr.md) und [Zuordnung](../dotnet/map-stl-clr.md) einen öffentlichen definierten Vergleichsoperator haben, der die `operator<` standardmäßig ist.  Einige Vorgänge in Containern benötigen auch einen öffentlichen Standardkonstruktor definiert werden und einen öffentlichen Äquivalenzoperator.  
  
 Wie Referenztypen müssen Werttypen und Handles zu den Typen verweisen, die in einem assoziativen Container eingefügt werden sollen, ein Vergleichsoperator wie `operator<` aufweisen definiert haben.  Die Anforderungen für einen öffentlichen Kopierkonstruktor, Operator der öffentlichen Zweckbestimmung und einen öffentlichen Destruktor vorhanden für Werttypen nicht oder Handles in Verweistypen.  
  
## Siehe auch  
 [Standard Template Library](../misc/standard-template-library.md)