---
title: -Sdl (Aktivieren zusätzlicher Sicherheitsüberprüfungen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
dev_langs:
- C++
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fda6d2c3a608050906626e499b1ddaa48ddd82b9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702623"
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl (Aktivieren zusätzlicher Sicherheitsüberprüfungen)

Fügt empfohlene SDL-Prüfungen (Security Development Lifecycle) hinzu. Diese Prüfungen enthalten zusätzliche sicherheitsrelevante Warnungen als Fehler und zusätzliche sichere Codegenerierungsfunktionen.

## <a name="syntax"></a>Syntax

```
/sdl[-]
```

## <a name="remarks"></a>Hinweise

**/ SDL** aktiviert eine Obermenge der grundlegenden sicherheitsüberprüfungen von bereitgestellten [/GS](../../build/reference/gs-buffer-security-check.md) und überschreibt **/GS-**. In der Standardeinstellung **/SDL** ist deaktiviert. **/SDL-** deaktiviert die zusätzlichen sicherheitsüberprüfungen.

## <a name="compile-time-checks"></a>Überprüfungen zur Kompilierzeit

**/ SDL** aktiviert die folgenden Warnungen als Fehler:

|Durch /sdl aktivierte Warnung|Entsprechender Befehlszeilenschalter|Beschreibung|
|------------------------------|-------------------------------------|-----------------|
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|Ein unärer Subtraktionsoperator wurde auf einen vorzeichenlosen Typ angewendet, was zu einem Ergebnis ohne Vorzeichen führte.|
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|Eine negative integrale Konstante wurde in einen vorzeichenlosen Typ konvertiert, was zu einem möglicherweise bedeutungslosen Ergebnis führte.|
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|Verwenden von `continue`, `break` oder `goto` Schlüsselwörter in einer `__finally` / `finally` -Block weist ein undefiniertes Verhalten bei nicht ordnungsgemäßer Beendigung.|
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|Der Code, der eine Variable initialisiert, wird nicht ausgeführt.|
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|Verwendung einer nicht initialisierten lokalen Variablen.|
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|Verwendung einer möglicherweise nicht initialisierten lokalen Zeigervariablen.|
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|Pufferüberlauf, wenn bestimmte CRT-Funktionen (C Run-Time) verwendet werden.|
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|Verwenden einer Funktion mit Pragma gekennzeichnete [veraltet](../../preprocessor/deprecated-c-cpp.md).|
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|Verwenden einer Funktion als markiert [veraltet](../../cpp/deprecated-cpp.md).|

## <a name="runtime-checks"></a>Überprüfungen zur Laufzeit

Wenn **/SDL** ist aktiviert, generiert der Compiler Code, um diese Überprüfungen zur Laufzeit auszuführen:

- Aktiviert den strict-Modus von **/GS** Laufzeit pufferüberlauferkennung, entspricht dem Kompilieren mit `#pragma strict_gs_check(push, on)`.

- Führt eingeschränkte Zeigerbereinigung aus. In Ausdrücken ohne Dereferenzierungen und in Typen ohne benutzerdefinierten Destruktor werden Zeigerverweise nach einem Aufruf von `delete` auf eine ungültige Adresse festgelegt. Dies dient dazu, die Wiederverwendung von veralteten Zeigerverweisen zu verhindern.

- Führt Klassenmemberinitialisierung aus. Initialisiert bei der Objektinstanziierung (bevor der Konstruktor ausgeführt wird) automatisch alle Klassenmember auf null. Dies dient dazu, die Verwendung von nicht initialisierten Daten zu verhindern, die Klassenmembern zugeordnet sind, die der Konstruktor nicht explizit initialisiert.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Warnungen, / SDL und Verbessern der Erkennung von nicht initialisierten Variablen](https://cloudblogs.microsoft.com/microsoftsecure/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/).

#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **C/C++-** Ordner.

1. Auf der **allgemeine** Seite, wählen Sie die Option aus der **SDL-Prüfungen** Dropdown-Liste.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)