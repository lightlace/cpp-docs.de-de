---
title: "BSCMAKE-Warnung BK4504"
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
  - "BK4504"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK4504"
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE-Warnung BK4504
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Datei enthält zu viele Verweise. Weitere Verweise von dieser Quelle werden ignoriert  
  
 Die CPP\-Datei enthält mehr als 64.000 Symbolverweise.  Wenn BSCMAKE 64.000 Verweise in einer Datei erreicht hat, ignoriert es alle weiter Verweise.  
  
 Um das Problem zu beheben, entweder Unterteilung die Datei in mehrere kleinere Dateien, die weniger als 64.000 Symbolverweise verfügt, oder die `#pragma component(browser)` mithilfe von Präprozessordirektiven um Symbole einzuschränken die als spezifische Projekt generiert werden.  Weitere Informationen finden Sie unter [Komponente](../../preprocessor/component.md).