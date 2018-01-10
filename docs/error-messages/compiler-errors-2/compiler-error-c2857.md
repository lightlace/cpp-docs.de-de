---
title: Compilerfehler C2857 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2857
dev_langs: C++
helpviewer_keywords: C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c4bf637f0abb5affdb21deb8e081c8b5156afd88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2857"></a>Compilerfehler C2857
' #include "mit der YcDateiname angegebene Anweisung in der Quelldatei nicht gefunden  
  
 Die ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) Option gibt den Namen einer Include-Datei, die nicht in der Quelldatei kompiliert wird.  
  
 Dieser Fehler kann verursacht werden, indem eine `#include` -Anweisung in einem Block zur bedingten Kompilierung, die nicht kompiliert wird.