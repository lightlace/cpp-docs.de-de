---
title: "Linkertoolwarnung LNK4022"
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
  - "LNK4022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4022"
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kann keine eindeutige Übereinstimmung für Symbol 'Symbol' finden  
  
 LINK oder LIB haben mehrfache Übereinstimmungen für das angegebene, nicht ergänzte Symbol gefunden und konnten die Mehrdeutigkeit nicht auflösen.  Es wird keine Ausgabedatei \(**.exe**, **.dll**, **.exp** oder **.lib**\) erstellt.  Auf diese Warnung folgt jeweils eine Warnung [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) für jedes doppelte Symbol und zuletzt der schwerwiegende Fehler [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).  
  
 Um diese Warnung zu vermeiden, geben Sie das Symbol in seiner ergänzten Form an.  Führen Sie [DUMPBIN](../../build/reference/dumpbin-options.md) für das Objekt aus, um die ergänzten Namen anzuzeigen.