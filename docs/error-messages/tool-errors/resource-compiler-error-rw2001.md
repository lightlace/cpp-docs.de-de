---
title: "Ressourcencompiler: Fehler RW2001"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "RW2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2001"
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Fehler RW2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige Direktive in vorverarbeiteter RC\-Datei  
  
 Die RC\-Datei enthält eine **\#pragma**\-Direktive.  
  
 Verwenden Sie die **\#ifndef**\-Präprozessordirektive zusammen mit der **RC\_INVOKED**\-Konstante, die vom Ressourcencompiler beim Verarbeiten einer Includedatei definiert wird.  Platzieren Sie die **\#pragma**\-Direktive in einem Codeblock, der nicht verarbeitet wird, wenn die **RC\_INVOKED**\-Konstante definiert ist.  Code in diesem Block wird nur vom C\/C\+\+\-Compiler verarbeitet, nicht vom Ressourcencompiler.  Der folgende Beispielcode demonstriert diese Technik:  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 Die **\#pragma**\-Präprozessordirektive besitzt in einer RC\-Datei keine Bedeutung.  Die `#include`\-Präprozessordirektive wird häufig in einer RC\-Datei verwendet, um eine Headerdatei, entweder eine projektbasierte, benutzerdefinierte Headerdatei oder eine Standardheaderdatei, die von Microsoft mit einem Produkt bereitgestellt wird, einzuschließen.  Einige dieser Includedateien enthalten die **\#pragma**\-Direktive.  Da eine Headerdatei eine oder mehrere andere Headerdateien enthalten kann, ist möglicherweise nicht gleich zu erkennen, welche Datei die beanstandete **\#pragma**\-Direktive enthält.  
  
 Mit der **\#ifndef RC\-INVOKED**\-Technik kann das Einschließen von Headerdateien in projektbasierte Headerdateien gesteuert werden.