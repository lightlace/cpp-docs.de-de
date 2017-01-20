---
title: "Linkertoolfehler LNK1179"
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
  - "LNK1179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1179"
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige oder beschädigte Datei: COMDAT 'Dateiname' doppelt vorhanden  
  
 Ein Objektmodul enthält mindestens zwei gleichnamige COMDATs.  
  
 Dieser Fehler kann durch die Verwendung der [\/H](../../build/reference/h-restrict-length-of-external-names.md)\-Option auftreten, durch die die Länge externer Namen beschränkt wird, und durch die [\/Gy](../../build/reference/gy-enable-function-level-linking.md)\-Option, durch die die Funktionen in COMDATs gepackt werden.  
  
## Beispiel  
 Im folgenden Code sind die ersten acht Zeichen von `function1` und `function2` identisch.  Durch die Kompilierung mit **\/Gy** und **\/H8** entsteht ein Bindungsfehler.  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```