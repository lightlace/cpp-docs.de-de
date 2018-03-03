---
title: Linkertoolfehler Lnk2023 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2023
dev_langs:
- C++
helpviewer_keywords:
- LNK2023
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dfaac5729c014baff676772fb052bfbcf79489cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2023"></a>Linkertoolfehler LNK2023
Fehlerhafte Dll oder Einstiegspunkt \<Dll oder Einstiegspunkt >  
  
 Der Linker wird eine falsche Version von msobj90.dll geladen. Stellen Sie sicher, dass link.exe und msobj90.dll im Pfad über die gleiche Version verfügen.  
  
 Eine Abhängigkeit von msobj90.dll möglicherweise nicht vorhanden. Die Liste der Abhängigkeiten für msobj90.dll ist:  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 Überprüfen Sie Ihre Computer für alle anderen Kopien von msobj90.dll, die möglicherweise nicht mehr aktuell.