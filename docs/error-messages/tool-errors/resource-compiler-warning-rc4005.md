---
title: 'Ressourcencompiler: Warnung RC4005 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 724764e443d4ab999c1df1247e9f5572ebdb2078
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-warning-rc4005"></a>Ressourcencompiler: Warnung RC4005
'Bezeichner': Neudefinition von Makros  
  
 Der Bezeichner wird zweimal definiert. Der Compiler verwendet die zweite Makrodefinition.  
  
 Diese Warnung kann verursacht werden, indem Sie ein Makro definieren, in der Befehlszeile und im Code mit einem `#define` Richtlinie. Er kann auch von Makros aus Includedateien importiert verursacht werden.  
  
 Um die Warnung zu vermeiden, entfernen Sie eine der Definitionen oder verwenden eine `#undef` Richtlinie vor der zweiten Definition.