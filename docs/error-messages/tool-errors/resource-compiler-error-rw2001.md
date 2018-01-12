---
title: 'Ressourcencompiler: Fehler RW2001 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW2001
dev_langs: C++
helpviewer_keywords: RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a14cd36ab87297cf5bc0aa547bdea5ef23260e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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