---
title: 'Ressourcencompiler: Fehler RW2001 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW2001
dev_langs:
- C++
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 077260b615d0a5adf32278d8857df5b8f74b7e5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-error-rw2001"></a>Ressourcencompiler: Fehler RW2001
Ungültige Direktive in vorverarbeiteten RC-Datei  
  
 Die RC-Datei enthält eine **#pragma** Richtlinie.  
  
 Verwenden der **#ifndef** Präprozessordirektive mit der **RC_INVOKED** konstant, dass der Ressourcencompiler definiert, wenn er eine Includedatei verarbeitet. Ort der **#pragma** -Direktive innerhalb eines Codeblocks, der nicht verarbeitet, wenn die **RC_INVOKED** Konstante definiert ist. Code im Block wird nur vom C/C++-Compiler und nicht vom Ressourcencompiler verarbeitet. Im folgenden Beispielcode wird diese Technik veranschaulicht:  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 Die **#pragma** Präprozessordirektive hat keine Bedeutung ein. RC-Datei. Die **#include** Präprozessordirektive wird häufig in verwendet ein. RC-Datei eine Headerdatei (projektbasierten benutzerdefinierte Headerdatei oder eine Standardheaderdatei mit einem der Produkte von Microsoft bereitgestellten) einschließen. Einige dieser Includedateien enthalten die **#pragma** Richtlinie. Eine Headerdatei kann eine oder mehrere andere Headerdateien, die Datei enthalten, die die auslösende enthält **#pragma** Richtlinie möglicherweise nicht sofort bemerkbar.  
  
 Die **#ifndef RC_INVOKED** Technik einschließlich Headerdateien in Headerdateien projektbasierten steuern kann.