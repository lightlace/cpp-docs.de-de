---
title: detect_mismatch
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: 2973a4738aa54e9f454190b18bcabff92077b284
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633323"
---
# <a name="detectmismatch"></a>detect_mismatch
Platziert einen Datensatz in einem Objekt. Der Linker überprüft diese Datensätze auf potenzielle Konflikte.

## <a name="syntax"></a>Syntax

```
#pragma detect_mismatch( "name", "value"))
```

## <a name="remarks"></a>Hinweise

Wenn Sie das Projekt verknüpfen, löst der Linker einen `LNK2038`-Fehler aus, wenn das Projekt zwei Objekte enthält, die den gleichen `name`, jedoch einen unterschiedlichen `value` aufweisen. Verwenden Sie dieses Pragma, um zu verhindern, dass inkonsistente Objektdateien verknüpft werden.

Name und Wert sind Zeichenfolgenliterale und befolgen im Zusammenhang mit Escapezeichen und Verkettungen die Regeln für Zeichenfolgenliterale. Beachtet, und darf keine Kommas, Gleichheitszeichen, Anführungszeichen enthalten oder die **null** Zeichen.

## <a name="example"></a>Beispiel

Dieses Beispiel erstellt zwei Dateien, die unterschiedliche Versionsnummern für die gleiche Versionsbezeichnung aufweisen.

```cpp
// pragma_directive_detect_mismatch_a.cpp
#pragma detect_mismatch("myLib_version", "9")
int main ()
{
   return 0;
}

// pragma_directive_detect_mismatch_b.cpp
#pragma detect_mismatch("myLib_version", "1")
```

Wenn Sie beide Dateien kompilieren, indem Sie die Befehlszeile `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` verwenden, erhalten Sie den Fehler `LNK2038`.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)