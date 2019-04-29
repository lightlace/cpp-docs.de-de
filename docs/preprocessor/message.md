---
title: message
ms.date: 11/04/2016
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: e9383238fd308ec59a9767f56af1c07fc3cfcf07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371737"
---
# <a name="message"></a>message
Sendet ein Zeichenfolgenliteral an die Standardausgabe, ohne die Kompilierung zu beenden.

## <a name="syntax"></a>Syntax

```
#pragma message( messagestring )
```

## <a name="remarks"></a>Hinweise

Ein typisches Einsatzgebiet von der **Nachricht** Pragma ist zur Kompilierungszeit informationsmeldungen anzuzeigen.

Die *Messagestring* Parameter kann ein Makro, das ein Zeichenfolgenliteral erweitert, und Sie können diese Makros mit Zeichenfolgenliteralen in beliebiger Kombination verketten.

Wenn Sie ein vordefiniertes Makro im Verwenden der **Nachricht** Pragma sollte das Makro eine Zeichenfolge zurückgeben, andernfalls müssen Sie die Ausgabe des Makros in eine Zeichenfolge zu konvertieren.

Das folgende Codefragment verwendet den **Nachricht** Pragma, um Meldungen während der Kompilierung anzuzeigen:

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