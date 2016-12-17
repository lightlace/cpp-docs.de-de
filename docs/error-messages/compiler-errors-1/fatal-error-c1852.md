---
title: "Schwerwiegender Fehler C1852"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C1852"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1852"
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1852
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Dateiname' ist keine gültige vorkompilierte Headerdatei.  
  
 Die Datei ist kein vorkompilierter Header.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es wurde eine ungültige Datei mit **\/Yu** oder **\#pragma hdrstop** angegeben.  
  
2.  Wenn Sie keine andere Angabe vornehmen, nimmt der Compiler die Dateierweiterung PCH an.