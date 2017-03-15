---
title: "Schwerwiegender Fehler C1308 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1308"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1308"
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Schwerwiegender Fehler C1308
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verknüpfen von Assemblys wird nicht unterstützt  
  
 netmodule. zulässig, wie als Eingabe für den Linker, jedoch keine Assembly.  Dieser Fehler kann generiert werden, wenn versucht wird, eine mit `/clr:safe` kompilierte Assembly zu verknüpfen.  
  
 Weitere Informationen finden Sie unter [NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).  
  
 Im folgenden Beispiel wird C1308 generiert:  
  
```  
// C1308.cpp  
// compile with: /clr:safe /LD  
public ref class MyClass {  
public:  
   int i;  
};  
```  
  
 und anschließend  
  
```  
// C1308b.cpp  
// compile with: /clr /link C1308b.obj C1308.dll  
// C1308 expected  
#using "C1308.dll"  
int main() {  
   MyClass ^ my = gcnew MyClass();  
}  
```