---
title: '#<a name="undef-directive-cc--microsoft-docs"></a>Undef-Direktive (C/C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#undef'
dev_langs: C++
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aee7babf895b72a5ff4f5fb1485e4bb118e95889
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="undef-directive-cc"></a>#undef-Anweisung (C/C++)
Entfernt einen Namen, der zuvor mit `#define` erstellt wurde (hebt die Definierung auf).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#undef   
identifier  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `#undef` -Direktive entfernt die aktuelle Definition der *Bezeichner*. Folglich weiteren Vorkommen *Bezeichner* werden vom Präprozessor ignoriert. So entfernen Sie ein Makro mit `#undef`, geben Sie nur das Makro *Bezeichner* ; Geben Sie eine Parameterliste nicht.  
  
 Sie können die `#undef`-Direktive auch auf einen Bezeichner anwenden, der keine vorherige Definition hat. Dadurch wird sichergestellt, dass der Bezeichner nicht definiert wird. Innerhalb von `#undef`-Anweisungen wird keine Makroersetzung durchgeführt.  
  
 Die `#undef`-Direktiven werden in der Regel paarweise mit `#define`-Direktiven verwendet, um einen Bereich in einem Quellprogramm zu erstellen, in dem ein Bezeichner eine besondere Bedeutung hat. Beispielsweise kann eine bestimmte Funktion des Quellprogramms Manifestkonstanten verwenden, um umgebungsspezifische Werte zu definieren, die sich nicht auf das übrige Programm auswirken. Die `#undef`-Direktive kann auch zusammen mit der `#if`-Direktive eine bedingte Kompilierung des Quellprogramms steuern. Finden Sie unter [#if-, #elif, #else- und #endif-Direktiven](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) für Weitere Informationen.  
  
 Im folgenden Beispiel entfernt die `#undef`-Direktive die Definitionen einer symbolischen Konstante und eines Makros. Beachten Sie, dass nur der Bezeichner des Makros angegeben wird.  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Microsoft-spezifisch**  
  
 Die Definition für Makros kann in der Befehlszeile mithilfe der "/U"-Option, gefolgt von den gewünschten Makronamen, aufgehoben werden. Die Auswirkungen dieses Befehls entspricht einer Folge von `#undef` *Makronamen* -Anweisungen am Anfang der Datei.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)