---
title: "Compilerfehler C3828 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3828"
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Objekttyp“: Positionierungsargumente sind während des Erstellens von Instanzen von verwalteten oder WinRT\-Klassen nicht zulässig.  
  
 Wenn Sie ein Objekt des verwalteten oder des Windows\-Runtime\-Typs erstellen, dürfen Sie die Positionierungsform des [ref new, gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md)\- oder [new](../../cpp/new-operator-cpp.md)\-Operators nicht verwenden.  
  
 Im folgenden Beispiel wird C3828 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```