---
title: "Compilerfehler C2170 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2170"
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Nicht als Funktion deklariert, kann nicht systemintern sein  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Das `intrinsic`\-Pragma wird für ein anderes Element als eine Funktion verwendet.  
  
2.  Das `intrinsic`\-Pragma wird für eine Funktion ohne systeminterne Form verwendet.