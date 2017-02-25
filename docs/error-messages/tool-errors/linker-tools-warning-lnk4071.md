---
title: "Linkertoolwarnung LNK4071 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4071"
ms.assetid: 803f8c34-8219-4f55-a4ae-7133ceff2ba3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Linkertoolwarnung LNK4071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inkrementelles Binden für spätere Bindevorgänge nicht möglich  
  
 LINK hat mehrere Definitionen für mindestens ein Symbol gefunden. Es wurde jedoch [\/FORCE](../../build/reference/force-force-file-output.md) oder **\/FORCE:MULTIPLE** verwendet, um unabhängig von auftretenden Fehlern eine Ausgabedatei zu erstellen.  Die inkrementelle Statusdatei \(**.ilk**\) wird von LINK gelöscht.