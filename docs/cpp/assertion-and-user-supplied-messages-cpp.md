---
title: Assertion und vom Benutzer bereitgestellte Meldungen (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e93798dadee3e4270d82eac84a794c6133c05c07
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411704"
---
# <a name="assertion-and-user-supplied-messages-c"></a>Assertion und benutzerdefinierte Meldungen (C++)
Die C++-Sprache unterstützt drei Fehlerbehandlungsmechanismen, mit denen Sie Ihre Anwendung debuggen: die [#error-Direktive](../preprocessor/hash-error-directive-c-cpp.md), [Static_assert](../cpp/static-assert.md) -Schlüsselwort, und die [assert-Makro, _assert, _ Wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) Makro. Alle drei Mechanismen geben Fehlermeldungen aus, zwei testen auch Softwareassertionen. Eine Softwareassertion gibt eine Bedingung an, die an einer bestimmten Stelle im Programm "true" sein muss. Wenn bei einer Assertion zur Kompilierzeit ein Fehler auftritt, gibt der Compiler eine Diagnosemeldung und einen Kompilierungsfehler aus. Wenn bei einer Assertion zur Laufzeit ein Fehler auftritt, gibt das Betriebssystem eine Diagnosemeldung aus und schließt Ihre Anwendung.  
  
## <a name="remarks"></a>Hinweise  
 Die Lebensdauer der Anwendung besteht aus einer Vorverarbeitungs-, einer Kompilierungs- und einer Laufzeitphase. Jeder Mechanismus zur Fehlerbehandlung greift auf Debuginformationen zu, die während einer dieser Phasen verfügbar sind. Um auf effiziente Weise zu debuggen, wählen Sie den Mechanismus aus, der entsprechende Informationen über diese Phase bereitstellt:  
  
-   Die [#error-Direktive](../preprocessor/hash-error-directive-c-cpp.md) ist während der Vorverarbeitungsphase wirksam. Sie gibt bedingungslos eine vom Benutzer angegebene Meldung aus und führt dazu, dass die Kompilierung mit einem Fehler beendet wird. Die Meldung kann Text enthalten, der von Präprozessoranweisungen geändert wird, aber Ausdrucksergebnisse werden nicht gewertet.  
  
-   Die [Static_assert](../cpp/static-assert.md) Deklaration faktisch zum Zeitpunkt der Kompilierung ist. Sie testet eine Softwareassertion, die durch einen vom Benutzer angegebenen ganzzahligen Ausdruck dargestellt wird, der in einen booleschen Wert konvertiert werden kann. Wenn der Ausdruck 0 (false) ergibt, gibt der Compiler die vom Benutzer angegebene Meldung aus, und die Kompilierung wird mit einem Fehler beendet.  
  
     Die `static_assert`-Deklaration ist zum Debuggen von Vorlagen besonders nützlich, da Vorlagenargumente in den benutzerdefinierten Ausdruck eingeschlossen werden können.  
  
-   Die [assert-Makro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) Makros zur Laufzeit gültig ist. Es wertet einen vom Benutzer angegebenen Ausdruck aus, und wenn das Ergebnis null (0) ist, gibt das System eine Diagnosemeldung aus und schließt die Anwendung. Viele andere Makros, wie z. B.[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) und `_ASSERTE`, ähneln dieses Makro jedoch unterschiedliche systemdefinierte oder benutzerdefinierte diagnosemeldungen ausgeben.  
  
## <a name="see-also"></a>Siehe auch  
 [#error-Direktive (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [static_assert](../cpp/static-assert.md)   
 [_STATIC_ASSERT-Makro](../c-runtime-library/reference/static-assert-macro.md)   
 [Vorlagen](../cpp/templates-cpp.md)