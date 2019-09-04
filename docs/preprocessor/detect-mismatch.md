---
title: detect_mismatch-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: 6e247b3f251bce47710a3380fb295597314a3bd8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222397"
---
# <a name="detect_mismatch-pragma"></a>detect_mismatch-Pragma

Platziert einen Datensatz in einem Objekt. Der Linker überprüft diese Datensätze auf potenzielle Konflikte.

## <a name="syntax"></a>Syntax

> **#pragma detect_mismatch (** "*Name*" **,** "*value*" **)**

## <a name="remarks"></a>Hinweise

Wenn Sie das Projekt verknüpfen, löst der Linker einen [Linkertoolfehler lnk2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md) -Fehler aus, wenn das Projekt zwei Objekte mit demselben *Namen* enthält, für die jedoch jeweils ein anderer *Wert*vorhanden ist. Verwenden Sie dieses Pragma, um zu verhindern, dass inkonsistente Objektdateien verknüpft werden.

Sowohl *Name* als auch *Wert* sind Zeichen folgen Literale und unterliegen den Regeln für Zeichen folgen Literale in Bezug auf Escapezeichen und Verkettung. Bei der Groß-/Kleinschreibung wird zwischen Groß-und Kleinschreibung unterschieden.

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
