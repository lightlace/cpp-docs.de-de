---
title: "Schwerwiegender Fehler C1033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1033"
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Schwerwiegender Fehler C1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Programmdatenbank pdb kann nicht geöffnet werden  
  
 Dieser Fehler kann durch eine Datenträgerfehler verursacht werden.  
  
 Visual C\+\+ .NET 2002 muss das Gebietsschema des Benutzers korrekt festgelegt werden, wenn der Dateiname \(oder der Pfad zum Verzeichnis der Datei\) MBCS\-Zeichen enthält.  Die Einstellung des Systemgebietsschemas allein reicht nicht aus; für die Verarbeitung von MBCS\-Zeichen muss das Benutzergebietsschema festgelegt werden.  
  
 Weitere Informationen finden Sie unter [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007).