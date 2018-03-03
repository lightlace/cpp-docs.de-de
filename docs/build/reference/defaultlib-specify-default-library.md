---
title: -DEFAULTLIB (Standardbibliothek festlegen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs:
- C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40fe07543dd9dc65d93cc9f79504f5fd324204dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (Standardbibliothek festlegen)
```  
/DEFAULTLIB:library  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *Bibliothek*  
 Der Name einer Bibliothek beim Auflösen externer Verweise durchsucht.  
  
## <a name="remarks"></a>Hinweise  
 Die Option Option Fügt eine *Bibliothek* zur Liste der Bibliotheken, mit dem LINK, beim Auflösen von Verweisen gesucht. Eine Bibliothek mit der Option angegeben, wird nach Bibliotheken in der Befehlszeile und vor Standardbibliotheken, die mit dem Namen in der OBJ-Dateien durchsucht.  
  
 Die [alle Standardbibliotheken ignorieren](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB) überschreibt Option:*Bibliothek*. Die [Bibliotheken ignorieren](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB:*Bibliothek*) überschreibt Option:*Bibliothek* Wenn identisch *Bibliothek* Name ist in beiden angegeben.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
-   Diese Linkeroption ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar. Um eine Bibliothek der Linkphase hinzuzufügen, verwenden Sie die **zusätzliche Abhängigkeiten** Eigenschaft aus der **Eingabe** Eigenschaftenseite.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)