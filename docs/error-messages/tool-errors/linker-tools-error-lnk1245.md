---
title: Linkertoolfehler Lnk1245 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 142d88489748f30308395d64f3db78178a9b856f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1245"></a>Linkertoolfehler LNK1245
Ungültiges Subsystem 'Subsystem' angegeben. / SUBSYSTEM muss WINDOWS, WINDOWSCE oder Konsole sein.  
  
 ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) wurde verwendet, um das Objekt zu kompilieren und eine der folgenden Bedingungen "true" war:  
  
-   Ein benutzerdefinierter Einstiegspunkt wurde definiert ([/Entry](../../build/reference/entry-entry-point-symbol.md)), sodass der Linker kein Subsystem ableiten kann.  
  
-   Ein Wert wurde zum Übergeben der [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) Linkeroption, die nicht für Objekte mit "/ CLR" gültig ist.  
  
 Die Auflösung werden in beiden Fällen geben Sie einen gültigen Wert für die/Subsystem (Linkeroption).