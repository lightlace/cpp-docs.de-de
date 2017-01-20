---
title: "Linkertoolwarnung LNK4105"
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
  - "LNK4105"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4105"
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4105
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kein Argument mit Option 'Option' angegeben; Option wird ignoriert  
  
 Diese Warnung tritt nur auf, wenn die [\/LIBPATH](../../build/reference/libpath-additional-libpath.md)\-Option festgelegt wurde.  Wenn mit dieser Option kein Verzeichnis angegeben wird, wird sie vom Linker ignoriert, und diese Warnmeldung wird generiert.  
  
 Wenn Sie die bestehenden Umgebungseinstellungen für die Bibliothek nicht überschreiben müssen, entfernen Sie die **\/LIBPATH**\-Option aus der Linkerbefehlszeile.  Wenn ein alternativer Suchpfad für Bibliotheken verwendet werden soll, geben Sie diesen Pfad hinter der \/LIBPATH\-Option an.  
  
## Beispiel  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 Durch die vorherige Zeile wird der Linker angewiesen, die benötigten Bibliotheken nicht in den Standardverzeichnissen, sondern zunächst in `c:\filepath\lib` zu suchen.