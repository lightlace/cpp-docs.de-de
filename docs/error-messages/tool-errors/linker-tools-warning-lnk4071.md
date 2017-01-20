---
title: "Linkertoolwarnung LNK4071"
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
  - "LNK4071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4071"
ms.assetid: 803f8c34-8219-4f55-a4ae-7133ceff2ba3
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inkrementelles Binden für spätere Bindevorgänge nicht möglich  
  
 LINK hat mehrere Definitionen für mindestens ein Symbol gefunden. Es wurde jedoch [\/FORCE](../../build/reference/force-force-file-output.md) oder **\/FORCE:MULTIPLE** verwendet, um unabhängig von auftretenden Fehlern eine Ausgabedatei zu erstellen.  Die inkrementelle Statusdatei \(**.ilk**\) wird von LINK gelöscht.