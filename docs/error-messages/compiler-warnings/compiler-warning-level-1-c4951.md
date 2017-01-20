---
title: "Compilerwarnung (Stufe 1) C4951"
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
  - "C4951"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4951"
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4951
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Funktion" wurde bearbeitet, seit die Profildaten erfasst wurden. Die Funktionsprofildaten werden nicht verwendet.  
  
 Eine Funktion wurde in einem Eingabemodul für [\/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md) bearbeitet, sodass die Profildaten jetzt ungültig sind. Das Eingabemodul wurde nach **\/LTCG:PGINSTRUMENT** neu kompiliert und verfügt über eine Funktion \(***Funktion***\) mit einer anderen Ablaufsteuerung als der, die zum Zeitpunkt des **\/LTCG:PGINSTRUMENT**\-Vorgangs im Modul enthalten war.  
  
 Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie **\/LTCG:PGINSTRUMENT** aus, wiederholen alle Testläufe und führen **\/LTCG:PGOPTIMIZE** aus.  
  
 Bei Verwendung von **\/LTCG:PGOPTIMIZE** würde diese Warnung durch einen Fehler ersetzt.