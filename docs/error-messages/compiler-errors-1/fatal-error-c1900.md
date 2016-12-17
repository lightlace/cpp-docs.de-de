---
title: "Schwerwiegender Fehler C1900"
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
  - "C1900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1900"
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konflikt zwischen 'tool1', Version 'Nummer1', und 'tool2', Version 'Nummer2'  
  
 In verschiedenen Durchläufen des Compilers ausgeführte Tools stimmen nicht überein.  ***Zahl1***  und ***Zahl2*** finden Sie die Datumsangaben der Dateien.  Z. B. führt in Durchgang 1 durch das Compiler\-front End \(c1.dll\) ausgeführt und in Durchgang 2 führt der Compiler\-back\-End \(c2.dll\) aus.  Die Datumsangaben der Dateien müssen übereinstimmen.  
  
 Um dieses Problem zu beheben, stellen Sie sicher, dass alle Aktualisierungen auf Visual Studio angewendet wurden.  Wenn das Problem weiterhin besteht, verwenden Sie **Programme und Funktionen** in der Windows\-Systemsteuerung, um Visual Studio zu reparieren oder neu zu installieren.