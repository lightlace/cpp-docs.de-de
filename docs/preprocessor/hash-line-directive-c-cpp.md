---
title: '#line-Direktive (C/C++) | Microsoft Docs'
ms.custom: ''
ms.date: 10/18/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#line'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ebbcea7432b27e9269b5041d90d14534a77b812
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="line-directive-cc"></a>#line-Anweisung (C/C++)

Die `#line`-Direktive weist den Präprozessor an, die vom Compiler intern gespeicherte Zeilennummer und den Dateinamen in eine bestimmte Zeilennummer und einen bestimmten Dateinamen zu ändern.

## <a name="syntax"></a>Syntax

> **#line** *Ziffernfolge* ["*Filename*"]

## <a name="remarks"></a>Hinweise

Der Compiler verwendet die Zeilennummer und den optionalen Dateinamen, um auf Fehler zu verweisen, die während der Kompilierung gefunden werden. Die Zeilennummer verweist normalerweise auf die aktuelle Eingabezeile, und der Dateiname verweist auf die aktuelle Eingabedatei. Nach der Verarbeitung jeder Zeile wird die Zeilennummer erhöht.

Die *Ziffernfolge* Wert kann eine beliebige Integerkonstante sein. Makroersetzungen können für die Vorverarbeitungstoken durchgeführt werden, das Ergebnis muss jedoch anhand der richtigen Syntax ausgewertet werden. Die *Filename* kann eine beliebige Kombination von Zeichen sein und muss in doppelte Anführungszeichen eingeschlossen werden (**""**). Wenn *Filename* wird weggelassen, bleibt der vorherige Dateiname unverändert.

Sie können auch die Quellzeilennummer und den Quelldateinamen ändern, indem Sie eine `#line`-Direktiven schreiben. Das Konvertierungsprogramm verwendet die Zeilennummer und den Dateinamen zur Bestimmung der Werte der vordefinierten Makros **&#95; &#95;Datei&#95; &#95;** und **&#95; &#95;Zeile&#95; &#95;**. Sie können diese Makros verwenden, um selbsterklärende Fehlermeldungen in den Programmtext einzufügen. Weitere Informationen zu diesen vordefinierten Makros finden Sie unter [vordefinierte Makros](../preprocessor/predefined-macros.md).

Die **&#95; &#95;Datei&#95; &#95;** -Makro wird in eine Zeichenfolge, deren Inhalt der Dateiname in doppelten Anführungszeichen (**""**).

Wenn Sie die Zeilennummer und den Dateinamen ändern, ignoriert der Compiler die vorherigen Werte und setzt die Verarbeitung mit den neuen Werten fort. Die `#line`-Direktive wird in der Regel von Programm-Generatoren verwendet, damit Fehlermeldungen auf die ursprüngliche Quelldatei und nicht auf das generierte Programm verweisen.

Die folgenden Beispiele veranschaulichen `#line` und **&#95; &#95;Zeile&#95; &#95;** und **&#95; &#95;Datei&#95; &#95;** Makros.

In dieser Anweisung die intern gespeicherte Zeilennummer auf 151 festgelegt ist, und der Dateiname auf copy.c geändert wird.

```cpp
#line 151 "copy.c"
```

 In diesem Beispiel wird das Makro `ASSERT` verwendet vordefinierte Makros **&#95; &#95;Zeile&#95; &#95;** und **&#95; &#95;Datei&#95; &#95;** So drucken Sie ein Fehlermeldung zur Quelldatei ist eine bestimmte Assertion nicht "true".

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)