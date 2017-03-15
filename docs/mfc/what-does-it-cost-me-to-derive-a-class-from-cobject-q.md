---
title: "Welcher Overhead entsteht beim Ableiten einer Klasse von CObject?"
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
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject-Klasse, Mehraufwand der abgeleiteten Klassen"
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Welcher Overhead entsteht beim Ableiten einer Klasse von CObject?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Aufwand, Sie beim Ableiten von der [CObject](../mfc/reference/cobject-class.md) ist minimal.  Die abgeleitete Klasse erbt nur vier virtuelle Funktionen [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) und ein einzelnes Objekt.  
  
## Siehe auch  
 [CObject\-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)