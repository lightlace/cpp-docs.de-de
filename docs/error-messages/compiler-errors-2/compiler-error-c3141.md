---
title: "Compilerfehler C3141"
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
  - "C3141"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3141"
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3141
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface\_name': Schnittstellen unterstützen nur die öffentliche Vererbung  
  
 Schnittstellen, die mit dem Schlüsselwort [interface \(oder \_\_interface\)](../../cpp/interface.md) definiert wurden, unterstützen nur die öffentliche Vererbung.  
  
 Im folgenden Beispiel wird C3141 generiert:  
  
```  
// C3141.cpp  
__interface IBase {};  
__interface IDerived1 : protected IBase {};  // C3141  
__interface IDerived2 : private IBase {};    // C3141  
```