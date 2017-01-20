---
title: "VCPROFILE_PATH"
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
  - "VCPROFILE_PATH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_PATH-Umgebungsvariable"
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# VCPROFILE_PATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Geben Sie das Verzeichnis zur Erstellung von PGC\-Dateien an.  
  
## Syntax  
  
```  
VCPROFILE_PATH=path  
```  
  
#### Parameter  
 `path`  
 Der Verzeichnispfad, in den PGC\-Dateien hinzugefügt werden  
  
## Hinweise  
 In der Standardeinstellung werden PGC\-Dateien im selben Verzeichnis wie die zu profilierende Binärdatei erstellt.  Wenn der absolute Pfad der Binärdatei jedoch nicht existiert \(zum Beispiel bei der Ausführung von Profilszenarien auf einem anderen Computer als dem zur Erstellung der Binärdatei verwendeten\), können Sie in `VCPROFILE_PATH` einen existierenden Pfad festlegen.  
  
## Beispiel  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## Siehe auch  
 [Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)