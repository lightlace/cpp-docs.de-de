---
title: Assertion und benutzerdefinierte Meldungen (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
ms.openlocfilehash: 913aa199b4acd2ceb6daf7a24d8c50c28234b74a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184360"
---
# <a name="assertion-and-user-supplied-messages-c"></a>Assertion und benutzerdefinierte Meldungen (C++)

Die C++ Sprache unterstützt drei Mechanismen für die Fehlerbehandlung, mit denen Sie Ihre Anwendung debuggen: die [#error-Anweisung](../preprocessor/hash-error-directive-c-cpp.md), ["static_assert"](../cpp/static-assert.md) -Schlüsselwort, und die [assert-Makro, _ bestätigen, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) Makro. Alle drei Mechanismen geben Fehlermeldungen aus, zwei testen auch Softwareassertionen. Eine Softwareassertion gibt eine Bedingung an, die an einer bestimmten Stelle im Programm "true" sein muss. Wenn bei einer Assertion zur Kompilierzeit ein Fehler auftritt, gibt der Compiler eine Diagnosemeldung und einen Kompilierungsfehler aus. Wenn bei einer Assertion zur Laufzeit ein Fehler auftritt, gibt das Betriebssystem eine Diagnosemeldung aus und schließt Ihre Anwendung.

## <a name="remarks"></a>Hinweise

Die Lebensdauer der Anwendung besteht aus einer Vorverarbeitungs-, einer Kompilierungs- und einer Laufzeitphase. Jeder Mechanismus zur Fehlerbehandlung greift auf Debuginformationen zu, die während einer dieser Phasen verfügbar sind. Um auf effiziente Weise zu debuggen, wählen Sie den Mechanismus aus, der entsprechende Informationen über diese Phase bereitstellt:

- Die [#error-Anweisung](../preprocessor/hash-error-directive-c-cpp.md) während der Vorverarbeitungsphase gültig ist. Sie gibt bedingungslos eine vom Benutzer angegebene Meldung aus und führt dazu, dass die Kompilierung mit einem Fehler beendet wird. Die Meldung kann Text enthalten, der von Präprozessordirektiven geändert wird, aber Ausdrucksergebnisse werden nicht gewertet.

- Die ["static_assert"](../cpp/static-assert.md) Deklaration gültig ist, zum Zeitpunkt der Kompilierung. Sie testet eine Softwareassertion, die durch einen vom Benutzer angegebenen ganzzahligen Ausdruck dargestellt wird, der in einen booleschen Wert konvertiert werden kann. Wenn der Ausdruck 0 (false) ergibt, gibt der Compiler die vom Benutzer angegebene Meldung aus, und die Kompilierung wird mit einem Fehler beendet.

   Die `static_assert`-Deklaration ist zum Debuggen von Vorlagen besonders nützlich, da Vorlagenargumente in den benutzerdefinierten Ausdruck eingeschlossen werden können.

- Die [assert-Makro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) Makro zur Laufzeit gültig ist. Es wertet einen vom Benutzer angegebenen Ausdruck aus, und wenn das Ergebnis null (0) ist, gibt das System eine Diagnosemeldung aus und schließt die Anwendung. Viele andere Makros, wie z. B.[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) und _ASSERTE-, ähneln diesem Makro aber unterschiedliche systemdefinierte oder benutzerdefinierte diagnosemeldungen ausgeben.

## <a name="see-also"></a>Siehe auch

[#error-Direktive (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Macros](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)<br/>
[static_assert](../cpp/static-assert.md)<br/>
[_STATIC_ASSERT Macro](../c-runtime-library/reference/static-assert-macro.md)<br/>
[Vorlagen](../cpp/templates-cpp.md)