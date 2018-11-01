---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: 5849a24d7b5d3d4f4a6d24d8cab3dd32f9d1de14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490765"
---
# <a name="finally"></a>finally

Zusätzlich zu `try` und `catch` -Klauseln sowie in CLR-Ausnahmebehandlung unterstützt eine `finally` Klausel. Die Semantik ist identisch mit der `__finally` -block in strukturierte Ausnahmebehandlung (SEH). Ein `__finally` blockieren kann folgen einem `try` oder `catch` Block.

## <a name="remarks"></a>Hinweise

Der Zweck der `finally` Block ist zum Bereinigen von Ressourcen übrig bleiben, nachdem die Ausnahme aufgetreten ist. Beachten Sie, dass die `finally` Block wird immer ausgeführt, auch wenn keine Ausnahme ausgelöst wurde. Die `catch` Block wird nur ausgeführt, wenn eine verwaltete Ausnahme ausgelöst wird, in der zugeordneten `try` Block.

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