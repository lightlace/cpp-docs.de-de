---
title: message-Pragma
ms.date: 08/29/2019
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: 48605fbef3b6d81c140e663e950429cd3dcf9b19
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218791"
---
# <a name="message-pragma"></a>message-Pragma

Sendet ein Zeichenfolgenliteral an die Standardausgabe, ohne die Kompilierung zu beenden.

## <a name="syntax"></a>Syntax

> **#pragma Meldung (** Meldungs *Zeichenfolge* **)**

## <a name="remarks"></a>Hinweise

Eine typische Verwendung des **Message** -Pragmas besteht in der Anzeige von Informationsmeldungen zur Kompilierzeit.

Der *Message-String-* Parameter kann ein Makro sein, das zu einem zeichenfolgenliteralerweitert wird, und Sie können solche Makros mit Zeichenfolgenliteralen in beliebiger Kombination verketten.

Wenn Sie ein vordefiniertes Makro im **Message** -Pragma verwenden, sollte das Makro eine Zeichenfolge zurückgeben. Andernfalls müssen Sie die Ausgabe des Makros in eine Zeichenfolge konvertieren.

Das folgende Code Fragment verwendet das **Message** -Pragma, um Meldungen während der Kompilierung anzuzeigen:

```cpp
// pragma_directives_message1.cpp
// compile with: /LD
#if _M_IX86 >= 500
#pragma message("_M_IX86 >= 500")
#endif

#pragma message("")

#pragma message( "Compiling " __FILE__ )
#pragma message( "Last modified on " __TIMESTAMP__ )

#pragma message("")

// with line number
#define STRING2(x) #x
#define STRING(x) STRING2(x)

#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")

#pragma message("")
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
