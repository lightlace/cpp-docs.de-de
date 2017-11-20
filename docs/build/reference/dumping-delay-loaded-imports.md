---
title: "Sichern von verzögert geladenen Importen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2104165bf466473d89270eb502e3357713579f38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="dumping-delay-loaded-imports"></a>Sichern von verzögert geladenen Importen
Verzögert geladene Importe können mit gesicherte [Dumpbin/Imports](../../build/reference/imports-dumpbin.md) und als Standard importiert mit leicht unterschiedliche Informationen angezeigt. Sie werden in einem eigenen Bereich der-Sicherung getrennt und explizit als verzögert geladene Importe gekennzeichnet sind. Wenn Entladen von Informationen in das Bild vorhanden ist, wird dies vermerkt. Bindungsinformationen vorhanden ist, wird der Datums-/Zeitstempel der Ziel-DLL zusammen mit den gebundenen Adressen des Imports vermerkt.  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)