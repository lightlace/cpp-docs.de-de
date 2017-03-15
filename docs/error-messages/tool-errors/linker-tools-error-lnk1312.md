---
title: "Linkertoolfehler LNK1312 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1312"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1312"
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Linkertoolfehler LNK1312
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige oder beschädigte Datei: Assembly konnte nicht importiert werden  
  
 Beim Erstellen einer Assembly wurde eine Datei, bei der es sich nicht um ein Modul oder eine Assembly handelt, das\/die mit **\/clr** kompiliert wurde, an die Linkeroption **\/ASSEMBLYMODULE** übergeben.  Wenn Sie eine Objektdatei an **\/ASSEMBLYMODULE** übergeben haben, übergeben Sie das Objekt direkt an den Linker und nicht an **\/ASSEMBLYMODULE**.  
  
## Beispiel  
 Im folgenden Beispiel wurde die OBJ\-Datei erstellt.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird LNK1312 generiert.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```