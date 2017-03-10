---
title: _crtDbgFlag | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4f4c3a874d59095d620a04d5ebb6ac88e2bdfa66
ms.lasthandoff: 02/24/2017

---
# <a name="crtdbgflag"></a>_crtDbgFlag
Das Flag **_crtDbgFlag** besteht aus fünf Bitfeldern, die steuern, wie Speicherbelegungen in der Debugversion des Heaps nachverfolgt, geprüft, gemeldet und gesichert werden. Die Bitfelder des Flags werden mithilfe der Funktion [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) festgelegt. Dieses Flag und seine Bitfelder werden in Crtdbg.h deklariert. Dieses Flag ist nur verfügbar, wenn das Flag [_DEBUG](../c-runtime-library/debug.md) in der Anwendung definiert wurde.  
  
 Weitere Informationen zur Verwendung dieses Flags in Verbindung mit anderen Debugfunktionen finden Sie unter [Berichtsfunktionen für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerungsflags](../c-runtime-library/control-flags.md)
