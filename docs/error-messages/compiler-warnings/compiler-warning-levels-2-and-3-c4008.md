---
title: "Compilerwarnung (Stufen 2 und 3) C4008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4008"
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufen 2 und 3) C4008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': 'Attribut'\-Attribut wird ignoriert  
  
 Der Compiler ignoriert die Attribute `__fastcall`, **static** oder **inline** für eine Funktion \(Warnstufe 3\) oder für Daten \(Warnstufe 2\).  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  `__fastcall`\-Attribute werden mit Daten.  
  
2.  Attribute **static** oder **inline** mit **main**\-Funktion.