---
title: Schließlich | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 70057cad8ff5bca0606f06dd43eaa485834d2c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="finally"></a>finally
Zusätzlich zu `try` und `catch` -Klauseln, CLR-Ausnahmebehandlung unterstützt eine `finally` Klausel. Die Semantik ist identisch mit der `__finally` strukturierte Ausnahmebehandlung (SEH) blockieren. Ein `__finally` -Block folgen kann eine `try` oder `catch` Block.  
  
## <a name="remarks"></a>Hinweise  
 Der Zweck der `finally` Block wird zum Bereinigen von Ressourcen übrig bleiben, nachdem die Ausnahme aufgetreten ist. Beachten Sie, dass die `finally` Block wird immer ausgeführt, auch wenn keine Ausnahme ausgelöst wurde. Die `catch` Block wird nur ausgeführt, wenn eine verwaltete Ausnahme ausgelöst wird, innerhalb der zugeordneten `try` Block.  
  
 `finally` ist ein kontextbezogenes Schlüsselwort. finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md) für Weitere Informationen.  
  
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