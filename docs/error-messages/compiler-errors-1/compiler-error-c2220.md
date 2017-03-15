---
title: "Compilerfehler C2220 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2220"
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compilerfehler C2220
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Warnung als Fehler behandelt \- keine Objektdatei generiert  
  
 [\/WX](../../build/reference/compiler-option-warning-level.md) weist den Compiler an, alle Warnungen als Fehler zu behandeln.  Da ein Fehler aufgetreten ist, wurde kein Objekt und keine ausführbare Datei generiert.  
  
 Dieser Fehler kommt nur vor, wenn das **\/WX**\-Flag festgelegt ist und eine Warnung während der Kompilierung auftritt.  Um diesen Fehler zu beheben, müssen Sie jede Warnung im Projekt ausschließen.  
  
### So beheben Sie den Fehler mit einer der folgenden Methoden  
  
-   Korrigieren Sie die Probleme, die Warnungen im Projekt verursachen.  
  
-   Kompilieren Sie auf einer niedrigeren Warnungsebene, z. B. mit **\/W3** statt **\/W4**.  
  
-   Verwenden Sie ein [warning](../../preprocessor/warning.md)\-Pragma, um eine bestimmte Warnung zu deaktivieren oder zu unterdrücken.  
  
-   Verwenden Sie beim Kompilieren nicht die **\/WX**\-Option.