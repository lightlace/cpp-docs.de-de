---
title: "Schwerwiegender Fehler C1046 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1046"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1046"
ms.assetid: 822ec5f5-b0b0-4711-99e1-fc237b619af6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1046
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Compilerlimit:**   
 ***Struktur* zu tief geschachtelt**  
  
 Die Struktur, Union oder Klasse hat die Schachtelungstiefe von 15 Ebenen überschritten.  Schreiben Sie die Definition neu, um die Schachtelungstiefe zu verringern.  Teilen Sie die Struktur, Union oder Klasse in zwei oder mehr Teile auf, indem Sie eine oder mehrere der geschachtelten Strukturen mit `typedef`  definieren.