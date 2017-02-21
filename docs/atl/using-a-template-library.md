---
title: "Using a Template Library | Microsoft Docs"
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
  - "template libraries"
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Using a Template Library
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlage ist etwas wie ein Makro.  Wie ein Makro, führt das Aufrufen einer Vorlage sie erweitert \(mit dem entsprechenden Parameterersetzung\) um zu codieren Sie geschrieben haben.  Es wird eine Vorlage weiter als dieses, die Erstellung neuer Klassen basierend auf Typen zu ermöglichen, die Sie als Parameter übergeben.  Diese typsicheren Methoden des neuen Klassenwerkzeuges der Ausführung des Vorgangs ausgedrückt im Vorlagencode.  
  
 Vorlagenbibliotheken wie ATL unterscheiden sich von herkömmlichen C\+\+\-Klassenbibliotheken darin, dass sie in der Regel nur als Quellcode \(oder als Quellcode mit wenigen, Laufzeit unterstützende\), angegeben werden und nicht in der Natur grundsätzlich oder unbedingt hierarchisch sind.  Anstatt, die Ableitung von einer Klasse, um die Funktionalität abzurufen, sollen, instanziieren Sie eine Klasse aus einer Vorlage.  
  
## Siehe auch  
 [Einführung in ATL](../atl/introduction-to-atl.md)