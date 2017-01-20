---
title: "1. Introduction"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 1. Introduction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Dokument gibt eine Auflistung von Bibliotheksfunktionen, Compileranweisung und Umgebungsvariablen an, die verwendet werden können, um Freigegebene Arbeitsspeicher Parallelität in C\# und C\+\+\-Programmen anzugeben.  Die Funktionen, die in diesem Dokument beschriebene bekannt als die zusammen *OpenMPs C\/C\+\+ Anwendungsprogrammierschnittstelle \(API\)*.  Das Ziel dieser Spezifikation ist, ein Modell für parallele Programmierung bereitzustellen, die einem Programm ermöglicht, über Freigegebene Arbeitsspeicher von verschiedenen Architekturen Anbieter portabel sind.  OpenMP C\/C\+\+ API wird vom Compiler von zahlreichen Anbietern unterstützt.  Weitere Informationen zu OpenMP, einschließlich der *OpenMP\-Fortran\-Anwendungsprogrammierschnittstelle*, können auf der folgenden Website durchsucht werden:  
  
 [http:\/\/www.openmp.org](http://www.openmp.org)  
  
 Die Direktive, die Bibliotheksfunktionen und die Umgebungsvariablen, die in diesem Dokument definiert sind, ermöglichen es Benutzern, während paralleler Programme zum Aktivieren von Portabilität zu erstellen und zu verwalten.  Die Direktive erweitern das Programmiermodell sequenzielle C und C\+\+ mehrere Konstrukte der Daten des einzelnen Programms \(SPMD\), Arbeitsteilungs und konstrukten Synchronisierung konstrukten, und sie bieten Unterstützung für die gemeinsame Nutzung und Privatisierung von Daten.  Compiler, die OpenMP C und C\+\+ APIs unterstützen, stellen eine Befehlszeilenoption an den Compiler ein, der Interpretation aller OpenMP\-Compiler Direktiven aktiviert und ermöglicht.