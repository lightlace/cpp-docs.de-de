---
title: -STACK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a82111ce950d14bc6b3e270ee9a658d806b28b62
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374075"
---
# <a name="stack"></a>/STACK
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option legt die Stapelgröße in Bytes fest, und lässt Argumente in decimal oder C-Notation angegeben. Durch die Option gilt nur für eine ausführbare Datei.  
  
 Die *reservieren* -Argument gibt die gesamte stapelzuordnung im virtuellen Arbeitsspeicher. EDITBIN rundet den angegebenen Wert in der nächsten 4 Bytes.  
  
 Das optionale `commit` -Argument vom Betriebssystem interpretiert wird. In Windows NT, Windows 95- und Windows 98 `commit` gibt die Menge an physikalischem Arbeitsspeicher, zu einem Zeitpunkt belegen. Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei. Eine höhere `commit` -Wert spart Zeit, wenn die Anwendung mehr Stapelspeicher benötigt, aber erhöht den Arbeitsspeicherbedarf und möglicherweise die Startzeit.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)