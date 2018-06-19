---
title: Check_stack | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
dev_langs:
- C++
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b393030961aa4695a16a9b50d49d0cae64cc4e0c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849768"
---
# <a name="checkstack"></a>check_stack
Weist den Compiler an, stapelüberprüfungen deaktivieren können, wenn **deaktiviert** (oder **-**) angegeben wird, oder wenn stapelüberprüfungen zu deaktivieren **auf** (oder **+**) angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | -}  
```  
  
## <a name="remarks"></a>Hinweise  
 Wird kein Argument angegeben ist, werden Stapelüberprüfungen gemäß der Standardeinstellung behandelt. Dieses Pragma tritt mit der ersten Funktionsdefinition in Kraft, nachdem das Pragma angezeigt wird. Stapelüberprüfungen sind weder ein Bestandteil von Makros noch von Funktionen, die inline generiert werden.  
  
 Wenn Sie ein Argument für die **Check_stack** Pragma stapelüberprüfung wird in der Befehlszeile angegebene Verhalten wiederhergestellt. Weitere Informationen finden Sie unter [Compilerreferenz](../build/reference/compiler-options.md). Die Interaktion der **#pragma Check_stack** und [/GS](../build/reference/gs-control-stack-checking-calls.md) Option wird in der folgenden Tabelle zusammengefasst.  
  
### <a name="using-the-checkstack-pragma"></a>Verwenden des check_stack-Pragmas  
  
|Syntax|Kompiliert mit der<br /><br /> /Gs-Option?|Aktion|  
|------------|------------------------------------|------------|  
|**#pragma Check_stack ()** oder<br /><br /> **#pragma check_stack**|Ja|Deaktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|  
|**#pragma Check_stack ()** oder<br /><br /> **#pragma check_stack**|Nein|Aktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|  
|**#pragma check_stack(on)**<br /><br /> oder **#pragma Check_stack +**|"Ja" oder "Nein"|Aktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|  
|**#pragma check_stack(off)**<br /><br /> oder **#pragma Check_stack -**|"Ja" oder "Nein"|Deaktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)