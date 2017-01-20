---
title: "Linkertoolwarnung LNK4206"
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
  - "LNK4206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4206"
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vorkompilierte Typinformationen nicht gefunden; 'Dateiname' wurde nicht verknüpft oder überschrieben; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären.  
  
 Die angegebene Objektdatei, die mit [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) kompiliert wurde, wurde entweder im LINK\-Befehl nicht angegeben oder außer Kraft gesetzt.  
  
 Eine häufige Ursache für diese Warnung ist der Umstand, dass sich die mit \/Yc kompilierte OBJ\-Datei in einer Bibliothek befindet, und keine Symbolverweise auf diese OBJ\-Datei im Code vorhanden sind.  In diesem Fall wird die OBJ\-Datei vom Linker nicht verwendet. Der Linker ist tatsächlich nicht einmal in der Lage, diese Datei zu erkennen.  Um das Problem zu beheben, sollte der Code neu kompiliert und für die übrigen Objekte \(die nicht mit \/Yc kompiliert wurden\) [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) verwendet werden.