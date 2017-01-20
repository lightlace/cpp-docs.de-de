---
title: "Compilerfehler C3121"
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
  - "C3121"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3121"
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3121
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

GUID kann für die Klasse 'Klassenname' nicht geändert werden  
  
 Sie haben versucht, die Klassen\-ID mit [\_\_declspec\(uuid\)](../../cpp/uuid-cpp.md) zu ändern.  
  
 Der folgende Code generiert z. B. C3121:  
  
```  
// C3121.cpp  
[emitidl];  
[module(name="MyLibrary")];  
  
[coclass, uuid="00000000-0000-0000-0000-111111111111"]  
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121  
{  
};  
int main()  
{  
}  
```