---
title: '#Line-Direktive (C/C++)'
ms.date: 10/18/2017
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: ad0fe1514e89b861bab046652b1768862cc8045b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383775"
---
# <a name="line-directive-cc"></a>#line-Anweisung (C/C++)

Die **#line** -Direktive weist den Präprozessor an, den Compiler intern gespeicherte Zeilennummer und den Dateinamen in einen angegebenen Zeilennummer und den Dateinamen zu ändern.

## <a name="syntax"></a>Syntax

> **#line** *digit-sequence* ["*filename*"]

## <a name="remarks"></a>Hinweise

Der Compiler verwendet die Zeilennummer und den optionalen Dateinamen, um auf Fehler zu verweisen, die während der Kompilierung gefunden werden. Die Zeilennummer verweist normalerweise auf die aktuelle Eingabezeile, und der Dateiname verweist auf die aktuelle Eingabedatei. Nach der Verarbeitung jeder Zeile wird die Zeilennummer erhöht.

Die *Ziffernfolge* Wert kann eine beliebige Integerkonstante sein. Makroersetzungen können für die Vorverarbeitungstoken durchgeführt werden, das Ergebnis muss jedoch anhand der richtigen Syntax ausgewertet werden. Die *Filename* kann eine beliebige Kombination von Zeichen sein und muss in doppelte Anführungszeichen eingeschlossen werden (**""**). Wenn *Filename* wird weggelassen, bleibt der vorherige Dateiname unverändert.

Sie können auch die Quellzeilennummer und den Dateinamen ändern, indem Sie das Schreiben einer **#line** Richtlinie. Das Konvertierungsprogramm verwendet die Zeilennummer und den Dateinamen, um zu bestimmen, die Werte der vordefinierten Makros `__FILE__` und `__LINE__`. Sie können diese Makros verwenden, um selbsterklärende Fehlermeldungen in den Programmtext einzufügen. Weitere Informationen zu diesen vordefinierten Makros finden Sie unter [vordefinierte Makros](../preprocessor/predefined-macros.md).

Die `__FILE__` Makro erweitert wird, um eine Zeichenfolge, deren Inhalt der Dateiname in doppelten Anführungszeichen (**""**).

Wenn Sie die Zeilennummer und den Dateinamen ändern, ignoriert der Compiler die vorherigen Werte und setzt die Verarbeitung mit den neuen Werten fort. Die **#line** Richtlinie wird in der Regel von Programm-Generatoren verwendet, um die Fehlermeldungen angezeigt, auf die ursprüngliche Quelldatei anstatt auf das generierte Programm verweisen.

Die folgenden Beispiele veranschaulichen **#line** und `__LINE__` und `__FILE__` Makros.

In dieser Anweisung ist die intern gespeicherte Zeilennummer auf 151 festgelegt, und der Dateinamen in copy.c geändert wird.

```cpp
#line 151 "copy.c"
```

In diesem Beispiel ist das Makro `ASSERT` werden die vordefinierten Makros `__LINE__` und `__FILE__` um eine Fehlermeldung zur Quelldatei auszugeben, wenn es sich bei eine bestimmte Assertion nicht erfüllt ist.

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)