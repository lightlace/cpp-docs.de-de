---
title: "CL-Befehlsdateien"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Befehlsdateien"
  - "Befehlsdateien"
  - "Befehlsdateien, CL-Compiler"
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# CL-Befehlsdateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Befehlsdatei ist eine Textdatei, die Optionen und Dateinamen enthält, die Sie normalerweise in der [Befehlszeile](../../build/reference/compiler-command-line-syntax.md) eingeben oder über die [CL\-Umgebungsvariable](../../build/reference/cl-environment-variables.md) festlegen.  CL akzeptiert eine Compilerbefehlsdatei als Argument in der CL\-Umgebungsvariablen oder in der Befehlszeile.  Anders als in der Befehlszeile oder in der CL\-Umgebungsvariablen können Sie in einer Befehlsdatei mehrzeilige Optionen und Dateinamen verwenden.  
  
 Optionen und Dateinamen in einer Befehlsdatei werden entsprechend der Stelle verarbeitet, an der der Befehlsdateiname in der CL\-Umgebungsvariablen oder der Befehlszeile genannt wird.  Wenn in der Befehlsdatei jedoch die **\/link**\-Option auftritt, werden alle Optionen im Rest der Zeile an den Linker übergeben.  Optionen in nachfolgenden Zeilen der Befehlsdatei sowie Optionen in der Befehlszeile nach dem Aufruf der Befehlsdatei werden weiterhin als Compileroptionen akzeptiert.  Weitere Informationen zum Einfluss der Reihenfolge der Optionen auf ihre Interpretation finden Sie unter [Reihenfolge von CL\-Optionen](../../build/reference/order-of-cl-options.md).  
  
 Eine Befehlsdatei darf keinen CL\-Befehl enthalten.  Jede Option muss in derselben Zeile beginnen und enden; Sie können nicht den umgekehrten Schrägstrich \(\\\) verwenden, um eine Option über zwei Zeilen auszudehnen.  
  
 Eine Befehlsdatei wird durch das @\-Zeichen, gefolgt vom Dateinamen, angegeben. Durch den Dateinamen kann ein absoluter oder relativer Pfad angegeben werden.  
  
 Wenn sich der folgende Befehl beispielsweise in einer Datei mit dem Namen RESP befindet:  
  
```  
/Og /link LIBC.LIB  
```  
  
 und Sie den folgenden CL\-Befehl eingeben:  
  
```  
CL /Ob2 @RESP MYAPP.C  
```  
  
 dann sieht der Befehl für CL so aus:  
  
```  
CL /Ob2 /Og MYAPP.C /link LIBC.LIB  
```  
  
 Beachten Sie, dass die Befehlszeile und die Befehle aus der Befehlsdatei im Ergebnis miteinander kombiniert werden.  
  
## Siehe auch  
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)