---
title: Linkertoolfehler Lnk1302 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa84a411f91303c84acb44e2e6c0ab3d975e19f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299418"
---
# <a name="linker-tools-error-lnk1302"></a>Linkertoolfehler LNK1302
Verknüpfen sichere NETMODULE-Dateien nur zu unterstützen; Datei .netmodule kann nicht verknüpft  
  
 Eine NETMODULE-Datei (kompiliert mit **/ln**) wurde in den Versuch eines Benutzers zum Aufrufen der MSIL-Verknüpfung an den Linker übergeben.  Ein C++-Modul ist gültig für MSIL verknüpfen, wenn die Kompilierung mit **/CLR: safe**.  
  
 Um diesen Fehler zu beheben, kompilieren Sie mit **/CLR: safe** MSIL Verknüpfen aktivieren, oder übergeben der **"/ CLR"** oder **/CLR: pure** OBJ-Datei an den Linker anstelle des Moduls.  
  
 Weitere Informationen finden Sie unter  
  
-   [/LN (MSIL-Modul erstellen)](../../build/reference/ln-create-msil-module.md)  
  
-   [.NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)