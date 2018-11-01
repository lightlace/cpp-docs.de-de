---
title: /Zc:throwingNew (annehmen, dass neue Operator ausgelöst)
ms.date: 03/01/2018
f1_keywords:
- throwingNew
- /Zc:throwingNew
helpviewer_keywords:
- -Zc compiler options (C++)
- throwingNew
- Assume operator new Throws
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 20ff0101-9677-4d83-8c7b-8ec9ca49f04f
ms.openlocfilehash: 782cb55d30bfb11f55a0074a5c3245dd389323ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561225"
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/Zc:throwingNew (annehmen, dass neue Operator ausgelöst)

Wenn die **/Zc:throwingNew** angegeben wird, die der Compiler optimiert die Aufrufe an `operator new` überspringen sucht ein null-Zeiger zurück. Diese Option weist den Compiler davon aus, dass alle Implementierungen von verknüpft `operator new` und benutzerdefinierte Zuweisungen der C++-Standard entsprechen, und löst bei Zuordnungsfehler. Standardmäßig in Visual Studio generiert der Compiler davon aus null-Überprüfungen (**/Zc:throwingNew-**) für diese Aufrufe, da Benutzer mit einer nicht auslösend-Implementierung von Links erstellen können `operator new` oder benutzerdefinierte Allocator-Routinen schreiben die null-Zeiger zurückgeben.

## <a name="syntax"></a>Syntax

> **/Zc:throwingNew**[**-**]

## <a name="remarks"></a>Hinweise

Seit der ISO C ++ 98, hat der Standard angegeben, die standardmäßig [new-Operator](../../standard-library/new-operators.md#op_new) löst `std::bad_alloc` bei der speicherbelegung fehlschlägt. Versionen von Visual C++ bis zu Visual Studio 6.0 zurückgegeben einen null-Zeiger auf eine zuordnungsfehlermeldung. Ab Visual Studio 2002 `operator new` entspricht dem Standard und löst bei einem Fehler. Um Code zu unterstützen, die im ältere Format für die Zuordnung verwendet, stellt Visual Studio eine verknüpfbares Implementierung bereit, mit denen `operator new` in nothrownew.obj, die bei einem Fehler einen null-Zeiger zurückgibt. Standardmäßig generiert der Compiler auch defensive null-Überprüfungen, um zu verhindern, dass diese älteren Formats Zuweisungen eine sofortige Absturz bei einem Fehler verursacht. Die **/Zc:throwingNew** -Option weist den Compiler an, diese nullprüfungen auslassen, unter der Annahme, dass alle Speicher verknüpft Zuweisungen, die dem Standard entsprechen. Dies gilt nicht für explizite nicht auslösend `operator new` Überladungen, die mit einem zusätzlichen Parameter vom Typ deklariert werden `std::nothrow_t` und keinen expliziten `noexcept` Spezifikation.

Der Compiler generiert vom Konzept her, um ein Objekt im freien Speicher zu erstellen, Code aus, um die speicherbelegung und dann zum Aufrufen von seinem Konstruktor zum Initialisieren des Speichers. Da Visual C++-Compiler normalerweise nicht feststellen kann, wenn dieser Code wird mit einer nicht konforme, die nicht auslösende Zuordnung verknüpft, wird standardmäßig auch eine null-Überprüfung vor dem Aufruf des Konstruktors. Dies verhindert, dass einen null-Zeiger dereferenziert im Konstruktoraufruf, wenn eine nicht auslösende Zuordnung fehlschlägt. In den meisten Fällen sind diese Überprüfungen nicht erforderlich, da der Standardwert `operator new` Zuweisungen zu lösen, anstatt von null-Zeiger. Die Überprüfungen werden auch leider Nebeneffekte haben. Sie den Umfang des Codes Müll, sie das Vorhersageergebnis Branch überfluten und sie verhindern, dass andere nützliche compileroptimierungen, z. B. Devirtualization oder const-Verteilung aus dem initialisierte Objekt. Die Überprüfungen vorhanden sind, nur für Code für die Unterstützung, die mit verknüpft *nothrownew.obj* oder benutzerdefinierte nicht konforme `operator new` Implementierungen. Wenn Sie nicht konforme nicht verwenden, `operator new`, es wird empfohlen, **/Zc:throwingNew** den Code optimieren.

Die **/Zc:throwingNew** Option ist standardmäßig deaktiviert und ist nicht betroffen von dem [/ PERMISSIVE--](permissive-standards-conformance.md) Option.

Wenn Sie mit Link-zeitcodegenerierung (LTCG) kompilieren, müssen Sie nicht angeben **/Zc:throwingNew**. Wenn Ihr Code mit LTCG kompiliert wird, kann der Compiler erkennen, wenn die Standardeinstellung entsprechen `operator new` Implementierung verwendet. Wenn dies der Fall ist, bleibt der Compiler automatisch, die null-Überprüfungen. Der Linker sucht nach der **/ThrowingNew** Flag, um mitzuteilen, wenn die Implementierung der `operator new` überwacht wird. Sie können dieses Flag an den Linker angeben, indem Sie diese Direktive in der Quelle für die neue Implementierung des benutzerdefinierten Operator einschließlich:

```cpp
#pragma comment(linker, "/ThrowingNew")
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Von der **Konfiguration** Dropdownmenü, und wählen Sie **alle Konfigurationen**.

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc:throwingNew** oder **/Zc:throwingNew-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
[noexcept (C++)](../../cpp/noexcept-cpp.md)<br/>
[Ausnahmespezifikationen (throw) (C++)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[(Ausnahme) beenden](../../standard-library/exception-functions.md#terminate)<br/>
