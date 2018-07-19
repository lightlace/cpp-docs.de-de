---
title: /Zc:throwingNew (annehmen, dass neue Operator ausgelöst) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- throwingNew
- /Zc:throwingNew
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- throwingNew
- Assume operator new Throws
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 20ff0101-9677-4d83-8c7b-8ec9ca49f04f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f446e5c71e88be86c31e5a83ca7d23f611683af4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383461"
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/Zc:throwingNew (annehmen, dass neue Operator ausgelöst)

Wenn die **/Zc:throwingNew** angegeben wird, der Compiler optimiert Aufrufe `operator new` überspringen sucht ein null-Zeiger zurückgegeben. Diese Option weist den Compiler anweist anzunehmen, dass alle Implementierungen von verknüpften `operator new` und benutzerdefinierte Zuweisungen entspricht dem C++-Standard und löst bei einem Speicherzuweisungsfehler. In der Standardeinstellung werden in Visual Studio generiert der Compiler pessimistisch null-Überprüfungen (**/Zc:throwingNew-**) für diese aufgerufen wird, da Benutzer mit einer Implementierung nicht auslösende des Links können `operator new` oder benutzerdefinierte Zuweisung Routinen schreiben null-Zeiger zurückgeben.

## <a name="syntax"></a>Syntax

> **/Zc:throwingNew**[**-**]

## <a name="remarks"></a>Hinweise

Seit ISO C ++ 98, hat der Standard angegeben, die standardmäßig [new-Operator](../../standard-library/new-operators.md#op_new) löst `std::bad_alloc` Wenn speicherbelegung fehlschlägt. Versionen von Visual C++ auf Visual Studio 6.0, das einen null-Zeiger für eines zuordnungsfehlers zurückgegeben. Ab Visual Studio 2002 `operator new` entspricht dem Standard und löst bei einem Fehler. Um Code zu unterstützen, die die Zuordnung im ältere Format verwendet, stellt Visual Studio eine verknüpfbares Implementierung der `operator new` in nothrownew.obj, die bei einem Fehler einen null-Zeiger zurückgibt. Standardmäßig generiert der Compiler auch defensive null-Überprüfungen, um zu verhindern, dass diese älteren Formats Zuweisungen verursacht eine sofortige Absturz (Crash) bei einem Fehler. Die **/Zc:throwingNew** Option weist den Compiler an, diese null-Überprüfungen auslassen, unter der Annahme, dass alle Arbeitsspeicher verknüpfte Zuweisungen entspricht dem Standard. Dies gilt nicht für explizite nicht auslösende `operator new` Überladungen, die deklariert werden, ein weiterer Parameter vom Typ mit `std::nothrow_t` und keinen expliziten `noexcept` Spezifikation.

Der Compiler generiert im Prinzip um ein Objekt auf dem freien Speicher zu erstellen, Code aus, um dessen Arbeitsspeicher belegt werden und dann zum Aufrufen von seinem Konstruktor, um den Arbeitsspeicher zu initialisieren. Da Visual C++-Compiler normalerweise nicht feststellen kann, wenn dieser Code eine nicht konforme, nicht auslösende Zuordnung verknüpft werden soll, wird generiert standardmäßig auch eine null-Prüfung vor dem Aufruf des Konstruktors. Dies verhindert, dass einen null-Zeiger im Konstruktoraufruf dereferenziert wird, wenn eine nicht auslösende Zuordnung ein Fehler auftritt. In den meisten Fällen sind diese Überprüfungen überflüssig, da der Standardwert `operator new` Zuweisungen zu lösen, anstatt von null-Zeiger. Die Überprüfungen haben auch etwas unglücklich Nebeneffekte. Sie die Codegröße Aufblasen sie überfluten, die Verzweigung Vorhersage und dadurch die andere nützliche compileroptimierungen, z. B. Devirtualization oder const Weitergabe aus dem initialisierte Objekt. Überprüfungen werden nur für links zu Support-Code vorhanden *nothrownew.obj* noch benutzerdefinierte nicht konforme `operator new` Implementierungen. Wenn Sie keine nicht konforme benutzen `operator new`, es wird empfohlen, **/Zc:throwingNew** den Code optimieren.

Die **/Zc:throwingNew** Option ist standardmäßig deaktiviert und ist nicht betroffen von dem [/ liberalen-](permissive-standards-conformance.md) Option.

Wenn Sie mit Link-zeitcodegenerierung (LTCG) kompilieren, müssen Sie nicht angeben **/Zc:throwingNew**. Wenn Code mit LTCG kompiliert wird, kann der Compiler erkennen, wenn der in der Standardeinstellung entsprechen, das `operator new` Implementierung verwendet. Wenn dies der Fall ist, bleibt der Compiler automatisch, die null-Überprüfungen. Der Linker sucht nach der **/ThrowingNew** Flag anzuweisen, wenn die Implementierung von `operator new` ist entsprechen. Sie können dieses Flag an den Linker angeben, indem diese Richtlinie in der Quelle für die neue Implementierung von benutzerdefinierter Operator:

```cpp
#pragma comment(linker, "/ThrowingNew")
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Aus der **Konfiguration** Dropdown-Menü, und wählen Sie **alle Konfigurationen**.

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc:throwingNew** oder **/Zc:throwingNew-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
[noexcept (C++)](../../cpp/noexcept-cpp.md)<br/>
[Ausnahmespezifikationen (throw) (C++)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[(Ausnahme) beenden](../../standard-library/exception-functions.md#terminate)<br/>
