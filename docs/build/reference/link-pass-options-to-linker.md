---
title: "/link (Optionen an Linker &#252;bergeben)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/link (Compileroption) [C++]"
  - "cl.exe-Compiler [C++], Übergeben von Optionen an Linker"
  - "link (Compileroption) [C++]"
  - "-link (Compileroption) [C++]"
  - "Linker [C++], Übergeben von Optionen an"
  - "Übergabe von Optionen an Linker"
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /link (Optionen an Linker &#252;bergeben)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Übergibt eine oder mehrere Linkeroptionen an den Linker.  
  
## Syntax  
  
```  
/link linkeroptions  
```  
  
## Argumente  
 `linkeroptions`  
 die Linkeroption bzw. die Linkeroptionen, die an den Linker übergeben werden.  
  
## Hinweise  
 Die **\/link**\-Option und zugehörige Linkeroptionen müssen nach etwaigen Dateinamen und CL\-Optionen angegeben werden.  Ein Leerzeichen ist erforderlich zwischen **\/link** und `linkeroptions`.  Weitere Informationen finden Sie unter [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf eine Linker\-Eigenschaftenseite.  
  
4.  Ändern Sie eine oder mehrere Eigenschaften.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Diese Compileroption kann nicht programmgesteuert geändert werden.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)