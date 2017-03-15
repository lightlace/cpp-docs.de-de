---
title: "noreturn | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noreturn_cpp"
  - "noreturn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], noreturn"
  - "noreturn __declspec-Schlüsselwort"
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# noreturn
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Dieses `__declspec`\-Attribut weist den Compiler an, dass keine Funktion zurückgegeben wird.  Folglich weiß der Compiler, dass der Code, der einem Aufruf einer **\_\_declspec\(noreturn\)**\-Funktion folgt, nicht erreichbar ist.  
  
 Wenn der Compiler eine Funktion mit einem Kontrollpfad findet, die keinen Wert zurückgibt, wird eine Warnung \(C4715\) oder Fehlermeldung \(C2202\) generiert.  Wenn der Kontrollpfad wegen einer Funktion, die nie zurückgegeben wird, nicht erreicht werden kann, können Sie **\_\_declspec\(noreturn\)** verwenden, um diese Warnung bzw. diesen Fehler zu verhindern.  
  
> [!NOTE]
>  Das Hinzufügen von **\_\_declspec\(noreturn\)** zu einer Funktion, die zurückgegeben werden soll, kann ein nicht definiertes Verhalten zur Folge haben.  
  
## Beispiel  
 Im folgenden Beispiel enthält die **else**\-Klausel keine return\-Anweisung.  Das Deklarieren von `fatal` as **\_\_declspec\(noreturn\)** vermeidet einen Fehler oder eine Warnmeldung.  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)