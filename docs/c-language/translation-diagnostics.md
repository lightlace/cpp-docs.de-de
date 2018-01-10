---
title: "Übersetzung: Diagnose | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 10349357fa0411357b702ff48ff9407c1f5b91e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="translation-diagnostics"></a>Übersetzung: Diagnose
**ANSI 2.1.1.3** Wie eine Diagnose identifiziert wird  
  
 Microsoft C erzeugt Fehlermeldungen in der Form:  
  
```  
  
filename( line-number ) : diagnostic Cnumbermessage  
```  
  
 Hierbei ist *filename* der Name der Quelldatei, in der der Fehler aufgetreten ist; *line-number* die Nummer der Zeile, in der der Compiler den Fehler festgestellt hat; `diagnostic` entweder „error“ oder „warning“; `number` eine eindeutige vierstellige Zahl (der ein **C** vorangestellt ist, wie in der Syntax kenntlich gemacht), die den Fehler bzw. die Warnung angibt; `message` eine erläuternde Meldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementation-Defined Behavior (Durch die Implementierung definiertes Verhalten)](../c-language/implementation-defined-behavior.md)