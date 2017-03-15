---
title: "Projektbuildwarnung PRJ0041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0041"
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Projektbuildwarnung PRJ0041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehlende Abhängigkeit 'Abhängigkeit' für Datei 'Datei' kann nicht gefunden werden.Das Projekt kann zwar erstellt werden, ist aber erst dann aktuell, wenn die Datei gefunden wurde.  
  
 In einer Datei \(z. B. einer Ressourcen\- oder IDL\/ODL\-Datei\) war eine **include**\-Anweisung enthalten, die vom Projektsystem nicht aufgelöst werden konnte.  
  
 Da das Projektsystem keine Präprozessoranweisungen \(z. B. `#if`\) verarbeitet, ist die beanstandete Anweisung möglicherweise gar nicht im Build enthalten.  
  
 Um diese Warnung zu vermeiden, löschen Sie den gesamten nicht benötigten Code in den RC\-Dateien oder fügen Platzhalterdateien mit entsprechenden Namen hinzu.