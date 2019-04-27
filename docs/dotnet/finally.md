---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: f7db4320cf901412e3a9e3de682d0cfbcc9f23bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223013"
---
# <a name="finally"></a>finally

Zusätzlich zu `try` und `catch` -Klauseln sowie in CLR-Ausnahmebehandlung unterstützt eine `finally` Klausel. Die Semantik ist identisch mit der `__finally` -block in strukturierte Ausnahmebehandlung (SEH). Ein `__finally` blockieren kann folgen einem `try` oder `catch` Block.

## <a name="remarks"></a>Hinweise

Der Zweck der `finally` Block ist zum Bereinigen von Ressourcen übrig bleiben, nachdem die Ausnahme aufgetreten ist. Beachten Sie, dass die `finally` Block wird immer ausgeführt, auch wenn keine Ausnahme ausgelöst wurde. Die `catch` Block wird nur ausgeführt, wenn eine verwaltete Ausnahme ausgelöst wird, in der zugeordneten `try` Block.

`finally` ist ein kontextbezogenes Schlüsselwort. finden Sie unter [Kontextbezogene Schlüsselwörter](../extensions/context-sensitive-keywords-cpp-component-extensions.md) für Weitere Informationen.

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

[Ausnahmebehandlung](../extensions/exception-handling-cpp-component-extensions.md)
