---
title: '##line-Anweisung (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: 35bee779ebf059c20d4a46e27b5ad4cbfb3ce5f3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220221"
---
# <a name="line-directive-cc"></a>#line-Direktive (C++C/)

Die **#Line** Direktive weist den Präprozessor an, die intern gespeicherte Zeilennummer und den Dateinamen des Compilers in eine bestimmte Zeilennummer und einen bestimmten Dateinamen zu ändern.

## <a name="syntax"></a>Syntax

> **#line** *digit-sequence* ["*filename*"]

## <a name="remarks"></a>Hinweise

Der Compiler verwendet die Zeilennummer und den optionalen Dateinamen, um auf Fehler zu verweisen, die während der Kompilierung gefunden werden. Die Zeilennummer verweist normalerweise auf die aktuelle Eingabezeile, und der Dateiname verweist auf die aktuelle Eingabedatei. Nach der Verarbeitung jeder Zeile wird die Zeilennummer erhöht.

Der *Ziffern Sequenz* Wert kann eine beliebige ganzzahlige Konstante sein. Makroersetzungen können für die Vorverarbeitungstoken durchgeführt werden, das Ergebnis muss jedoch anhand der richtigen Syntax ausgewertet werden. Der *Dateiname* kann eine beliebige Kombination von Zeichen sein und muss in doppelte Anführungs`" "`Zeichen () eingeschlossen werden. Wenn *filename* ausgelassen wird, bleibt der vorherige Dateiname unverändert.

Sie können die Quell Zeilennummer und den Dateinamen ändern, indem Sie eine **#Line** -Direktive schreiben. Der Konvertierer verwendet die Zeilennummer und den Dateinamen, um die Werte der `__FILE__` vordefinierten `__LINE__`Makros und zu bestimmen. Sie können diese Makros verwenden, um selbsterklärende Fehlermeldungen in den Programmtext einzufügen. Weitere Informationen zu diesen vordefinierten Makros finden Sie unter [vordefinierte Makros](../preprocessor/predefined-macros.md).

Das `__FILE__` -Makro wird zu einer Zeichenfolge erweitert, deren Inhalt der Dateiname ist,`" "`umgeben von doppelten Anführungszeichen ().

Wenn Sie die Zeilennummer und den Dateinamen ändern, ignoriert der Compiler die vorherigen Werte und setzt die Verarbeitung mit den neuen Werten fort. Die **#Line** -Direktive wird in der Regel von Programm-Generatoren verwendet, damit Fehlermeldungen auf die ursprüngliche Quelldatei und nicht auf das generierte Programm verweisen.

Die folgenden Beispiele veranschaulichen **#Line** und die `__LINE__` - `__FILE__` und-Makros.

In dieser Anweisung wird die intern gespeicherte Zeilennummer auf 151 festgelegt, und der Dateiname wird in Copy. c geändert.

```C
#line 151 "copy.c"
```

In diesem Beispiel verwendet das- `ASSERT` Makro die vordefinierten Makros `__LINE__` und `__FILE__` , um eine Fehlermeldung zur Quelldatei auszugeben, wenn eine gegebene Behauptung nicht wahr ist.

```C
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)
