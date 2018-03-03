---
title: 'Ressourcencompiler: Fehler RC2101 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d08e9ddb7b8cda127b1d05bfef52b52833534cb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2101"></a>Ressourcencompiler: Fehler RC2101
Ungültige Direktive in vorverarbeiteten RC-Datei  
  
 Die Ressourcencompiler-Datei enthält eine **#pragma** Richtlinie.  
  
 Verwenden der **#ifndef** Präprozessordirektive RC_INVOKED-Konstante, dass der Ressourcencompiler definiert, wenn er eine Includedatei verarbeitet. Ort der **#pragma** Richtlinie in einem Block von Code, der nicht verarbeitet wird, wenn die RC_INVOKED-Konstante definiert wird. Code im Block wird nur vom C/C++-Compiler und nicht vom Ressourcencompiler verarbeitet. Im folgenden Beispielcode wird diese Technik veranschaulicht:  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 Die **#pragma** Präprozessordirektive hat keine Bedeutung ein. RC-Datei. Die **#include** Präprozessordirektive wird häufig in verwendet ein. RC-Datei eine Headerdatei (projektbasierten benutzerdefinierte Headerdatei oder eine Standardheaderdatei mit einem der Produkte von Microsoft bereitgestellten) einschließen. Einige dieser Includedateien enthalten die **#pragma** Richtlinie. Eine Headerdatei kann eine oder mehrere andere Headerdateien, die Datei enthalten, die die auslösende enthält **#pragma** Richtlinie möglicherweise nicht sofort bemerkbar.  
  
 Die **#ifndef** RC_INVOKED Technik einschließlich Headerdateien in Headerdateien projektbasierten steuern kann.