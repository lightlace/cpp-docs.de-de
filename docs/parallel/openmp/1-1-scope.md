---
title: "1.1 Scope"
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
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# 1.1 Scope
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Spezifikation enthält nur USER\-verwiesene Parallelisierung, worin der Benutzer explizit die Aktionen angibt, die vom Compiler und die Laufzeit System übernommen werden soll, um das Programm parallel auszuführen.  Implementierungen OpenMPs C und C\+\+ sind nicht erforderlich, um Abhängigkeiten für Konflikte, Deadlocks, Racebedingungen oder andere Probleme zu überprüfen, die falsche Programmausführung führen.  Der Benutzer stellt sicher, dass die Anwendung mithilfe der Konstrukte OpenMPs C und C\+\+ API ordnungsgemäß ausgeführt wird.  Vom Compiler generierter automatische Parallelisierung und Direktive für den Compiler, um solche Parallelisierung zu sichern werden nicht in diesem Dokument beschriebenen.