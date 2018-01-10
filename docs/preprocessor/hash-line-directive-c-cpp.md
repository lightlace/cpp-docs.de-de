---
title: '#<a name="line-directive-cc--microsoft-docs"></a>line-Direktive (C/C++) | Microsoft Docs'
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#line'
dev_langs: C++
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38006dcb6438ca05f6a310dc5e470f5bbd083c43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="line-directive-cc"></a>#line-Anweisung (C/C++)

Die `#line`-Direktive weist den Präprozessor an, die vom Compiler intern gespeicherte Zeilennummer und den Dateinamen in eine bestimmte Zeilennummer und einen bestimmten Dateinamen zu ändern.

## <a name="syntax"></a>Syntax

> **#line** *Ziffernfolge* ["*Filename*"]

## <a name="remarks"></a>Hinweise

Der Compiler verwendet die Zeilennummer und den optionalen Dateinamen, um auf Fehler zu verweisen, die während der Kompilierung gefunden werden. Die Zeilennummer verweist normalerweise auf die aktuelle Eingabezeile, und der Dateiname verweist auf die aktuelle Eingabedatei. Nach der Verarbeitung jeder Zeile wird die Zeilennummer erhöht.

Die *Ziffernfolge* Wert kann eine beliebige Integerkonstante sein. Makroersetzungen können für die Vorverarbeitungstoken durchgeführt werden, das Ergebnis muss jedoch anhand der richtigen Syntax ausgewertet werden. Die *Filename* kann eine beliebige Kombination von Zeichen sein und muss in doppelte Anführungszeichen eingeschlossen werden (**""**). Wenn *Filename* wird weggelassen, bleibt der vorherige Dateiname unverändert.

Sie können auch die Quellzeilennummer und den Quelldateinamen ändern, indem Sie eine `#line`-Direktiven schreiben. Das Konvertierungsprogramm verwendet die Zeilennummer und den Dateinamen zur Bestimmung der Werte der vordefinierten Makros **&#95; &#95; Datei &#95; &#95;**  und **&#95; &#95; LINE #95; &#95;** . Sie können diese Makros verwenden, um selbsterklärende Fehlermeldungen in den Programmtext einzufügen. Weitere Informationen zu diesen vordefinierten Makros finden Sie unter [vordefinierte Makros](../preprocessor/predefined-macros.md).

Die **&#95; &#95; Datei &#95; &#95;**  -Makro wird in eine Zeichenfolge, deren Inhalt der Dateiname in doppelten Anführungszeichen (**""**).

Wenn Sie die Zeilennummer und den Dateinamen ändern, ignoriert der Compiler die vorherigen Werte und setzt die Verarbeitung mit den neuen Werten fort. Die `#line`-Direktive wird in der Regel von Programm-Generatoren verwendet, damit Fehlermeldungen auf die ursprüngliche Quelldatei und nicht auf das generierte Programm verweisen.

Die folgenden Beispiele veranschaulichen `#line` und **&#95; &#95; LINE #95; &#95;**  und **&#95; &#95; Datei &#95; &#95;**  Makros.

In dieser Anweisung die intern gespeicherte Zeilennummer auf 151 festgelegt ist, und der Dateiname auf copy.c geändert wird.

```cpp
#line 151 "copy.c"
```

 In diesem Beispiel wird das Makro `ASSERT` verwendet vordefinierte Makros **&#95; &#95; LINE #95; &#95;**  und **&#95; &#95; Datei &#95; &#95;**  um eine Fehlermeldung zur Quelldatei auszugeben, wenn es sich bei eine bestimmte Assertion nicht "true" ist.

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)