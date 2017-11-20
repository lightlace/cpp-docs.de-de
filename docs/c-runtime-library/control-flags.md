---
title: Steuerungsflags | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.flags
dev_langs: C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8c6f58e345669cb1898bc2717a7e42ddc8e2539
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="control-flags"></a>Steuerungsflags
Die Debugversion der Microsoft C-Laufzeitbibliothek verwendet die folgenden Flags, um den Heapbelegungs- und Berichterstellungsprozess zu steuern. Weitere Informationen finden Sie unter [CRT-Debugverfahren](/visualstudio/debugger/crt-debugging-techniques).  
  
|Flag|Beschreibung|  
|----------|-----------------|  
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Ordnet die grundlegenden Heapfunktionen zu den entsprechenden Funktionen in der Debugversion zu.|  
|[_DEBUG](../c-runtime-library/debug.md)|Ermöglicht die Verwendung der Debugversionen der Laufzeitfunktionen.|  
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Steuert, wie der Debugheap-Manager die Belegungen nachverfolgt.|  
  
 Diese Flags können mit einer /D-Befehlszeilenoption oder einer `#define`-Direktive definiert werden. Wenn das Flag mit `#define` definiert wird, muss sich die Direktive vor der include-Anweisung der Headerdatei für die Routinedeklarationen befinden.  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Variablen und Standardtypen](../c-runtime-library/global-variables-and-standard-types.md)