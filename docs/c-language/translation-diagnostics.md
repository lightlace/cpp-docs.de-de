---
title: "Übersetzung: Diagnose | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: bb7f826be88ebec640a6f3b40b38478eea91ed36
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
