---
title: "Compilerfehler C2212"
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
  - "C2212"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2212"
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2212
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : \_\_based ist für Zeiger auf Funktionen nicht verfügbar  
  
 Zeiger auf Funktionen können nicht als `__based` deklariert werden.  Wenn Sie auf dem Code basierende Daten benötigen, verwenden Sie das `__declspec`\-Schlüsselwort oder das `data_seg`\-Pragma.