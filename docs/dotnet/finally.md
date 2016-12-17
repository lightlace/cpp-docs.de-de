---
title: "finally"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "finally-Schlüsselwort [C++]"
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: 9
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# finally
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Neben `try` und `catch` CLR\-Ausnahmebehandlung Klauseln unterstützt eine `finally`\-Klausel.  Die Semantik entspricht dem `__finally`\-Block in der strukturierten Ausnahmebehandlung \(SEH\) identisch.  Ein `__finally`\-Block kann einem `try` oder `catch`\-Block folgen.  
  
## Hinweise  
 Der Zweck des `finally`\-Blocks ist, alle Ressourcen zu bereinigen, die nach der Ausnahme verbleiben, aufgetreten ist.  Beachten Sie, dass der `finally`\-Block wird immer ausgeführt, wenn keine Ausnahme ausgelöst wurde.  Der `catch`\-Block wird nur ausgeführt, wenn eine verwaltete Ausnahme innerhalb des Blocks zugeordneten `try` ausgelöst wird.  
  
 `finally` ist ein kontextbezogenes Schlüsselwort. Weitere Informationen siehe [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt einen einfachen `finally`\-Block:  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
  **in der Erfassung**  
**MyException**  
**in einer finally\-Klausel**   
## Siehe auch  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)