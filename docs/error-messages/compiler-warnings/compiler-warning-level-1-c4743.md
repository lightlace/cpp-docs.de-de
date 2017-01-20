---
title: "Compilerwarnung (Stufe 1) C4743"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4743"
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'*type*' hat eine unterschiedliche Größe in '*file1*' und in '*file2*': *number* und *number* Bytes  
  
 Eine externe Variable, die in zwei Dateien referenziert oder definiert wurde, hat in diesen Dateien verschiedene, und bestimmten Compiler, dass die Größe der Variablen in *file1* von der Größe der Variablen in *file2* unterscheidet.  
  
 Die Ausgabe dieser Warnung für C\+\+ stellt einen wichtigen Fall dar.  Der Compiler kann die Warnung C4744 für virtuelle Funtkionstabellen ausgeben, wenn die folgenden Umstände vorliegen: Es werden in zwei verschiedenen Dateien dieselben Typen mit demselben Namen deklariert und diese Deklarationen enthalten virtuelle Funktionen und sind verschieden.  Die Warnung tritt auf, da zwei virtuelle Funktionstabellen verschiedener Größe für denselben Typ vorliegen, und der Linker muss eine dieser Tabellen für die Einbindung in der ausführbaren Datei auswählen.  Es besteht die Möglichkeit, dass aus diesem Grund durch das Programm die falsche virtuelle Funktion aufgerufen wird.  
  
 Um diese Warnung zu verhindern, verwenden Sie für die Typen oder Variablen entweder dieselbe Typdefinition oder verschiedene Namen.  
  
## Beispiel  
 In diesem Beispiel wird eine einzelne Typdefinition verwendet.  
  
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
  
## Beispiel  
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