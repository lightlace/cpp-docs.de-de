---
title: "NMAKE: Schwerwiegender Fehler U1051 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1051"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1051"
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Schwerwiegender Fehler U1051
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht genügend Arbeitsspeicher.  
  
 NMAKE steht nicht genügend Arbeitsspeicher, einschließlich des virtuellen Speichers, zur Verfügung, da das Makefile zu groß oder zu komplex war.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Geben Sie Festplattenspeicher frei.  
  
2.  Vergrößern Sie die Auslagerungsdatei von Windows NT oder Windows.  
  
3.  Falls nur ein Teil des Makefiles verwendet wird, teilen Sie dieses in separate Dateien auf, oder verwenden Sie **\!IF**\-Präprozessordirektiven, um den von NMAKE zu verarbeitenden Teil zu begrenzen.  Zu den **\!IF**\-Direktiven gehören **\!IF**, `!IFDEF`, **\!IFNDEF**, **\!ELSE IF**, **\!ELSE** `IFDEF` und **\!ELSE** `IFNDEF`.