---
title: "Schwerwiegender Fehler C1305 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1305"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1305"
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Schwerwiegender Fehler C1305
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Profildatenbank 'PDG\-Datei' wird für eine andere Architektur verwendet.  
  
 Eine durch die \/LTCG:PGINSTRUMENT\-Operation für eine andere Plattform erzeugte PDG\-Datei wird an [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) übergeben.  [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md) sind für x86\- und [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\-Plattformen verfügbar.  Eine mit einer \/LTCG:PGINSTRUMENT\-Operation für eine bestimmte Plattform erzeugte PGD\-Datei ist jedoch ungültig als Eingabe für eine \/LTCG:PGOPTIMIZE\-Operation für eine andere Plattform.  
  
 Um diesen Fehler zu beheben, geben Sie eine mit \/LTCG:PGINSTRUMENT erstellte PGD\-Datei nur an \/LTCG:PGOPTIMIZE für dieselbe Plattform weiter.