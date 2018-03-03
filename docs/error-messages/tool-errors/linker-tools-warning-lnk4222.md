---
title: Linkertoolwarnung Lnk4222 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a54c452a5df6f99260d6d01fbf4bb9f2f17b955
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4222"></a>Linkertoolwarnung LNK4222
exportiertes Symbol 'Symbol' sollte eine Ordinalzahl nicht zugewiesen werden  
  
 Die folgenden Symbole darf nicht nach Ordnungszahl exportiert werden:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 Diese Funktionen befinden sich immer anhand des Namens, mit `GetProcAddress`. Der Linker warnt diese Art der Export ist, da es zu einem größeren Bilds führen kann. Dies kann passieren, wenn der Bereich ordinal Berichten mit relativ wenigen Exporten groß ist. Ein auf ein Objekt angewendeter  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 ist erforderlich, dass 100 in der Exporttabelle für die Adresse mit 98 davon (2-99) nur Abdeckung slots. Andererseits  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 Sie benötigen zwei Steckplätze. (Beachten Sie, dass Sie auch mit exportieren können der [/EXPORT](../../build/reference/export-exports-a-function.md) (Linkeroption).)