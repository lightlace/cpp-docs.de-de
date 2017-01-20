---
title: "Compilerfehler C2778"
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
  - "C2778"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2778"
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2778
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

GUID in \_\_declspec\(uuid\(\)\) falsch formatiert  
  
 Für das erweiterte [uuid](../../cpp/uuid-cpp.md)\-Attribut wurde eine falsche GUID bereitgestellt.  
  
 Die bereitgestellte GUID muss einer Zeichenfolge von hexadezimalen Zahlen in folgendem Format entsprechen:  
  
```  
// C2778a.cpp  
// compile with: /c  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};  
```  
  
 Das erweiterte `uuid`\-Attribut akzeptiert von [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589) erkannte Zeichenfolgen mit und ohne Klammertrennzeichen.  
  
 Im folgenden Beispiel wird C2778 generiert:  
  
```  
// C2778b.cpp  
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778  
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778  
```