---
title: Linkertoolwarnung Lnk4222 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 359af4c4d3b1079b2d56f108bff0ee1488ea71f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302148"
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