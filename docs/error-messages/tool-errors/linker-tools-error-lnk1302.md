---
title: Linkertoolfehler Lnk1302 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1302
dev_langs: C++
helpviewer_keywords: LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a5b9201608d6d457288c7ade9376147da08bcb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1302"></a>Linkertoolfehler LNK1302
Verknüpfen sichere NETMODULE-Dateien nur zu unterstützen; Datei .netmodule kann nicht verknüpft  
  
 Eine NETMODULE-Datei (kompiliert mit **/ln**) wurde in den Versuch eines Benutzers zum Aufrufen der MSIL-Verknüpfung an den Linker übergeben.  Ein C++-Modul ist gültig für MSIL verknüpfen, wenn die Kompilierung mit **/CLR: safe**.  
  
 Um diesen Fehler zu beheben, kompilieren Sie mit **/CLR: safe** MSIL Verknüpfen aktivieren, oder übergeben der **"/ CLR"** oder **/CLR: pure** OBJ-Datei an den Linker anstelle des Moduls.  
  
 Weitere Informationen finden Sie unter  
  
-   [/ LN (Erstellen von MSIL-Modul)](../../build/reference/ln-create-msil-module.md)  
  
-   [.NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)