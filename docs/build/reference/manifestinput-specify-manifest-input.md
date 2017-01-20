---
title: "/MANIFESTINPUT (Angeben einer Manifesteingabedatei)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFESTINPUT (Angeben einer Manifesteingabedatei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt eine Manifesteingabedatei an, die dem Manifest hinzugefügt wird, das im Image eingebettet ist.  
  
## Syntax  
  
```c#  
/MANIFESTINPUT:filename  
```  
  
#### Parameter  
 `filename`  
 Die Manifestdatei, die dem eingebetteten Manifest hinzuzufügen ist.  
  
## Hinweise  
 Die **\/MANIFESTINPUT**\-Option gibt den Pfad einer Eingabedatei an, die zum Erstellen des eingebetteten Manifests in einem ausführbaren Image verwendet werden soll.  Wenn Sie mehrere Manifesteingabedateien haben, verwenden Sie den Schalter mehrfach, einmal für jede Eingabedatei.  Die Manifesteingabedateien werden zusammengeführt, um das eingebettete Manifest zu erstellen.  Diese Option erfordert die **\/MANIFEST:EMBED**\-Option.  
  
 Die Option kann nicht direkt in [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] festgelegt werden.  Verwenden Sie stattdessen **Zusätzliche Manifestdateien**\-Eigenschaft des Projekts, um zusätzliche Manifestdateien anzugeben, die hinzugefügt werden sollen.  Weitere Informationen finden Sie unter [Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projectname\>\-Eigenschaftenseiten“](../../ide/input-and-output-manifest-tool.md).  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)