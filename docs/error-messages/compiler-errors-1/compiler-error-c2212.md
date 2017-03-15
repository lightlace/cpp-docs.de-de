---
title: "Compilerfehler C2212 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2212"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2212"
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2212
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : \_\_based ist für Zeiger auf Funktionen nicht verfügbar  
  
 Zeiger auf Funktionen können nicht als `__based` deklariert werden.  Wenn Sie auf dem Code basierende Daten benötigen, verwenden Sie das `__declspec`\-Schlüsselwort oder das `data_seg`\-Pragma.