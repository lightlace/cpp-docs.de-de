---
title: "@ (Compiler-Antwortdateien festlegen)"
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
  - "@"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "@-Compileroption"
  - "cl.exe-Compiler, Angeben von Antwortdateien"
  - "Antwortdateien, C/C++-Compiler"
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# @ (Compiler-Antwortdateien festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt eine Compiler\-Antwortdatei fest.  
  
## Syntax  
  
```  
@response_file  
```  
  
## Argumente  
 `response_file`  
 eine Textdatei mit Compilerbefehlen.  
  
## Hinweise  
 Eine Antwortdatei kann alle Befehle enthalten, die in die Befehlszeile eingegeben werden können.  Dies kann hilfreich sein, wenn die Befehlszeilenargumente 127 Zeichen überschreiten.  
  
 Es ist nicht möglich, die **@**\-Option innerhalb einer Antwortdatei festzulegen.  Das bedeutet, eine Antwortdatei kann nicht in einer anderen Antwortdatei eingebettet sein.  
  
 In der Befehlszeile können beliebig viele Antwortdateioptionen angegeben werden \(z. B. `@respfile.1 @respfile.2`\).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
-   Eine Antwortdatei kann nicht innerhalb der Entwicklungsumgebung, sondern nur in der Befehlszeile angegeben werden.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Diese Compileroption kann nicht programmgesteuert geändert werden.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)