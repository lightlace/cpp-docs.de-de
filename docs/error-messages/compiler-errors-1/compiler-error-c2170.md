---
title: "Compilerfehler C2170"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2170"
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Nicht als Funktion deklariert, kann nicht systemintern sein  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Das `intrinsic`\-Pragma wird für ein anderes Element als eine Funktion verwendet.  
  
2.  Das `intrinsic`\-Pragma wird für eine Funktion ohne systeminterne Form verwendet.