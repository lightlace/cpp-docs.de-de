---
title: "Sichern von verzögert geladenen Importen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3800d4863bc1aa3e3c847ff0cea886be2fede985
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dumping-delay-loaded-imports"></a>Sichern von verzögert geladenen Importen
Verzögert geladene Importe können mit gesicherte [Dumpbin/Imports](../../build/reference/imports-dumpbin.md) und als Standard importiert mit leicht unterschiedliche Informationen angezeigt. Sie werden in einem eigenen Bereich der-Sicherung getrennt und explizit als verzögert geladene Importe gekennzeichnet sind. Wenn Entladen von Informationen in das Bild vorhanden ist, wird dies vermerkt. Bindungsinformationen vorhanden ist, wird der Datums-/Zeitstempel der Ziel-DLL zusammen mit den gebundenen Adressen des Imports vermerkt.  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)