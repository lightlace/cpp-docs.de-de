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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 525f8c235a4c2500b09ac37a050d4b57fadc8fb9
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

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
