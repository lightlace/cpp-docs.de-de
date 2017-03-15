---
title: "Linkertoolfehler LNK2031 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2031"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2031"
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Linkertoolfehler LNK2031
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

p\/invoke konnte nicht für "Funktionsdeklaration" "ergänzter\_Name" generiert werden. In den Metadaten fehlt die Aufrufkonvention  
  
 Wenn eine systemeigene Funktion in ein reines Abbild importiert wird, unterscheiden sich die impliziten Aufrufkonventionen zwischen systemeigenen und reinen Kompilierungen.  Weitere Informationen zu reinen Bildern finden Sie unter [Reiner und überprüfbarer Code](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## Beispiel  
 In diesem Codebeispiel wird eine Komponente mit einer exportierten, systemeigen Funktion generiert, deren Aufrufkonvention implizit [\_\_cdecl](../../cpp/cdecl.md) ist.  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird ein reiner Client erstellt, der die systemeigene Funktion verwendet.  Die Aufrufkonvention unter **\/clr:pure** lautet jedoch [\_\_clrcall](../../cpp/clrcall.md).  Im folgenden Beispiel wird LNK2031 generiert.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie die systemeigene Funktion in einem reinen Bild verwendet wird.  Beachten Sie den expliziten **\_\_cdecl**\-Spezifizierer der Aufrufkonvention.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```