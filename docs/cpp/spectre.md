---
title: spectre
ms.date: 01/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: 40eee25dec867ae3fce7a6b2d4715f0be81bfe76
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926366"
---
# <a name="spectre"></a>spectre

**Microsoft-spezifisch**

Weist den Compiler an, die Anweisungen zur Ausführung von Spectre Variant 1 für eine Funktion einzufügen.

## <a name="syntax"></a>Syntax

> **__declspec( spectre(nomitigation) )**

## <a name="remarks"></a>Hinweise

Die [/Qspectre](../build/reference/qspectre.md) -Compileroption bewirkt, dass der Compiler spekulative Anweisungen für die Ausführungs Barriere einfügt. Sie werden eingefügt, wenn die Analyse anzeigt, dass eine Spectre Variant 1-Sicherheitslücke vorhanden ist. Welche spezifischen Anweisungen ausgegeben werden, hängt vom Prozessor ab. Diese Anweisungen sollten sich nur minimal auf die Codegröße oder die Leistung auswirken, es kann jedoch vorkommen, dass Ihr Code nicht von der Sicherheits Anfälligkeit betroffen ist und eine maximale Leistung erfordert.

Die Expertenanalyse kann feststellen, dass eine Funktion von einem Fehler beim umgehen der Überprüfung der Spectre-Variante 1 sicher ist. In diesem Fall können Sie die Generierung des Entschärfungs Codes innerhalb einer Funktion unterdrücken, `__declspec(spectre(nomitigation))` indem Sie auf die Funktionsdeklaration anwenden.

> [!CAUTION]
> Die **/Qspectre** -Anweisungen für die spekulative Ausführungs Barriere bieten einen wichtigen Sicherheitsschutz und haben eine erhebliche Auswirkung auf die Leistung. Daher empfiehlt es sich, sie nicht zu unterdrücken, außer in dem seltenen Fall, in dem die Leistung einer Funktion ein wichtiger Aspekt ist und die Funktion bekanntermaßen sicher ist.

## <a name="example"></a>Beispiel

Im folgenden Code wird die Verwendung von `__declspec(spectre(nomitigation))`veranschaulicht.

```cpp
// compile with: /c /Qspectre
static __declspec(spectre(nomitigation))
int noSpectreIssues() {
    // No Spectre variant 1 vulnerability here
    // ...
    return 0;
}

int main() {
    noSpectreIssues();
    return 0;
}
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[/Qspectre](../build/reference/qspectre.md)
