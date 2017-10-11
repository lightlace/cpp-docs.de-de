---
title: _crtDbgFlag | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 559dba68c8c171fbc84be17e64c2628b4bbf5011
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="crtdbgflag"></a>_crtDbgFlag
Das Flag **_crtDbgFlag** besteht aus fünf Bitfeldern, die steuern, wie Speicherbelegungen in der Debugversion des Heaps nachverfolgt, geprüft, gemeldet und gesichert werden. Die Bitfelder des Flags werden mithilfe der Funktion [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) festgelegt. Dieses Flag und seine Bitfelder werden in Crtdbg.h deklariert. Dieses Flag ist nur verfügbar, wenn das Flag [_DEBUG](../c-runtime-library/debug.md) in der Anwendung definiert wurde.  
  
 Weitere Informationen zur Verwendung dieses Flags in Verbindung mit anderen Debugfunktionen finden Sie unter [Berichtsfunktionen für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerungsflags](../c-runtime-library/control-flags.md)
