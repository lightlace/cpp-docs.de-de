---
title: "Compilerwarnung (Stufe 1) C4124"
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
  - "C4124"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4124"
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4124
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_fastcall mit Stapelüberprüfung ist ineffizient  
  
 Das `__fastcall`\-Schlüsselwort wurde mit aktivierter Stapelüberprüfung verwendet.  
  
 Durch die `__fastcall`\-Konvention wird zwar schnellerer Code generiert, die Stapelüberprüfung bewirkt jedoch eine Verlangsamung.  Deaktivieren Sie die Stapelüberprüfung bei Verwendung von `__fastcall` mit dem **check\_stack**\-Pragma oder mit **\/Gs**.  
  
 Diese Warnung wird nur für die erste Funktion ausgegeben, die unter diesen Bedingungen deklariert wurde.