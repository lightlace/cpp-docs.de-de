---
title: "Linkertoolwarnung LNK4075"
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
  - "LNK4075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4075"
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Option1' wird aufgrund der Angabe von 'Option2' ignoriert  
  
 Die erste Option wird durch die zweite überschrieben.  
  
 Es sind sich gegenseitig ausschließende Linkeroptionen angegeben.  Überprüfen Sie die Linkeroptionen.  Der Ort, an dem sich die Linkeroptionen befinden, hängt von der Art und Weise ab, wie Sie das Projekt erstellen.  
  
-   Wenn das Projekt in der Entwicklungsumgebung erstellt wird, zeigen Sie die Eigenschaftenseiten für den Linker des Projekts an, und suchen Sie nach den beiden Linkeroptionen.  Weitere Informationen finden Sie unter [Gewusst wie: Angeben von Projekteigenschaften mithilfe der Eigenschaftenseiten](../../misc/how-to-specify-project-properties-with-property-pages.md).  
  
-   Wenn Sie das Projekt in der Befehlszeile erstellen, durchsuchen Sie die dort angegebenen Linkeroptionen.  
  
-   Wenn Sie das Projekt mithilfe von Buildskripts erstellen, durchsuchen Sie die Skripts nach den betreffenden Linkeroptionen.  
  
 Wenn Sie die sich gegenseitig ausschließenden Linkeroptionen gefunden haben, entfernen Sie eine der Linkeroptionen.  
  
 Im Folgenden sind einige spezielle Beispiele aufgeführt:  
  
-   Wenn Sie ein Modul, das mit **\/ZI** kompiliert wurde und dadurch über eine interne Linkeroption mit dem Namen \/EDITANDCONTINUE verfügt, mit einem mit \/OPT:REF, \/OPT:ICF oder \/INCREMENTAL:NO kompilierten Modul verknüpfen, das nicht über \/EDITANDCONTINUE verfügt, wird LNK4075 ausgegeben.  Weitere Informationen finden Sie unter [\/Z7, \/Zi, \/ZI \(Debuginformationsformat\)](../../build/reference/z7-zi-zi-debug-information-format.md).