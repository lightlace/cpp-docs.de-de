---
title: "Compilerwarnung C4801"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4801"
ms.assetid: 05b29dff-15ef-42ca-9712-dc993afc4fd6
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rückgabe von Verweis kann nicht überprüft werden: Ursache  
  
 Sie können keinen Verweis für Nachverfolgung in einer lokalen Variable speichern und anschließend überprüfbar zurückgeben.  
  
 Ein Verweis kann nur dann überprüfbar zurückgegeben werden, wenn er bei der Überprüfung vom Erstellungspunkt bis zum Rückgabepunkt nachverfolgt werden kann, und wenn er auf ein Element in einem Array, einen Member oder eine Klasse verweist.  
  
 Weitere Informationen finden Sie unter [Peverify.exe \(PEVerify Tool\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md).  
  
 Ein Verweis muss von der Erstellung bis zur Rückgabe auf dem Stapel verbleiben, um überprüfbar zu sein.  
  
 C4801 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit `#pragma warning` oder **\/wd** deaktivieren. Weitere Informationen finden Sie unter [warning](../../preprocessor/warning.md) oder [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Warnstufe\)](../../build/reference/compiler-option-warning-level.md).  
  
## Beispiel  
 C4801 wird erzeugt, wenn bei der Überprüfung die akzeptierte Adresse nicht erkannt werden kann, und es sich aus diesem Grund um einen nicht überprüfbaren Verweis handeln könnte.  Im folgenden Beispiel wird C4801 generiert.  
  
```  
// C4801.cpp  
// compile with: /clr:safe /c  
int% f(int% p) {  
   return p;   // C4801  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4801 generiert.  
  
```  
// C4801_b.cpp  
// compile with: /clr:safe /c  
  
int% f(int i, array<int>^ ar) {  
   int x;  
   int% bri = x;   // cannot return a byref to a local.  
   if (i < ar->Length) {  
      bri = ar[i];   // this byref is ok.  
   }  
  
   return bri;   // C4801 not returned within the basic block  
}  
```  
  
## Beispiel  
 C4801 wird unter Umständen auch ausgegeben, wenn Sie versuchen, eine Dereferenzierung durchzuführen und einen Verweiswert in einem try\-Block zurückzugeben.  Dadurch wird nicht überprüfbarer Code erstellt, da der Stapel am Ende eines try\-Blocks und damit auch alle Rückgabewerte auf dem Stapel zerstört werden.  Stellen Sie stattdessen sicher, dass keine Ausnahme ausgelöst wird, indem Sie den Referenztyp dereferenzieren und ihn einer Variablen zuweisen.  Dereferenzieren Sie anschließend am Ende der Funktion den Referenztyp erneut, und geben Sie ihn zurück.  
  
 Im folgenden Beispiel wird C4801 generiert.  
  
```  
// C4801_c.cpp  
// compile with: /clr:safe  
using namespace System;  
  
ref class StackEmptyException : public System::Exception {};  
ref class StackFullException : public System::Exception {};  
  
template <typename T>  
ref struct Stack {  
  
   Stack() {  
      topElem = -1;   // initialize stack  
      stackPtr = gcnew array<T>(10);  
   }  
  
   void push(const T%);  
   T% top();  
  
private:  
   int topElem;    
   array<T>^ stackPtr;    
};  
  
template <typename T>   
T% Stack<T>::top() {  
   try {  
      return stackPtr[topElem];   // C4801  
      // Try the following line instead.  
      // T% deadstore = stackPtr[topElem] ;  
   }  
  
   catch (System::IndexOutOfRangeException ^ e) {  
      throw gcnew StackEmptyException();  
   }  
  
   catch (System::Exception ^ e) {  
      throw;  
   }  
  
   return stackPtr[topElem] ;  
}  
  
int main() {  
   typedef Stack<Int32> IntStack;  
   IntStack ^ is = gcnew IntStack();  
  
   int i = 1;  
   while (1) {  
      try {  
         is->push(i++);  
      }  
      catch (System::Exception ^ e) {  
         break;  
      }  
      Console::Write("{0} ", is->top());  
   }  
}  
```