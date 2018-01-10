---
title: Compilerfehler C3505 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3505
dev_langs: C++
helpviewer_keywords: C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7b13350ea7a2ffaf232e990bd3ade42d0c44a6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3505"></a>Compilerfehler C3505

> Typbibliothek kann nicht geladen werden "*Guid*"  
  
C3505 kann verursacht werden, wenn Sie die 32-Bit, X86 gehostete-Cross-Compiler für 64-Bit-Version ausgeführt werden, X64 Ziele auf einem 64-Bit-Computer, da der Compiler unter WOW64 ausgeführt wird, und können nur von der 32-Bit-Registrierungsstruktur lesen.  
  
Sie können diesen Fehler beheben, durch die Erstellung von 32-Bit und 64-Bit-Versionen der Typbibliothek, die Sie importieren möchten, und registrieren beide.  Oder Sie können die systemeigenen 64-Bit-Compilers, wofür Sie ändern muss Ihre **VC++-Verzeichnisse** Eigenschaft in der IDE auf die 64-Bit-Compiler zeigen.  
  
Weitere Informationen finden Sie unter  
  
-   [Vorgehensweise: Aktivieren eines 64-Bit-Visual C++-Toolsets auf der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [Vorgehensweise: Konfigurieren von Visual C++-Projekten für 64-Bit-x64-Zielplattformen](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)