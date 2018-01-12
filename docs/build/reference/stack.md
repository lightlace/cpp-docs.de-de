---
title: -STACK | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /stack
dev_langs: C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 21438bf8f214c10525aa7e9a5829f835b8a33f2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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