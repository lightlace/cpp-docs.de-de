---
title: Schwerwiegender Fehler C1307 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1307
dev_langs: C++
helpviewer_keywords: C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe97f1658a74b0db5985ed755bf387811f2c6d1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1307"></a>Schwerwiegender Fehler C1307
Das Programm wurde seit dem Erfassen der Profildaten bearbeitet.  
  
 Bei Verwendung [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), der Linker ein Eingabemodul, die nach/LTCG: PGINSTRUMENT neu kompiliert wurde erkannt und, dass das Modul bis zu dem Zeitpunkt geändert wurde, in denen nicht mehr vorhandenen Profildaten relevant sind. Beispielsweise, wenn in der neu kompilierten Modul Aufrufdiagramms geändert haben, generiert der Compiler C1307.  
  
 Zum Beheben dieses Fehlers führen Sie/LTCG: PGINSTRUMENT aus, wiederholen Sie alle Testläufe und führen Sie die/LTCG: PGOPTIMIZE. Wenn Sie nicht ausgeführt werden können, und wiederholen alle Testläufe/LTCG: PGINSTRUMENT ausgeführt wird, verwenden Sie/LTCG: PGUPDATE anstelle von/LTCG: PGOPTIMIZE, um das optimierte Image zu erstellen.