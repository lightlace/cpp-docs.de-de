---
title: Importieren von Funktionsaufrufen mithilfe von "__declspec(dllimport)"
ms.date: 11/04/2016
f1_keywords:
- __declspec
- dllimport
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 8635cf5d389f72972f471a4fd53ed56c3497bfe9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811731"
---
# <a name="importing-function-calls-using-declspecdllimport"></a>Importieren von Funktionsaufrufen mithilfe von "__declspec(dllimport)"

Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit **_declspec(dllimport)** Funktionsaufrufe aus einer DLL in einer Anwendung zu importieren. Vorausgesetzt, dass `func1` ist eine Funktion, die in einer DLL, die getrennt von der .exe-Datei liegt, enthält die **main** Funktion.

Ohne **von "__declspec(dllimport)" "**, erhält diesen Code:

```
int main(void)
{
   func1();
}
```

der Compiler generiert Code, der folgendermaßen aussieht:

```
call func1
```

und der Linker übersetzt den Aufruf in etwa wie folgt:

```
call 0x4000000         ; The address of 'func1'.
```

Wenn `func1` vorhanden ist in einer anderen DLL der Linker kann nicht direkt diesem aufgelöst werden, da es keine Möglichkeit, zu wissen, welche die Adresse des hat `func1` ist. In 16-Bit-Umgebungen fügt der Linker diese Codeadresse zu einer Liste in die .exe-Datei, die das Ladeprogramm zur Laufzeit mit der richtigen Adresse patch würde. In 32-Bit- und 64-Bit-Umgebungen generiert der Linker einen Thunk, von dem sie die Adresse kennt. In einer 32-Bit-Umgebung wird der Thunk sieht:

```
0x40000000:    jmp DWORD PTR __imp_func1
```

Hier `imp_func1` ist die Adresse für den `func1` Slot in der Importadresstabelle der .exe-Datei. Folglich sind alle Adressen für den Linker bekannt. Das Ladeprogramm muss nur zum Aktualisieren der .exe-Datei der Importadresstabelle zur Ladezeit für alles ordnungsgemäß funktioniert.

Daher wird die Verwendung **von "__declspec(dllimport)" "** ist besser, da der Linker einen Thunk nicht generiert, wenn es nicht erforderlich ist. Thunks, dass der Code mehr (auf RISC-Systemen kann es mehrere Anweisungen sein) und kann Ihre cacheleistung beeinträchtigen. Wenn Sie dem Compiler, dass die Funktion in einer DLL enthalten ist mitzuteilen, können sie einen indirekten Aufruf für Sie generieren.

Jetzt diesen Code:

```
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

Diese Anweisung generiert:

```
call DWORD PTR __imp_func1
```

Es gibt keine Thunk und keine `jmp` -Anweisung, damit der Code kleiner und schneller ist.

Auf der anderen Seite für Funktionsaufrufe innerhalb einer DLL möchten nicht Sie einen indirekten Aufruf verwenden. Sie wissen bereits, die Adresse einer Funktion. Da die Verarbeitungszeit und Speicherplatz zum Laden und speichern die Adresse der Funktion vor einem indirekten Aufruf erforderlich sind, ist ein direkter Aufruf immer schneller und kürzer. Sie verwenden möchten **von "__declspec(dllimport)" "** beim Aufrufen von DLL-Funktionen außerhalb der DLL selbst. Verwenden Sie keine **von "__declspec(dllimport)" "** für Funktionen innerhalb einer DLL, die beim Erstellen dieser DLL.

## <a name="see-also"></a>Siehe auch

[Importieren in eine Anwendung](importing-into-an-application.md)
