---
title: "Schwerwiegender Fehler C1033"
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
  - "C1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1033"
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Programmdatenbank pdb kann nicht geöffnet werden  
  
 Dieser Fehler kann durch eine Datenträgerfehler verursacht werden.  
  
 Visual C\+\+ .NET 2002 muss das Gebietsschema des Benutzers korrekt festgelegt werden, wenn der Dateiname \(oder der Pfad zum Verzeichnis der Datei\) MBCS\-Zeichen enthält.  Die Einstellung des Systemgebietsschemas allein reicht nicht aus; für die Verarbeitung von MBCS\-Zeichen muss das Benutzergebietsschema festgelegt werden.  
  
 Weitere Informationen finden Sie unter [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007).