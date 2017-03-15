---
title: "Linkertoolwarnung LNK4224 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4224"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4224"
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Linkertoolwarnung LNK4224
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Option wird nicht mehr unterstützt; wird ignoriert  
  
 Eine ungültige, veraltete Linkeroption wurde angegeben und ignoriert.  
  
 LNK4224 kann beispielsweise auftreten, wenn in .obj eine \/comment\-Direktive vorhanden ist.  Die \/comment\-Direktive muss unter Verwendung der veralteten exestr\-Option über das [Kommentar](../../preprocessor/comment-c-cpp.md)\-Pragma hinzugefügt worden sein.  Verwenden Sie dumpbin [\/ALL](../../build/reference/all.md), um die Linkerdirektiven in einer OBJ\-Datei anzuzeigen.  
  
 Ändern Sie nach Möglichkeit die Quelle für das .obj, und entfernen Sie das Pragma.  Wenn Sie diese Warnung jedoch ignorieren, kann eine mit **\/clr:pure** kompilierte .executable möglicherweise nicht erwartungsgemäß ausgeführt werden.  
  
## Beispiel  
 Im folgenden Beispiel wird LNK4224 generiert.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```