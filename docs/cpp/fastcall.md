---
title: __fastcall
ms.date: 12/17/2018
f1_keywords:
- __fastcall_cpp
- __fastcall
- _fastcall
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
ms.openlocfilehash: 3e7cd4b1202ee717abf9a9767785ed8abe96bd69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154320"
---
# <a name="fastcall"></a>__fastcall

**Microsoft-spezifisch**

Die **__fastcall** -Aufrufkonvention gibt an, dass Argumente für Funktionen, konventionsgerecht möglichst in Registern übergeben werden. Diese Aufrufkonvention gilt nur für die x86-Architektur. Die folgende Liste zeigt die Implementierung dieser Aufrufkonvention.

|Element|Implementierung|
|-------------|--------------------|
|Reihenfolge der Argumentübergabe|Die ersten beiden in der Argumentliste von links nach rechts gefundenen DWORD oder kleineren Argumente werden in ECX- und EDX-Registern übergeben. Alle anderen Argumente werden von rechts nach links an den Stapel übergeben.|
|Stapelwartungszuständigkeit|Aufgerufene Funktion ruft die Argumente vom Stapel auf.|
|Namensergänzungskonvention|At-Zeichen (\@) Namen; vorangestellt ist ein at-Zeichen, gefolgt von der Anzahl von Bytes (als Dezimalzahl) in den Parameter Dezimalangabe Namen.|
|Konvention zur Umwandlung von Groß- in Kleinbuchstaben und umgekehrt|Groß-/Kleinbuchstaben werden nicht umgewandelt.|

> [!NOTE]
> In zukünftigen Versionen werden von Compilern möglicherweise andere Register zum Speichern von Parametern verwendet werden.

Mithilfe der [/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md) -Compileroption werden die einzelnen Funktionen im Modul als Kompilieren **__fastcall** ausgeführt, wenn die Funktion wurde mit einem in Konflikt stehenden Attribut deklariert oder der Name der Funktion ist `main` .

Die **__fastcall** Schlüsselwort akzeptiert und ignoriert der Compiler, die auf ARM und X64 abzielen Architekturen; auf x X64 chip, gemäß der Konvention werden die ersten vier Argumente konventionsgerecht möglichst in Registern übergeben und es werden zusätzliche Argumente übergeben. auf dem Stapel. Weitere Informationen finden Sie unter [X64 Aufrufkonvention](../build/x64-calling-convention.md). Auf einem ARM-Chip werden bis zu vier Ganzzahl- und acht Gleitkommaargumente in Registern übergeben, und zusätzliche Argumente werden auf den Stapel übergeben.

Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden. Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird. Bei dieser Klassendefinition:

```cpp
struct CMyClass {
   void __fastcall mymethod();
};
```

entspricht:

```cpp
void CMyClass::mymethod() { return; }
```

entspricht:

```cpp
void __fastcall CMyClass::mymethod() { return; }
```

Für die Kompatibilität mit früheren Versionen **_fastcall deklariert sind** ist ein Synonym für **__fastcall** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Funktion `DeleteAggrWrapper` an Argumente in Registern übergeben:

```cpp
// Example of the __fastcall keyword
#define FASTCALL    __fastcall

void FASTCALL DeleteAggrWrapper(void* pWrapper);
// Example of the __ fastcall keyword on function pointer
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)