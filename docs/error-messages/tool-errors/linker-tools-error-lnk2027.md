---
title: Linkertoolfehler Lnk2027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156310a0d21651b9fd2ee6002ace419db4996681
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2027"></a>Linkertoolfehler LNK2027
nicht aufgelöste Modulverweis 'Modul'  
  
 Eine Datei, die an den Linker übergeben hat eine Abhängigkeit auf ein Modul, das weder mit angegeben wurden **ASSEMBLYMODULE** noch direkt an den Linker übergeben.  
  
 Um LNK2027 zu beheben, führen Sie eine der folgenden:  
  
-   Übergeben Sie nicht an den Linker die Datei, die das Modul abhängig ist.  
  
-   Geben Sie das Modul mit **ASSEMBLYMODULE**.  
  
-   Wenn das Modul eine sichere NETMODULE-Datei ist, übergeben Sie das Modul direkt an dem Linker.  
  
 Weitere Informationen finden Sie unter [ASSEMBLYMODULE (Hinzufügen einer MSIL-Modul zur Assembly)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) und [NETMODULE-Dateien als Linkereingabe](../../build/reference/netmodule-files-as-linker-input.md).