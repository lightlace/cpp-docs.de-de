---
title: "Befehlszeilenfehler D8016"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "D8016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D8016"
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Befehlszeilenfehler D8016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Befehlzeilenoptionen "Option1" und "Option2" sind inkompatibel  
  
 Die Befehlszeilenoptionen können nicht zusammen angegeben werden.  
  
 Überprüfen Sie Umgebungsvariablen wie CL auf Optionsangaben.  
  
 **\/clr** impliziert **\/EHa**, und mit **\/clr** kann keine andere **\/EH**\-Compileroption angegeben werden.  Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Möglicherweise wird beim Update eines [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 6.0\-Projekts die Meldung D8016 angezeigt: Der Projektupdate\-Assistent aktiviert möglicherweise **\/RTC** für alle Quellcodedateien im Projekt, und die **\/RTC**\-Einstellung für das Projekt wird überschrieben.  Ändern Sie zur Behebung des Problems die **\/RTC**\-Einstellung aller Quellcodedateien auf die Standardeinstellung. Dadurch gilt für alle Dateien die Projekteinstellung für **\/RTC** .  
  
 Informationen zum Ändern der Eigenschafteneinstellung für **\/RTC** finden Sie unter [\/RTC \(Laufzeitfehlerüberprüfungen\)](../../build/reference/rtc-run-time-error-checks.md).