---
title: "Muss ich von CObject neue Klassen ableiten?"
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
  - "CObject-Klasse, Empfohlene Verwendung"
  - "Abgeleitete Klassen, aus CObject"
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Muss ich von CObject neue Klassen ableiten?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nein, gehen Sie nicht.  
  
 Leiten Sie eine Klasse von [CObject](../mfc/reference/cobject-class.md), wenn Sie die Funktionen benötigen, die bereitstellt, z Serialisierung oder dynamisches creatability.  Viele Datenklassen müssen Dateien serialisiert werden, weshalb es häufig sich, sie aus `CObject` abgeleitet.  Ein Beispiel einer Klasse, die von `CObject` abgeleitet wird, finden Sie unter [Scribble\-Beispiel](../top/visual-cpp-samples.md).  
  
## Siehe auch  
 [CObject\-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)