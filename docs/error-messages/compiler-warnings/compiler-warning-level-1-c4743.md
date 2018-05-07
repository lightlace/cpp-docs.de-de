---
title: Compilerfehler Warnung (Stufe 1) C4743 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4743
dev_langs:
- C++
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84b4d5f3aa465257d7efcf9f95584612214165b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4743"></a>Compilerwarnung (Stufe 1) C4743
"*Typ*'hat eine unterschiedliche Größe '*" file1 "*'und'*file2*": *Anzahl* und *Anzahl* Bytes  
  
 Eine externe Variable verwiesen wird, oder in zwei Dateien definiert verschiedene Typen in diesen Dateien hat und der Compiler bestimmt, die die Größe der Variablen im *"file1"* unterscheidet sich von der Größe der Variablen im *file2*.  
  
 Wichtige Fall wird diese Warnung für C++ ausgegeben werden kann. Wenn Sie dieselben Typen mit dem gleichen Namen in zwei verschiedenen Dateien deklarieren, wenn diese Deklarationen auf virtuelle Funktionen enthält, und wenn die Deklarationen nicht identisch sind, kann der Compiler Warnung C4744 für die virtuelle Funktion, die Tabellen ausgeben. Die Warnung tritt auf, weil es zwei verschiedene Größe virtuelle Funktion, die Tabellen für den gleichen Typ gibt und Linker muss wählen Sie eine von ihnen in der ausführbaren Datei integriert.  Es ist möglich, dass dies in Ihrem Programm Aufrufen der falschen virtuellen Funktions führen kann.  
  
 Um diese Warnung zu beheben, verwenden Sie die gleichen Typdefinition oder verwenden Sie unterschiedliche Namen für die Typen oder Variablen.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel enthält eine Definition des Typs.  
  
```  
// C4743a.cpp  
// compile with: /c  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
};  
  
void C::f1(void) {}  
void C::f2(void) {}  
void C::f3(void) {}  
C q;  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4743 generiert.  
  
```  
// C4743b.cpp  
// compile with: C4743a.cpp /W1 /GL /O2  
// C4743 expected  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
    virtual void f4(void);  
    virtual void f5(void);  
};  
  
void C::f4(void) {}  
void C::f5(void) {}  
C x;  
  
int main() {}   
```