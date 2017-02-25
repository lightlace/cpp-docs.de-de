---
title: "Schwerwiegender Fehler C1902 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1902"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1902"
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Schwerwiegender Fehler C1902
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler im Programmdatenbank\-Manager. Überprüfen Sie die Installation.  
  
 Eine Programmdatenbankdatei \(.pdb\) wurde mit einer neueren Version von mspdb *XX*.dll als derjenigen erstellt, die vom Compiler auf Ihrem System gefunden wurde.  Dieser Fehler gibt normalerweise an, dass mspdbsrv.exe oder mspdbcore.dll fehlen oder andere Versionen als mspdb *XX*.dll haben. \(Der Platzhalter *XX* in der Datei mspdb *XX*.dll ändert sich mit jeder Produktversion.  In [!INCLUDE[vsprvslong](../../error-messages/compiler-errors-1/includes/vsprvslong_md.md)] lautet der Dateiname z. B. mspdb80.dll.\)  
  
 Stellen Sie sicher, dass übereinstimmende Versionen von mspdbsrv.exe, mspdbcore.dll und mspdb *XX*.dll auf dem System installiert sind.  Stellen Sie sicher, dass keine nicht übereinstimmenden Versionen in das Verzeichnis kopiert wurden, das das Compilertool und das LINK\-Tool für Ihre Zielplattform enthält.  Sie könnten z. B. die Dateien kopiert haben, damit Sie das Compilertool oder das LINK\-Tool über die Befehlszeile aufrufen können, ohne die **PATH**\-Umgebungsvariable entsprechend festzulegen.