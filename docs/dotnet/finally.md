---
title: "Schließlich | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd357c8eeed9eddc6940ce02de6e5d2b4f8c68d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="finally"></a>finally
Zusätzlich zu `try` und `catch` -Klauseln, CLR-Ausnahmebehandlung unterstützt eine `finally` Klausel. Die Semantik ist identisch mit der `__finally` strukturierte Ausnahmebehandlung (SEH) blockieren. Ein `__finally` -Block folgen kann eine `try` oder `catch` Block.  
  
## <a name="remarks"></a>Hinweise  
 Der Zweck der `finally` Block wird zum Bereinigen von Ressourcen übrig bleiben, nachdem die Ausnahme aufgetreten ist. Beachten Sie, dass die `finally` Block wird immer ausgeführt, auch wenn keine Ausnahme ausgelöst wurde. Die `catch` Block wird nur ausgeführt, wenn eine verwaltete Ausnahme ausgelöst wird, innerhalb der zugeordneten `try` Block.  
  
 `finally`ist ein kontextbezogenes Schlüsselwort. finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine einfache `finally` blockieren:  
  
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
  
```Output  
in catch  
MyException  
in finally  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)