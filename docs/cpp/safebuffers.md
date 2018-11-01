---
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: 473a838a48ed6523ce78d0bc8128dd83636c81d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555750"
---
# <a name="safebuffers"></a>safebuffers

**Microsoft-spezifisch**

Weist den Compiler an, keine Pufferüberlauf-Sicherheitsüberprüfungen für eine Funktion einzufügen.

## <a name="syntax"></a>Syntax

```
__declspec( safebuffers )
```

## <a name="remarks"></a>Hinweise

Die **/GS** -Compileroption bewirkt, dass der Compiler Pufferüberläufe zu testen, indem sicherheitsüberprüfungen im Stapel eingefügt. Die Typen der Datenstrukturen, die für sicherheitsüberprüfungen freigegeben sind, werden in beschrieben [/GS (Puffer-Sicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md). Weitere Informationen zur pufferüberlauferkennung finden Sie unter [Sicherheitsfunktionen in MSVC](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/).

Ein fachmännischer manueller Codereview oder eine externe Analyse kann bestimmen, dass eine Funktion vor einem Pufferüberlauf sicher ist. In diesem Fall können Sie sicherheitsüberprüfungen für eine Funktion unterdrücken, indem Sie die Anwendung die **__declspec(safebuffers)** Schlüsselwort, um die Funktionsdeklaration.

> [!CAUTION]
>  Puffer-Sicherheitsüberprüfungen bieten wichtige Sicherheit und haben eine geringfügige Auswirkung auf die Leistung. Daher empfiehlt es sich, sie nicht zu unterdrücken, außer in dem seltenen Fall, in dem die Leistung einer Funktion ein wichtiger Aspekt ist und die Funktion bekanntermaßen sicher ist.

## <a name="inline-functions"></a>Inlinefunktionen

Ein *Hauptfunktion* können eine [inlining](inline-functions-cpp.md) Schlüsselwort, um eine Kopie der Einfügen einer *sekundären Funktion*. Wenn die **__declspec(safebuffers)** -Schlüsselwort auf eine Funktion angewendet wird, wird die pufferüberlauferkennung für diese Funktion unterdrückt. Allerdings inlining wirkt sich auf die **__declspec(safebuffers)** Schlüsselwort folgt.

Nehmen Sie an der **/GS** Compileroption ist für beide Funktionen angegeben, aber die primäre Funktion gibt die **__declspec(safebuffers)** Schlüsselwort. Die Datenstrukturen in der sekundären Funktion machen sie besonders geeignet für Sicherheitsüberprüfungen, und die Funktion unterdrückt diese Überprüfungen nicht. In diesem Fall gilt Folgendes:

- Geben Sie die ["__forceinline"](inline-functions-cpp.md) -Schlüsselwort in der sekundären Funktion zu erzwingen, dass der Compiler Inline, die unabhängig von compileroptimierungen funktionieren.

- Da die sekundäre Funktion für sicherheitsüberprüfungen freigegeben ist, sicherheitsüberprüfungen gelten auch für die primäre Funktion, obwohl er gibt an, die **__declspec(safebuffers)** Schlüsselwort.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie mit der **__declspec(safebuffers)** Schlüsselwort.

```cpp
// compile with: /c /GS
typedef struct {
    int x[20];
} BUFFER;
static int checkBuffers() {
    BUFFER cb;
    // Use the buffer...
    return 0;
};
static __declspec(safebuffers)
    int noCheckBuffers() {
    BUFFER ncb;
    // Use the buffer...
    return 0;
}
int wmain() {
    checkBuffers();
    noCheckBuffers();
    return 0;
}
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \__forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)