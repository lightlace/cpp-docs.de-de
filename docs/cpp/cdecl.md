---
title: __cdecl
ms.date: 10/09/2018
f1_keywords:
- __cdecl_cpp
- __cdecl
- _cdecl
- cdecl
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
ms.openlocfilehash: 298485d310ee4039b13781a8b5cd88a489af3b8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550214"
---
# <a name="cdecl"></a>__cdecl

**Microsoft-spezifisch**

**__cdecl** ist die Standardaufrufkonvention für C- und C++-Programme. Da der Stapel vom Aufrufer bereinigt wird, können sie tun `vararg` Funktionen. Die **__cdecl** -Aufrufkonvention erstellt größere ausführbare Dateien als [__stdcall](../cpp/stdcall.md), da jeder Funktionsaufruf stapelbereinigungscode enthalten muss. Die folgende Liste zeigt die Implementierung dieser Aufrufkonvention.

|Element|Implementierung|
|-------------|--------------------|
|Reihenfolge der Argumentübergabe|Von rechts nach links.|
|Stapelwartungszuständigkeit|Aufgerufene Funktion ruft die Argumente vom Stapel auf.|
|Namensergänzungskonvention|Namen, außer wenn Unterstrich (_) vorangestellt ist \__cdecl-Funktionen, die C-Bindung verwenden, werden exportiert.|
|Konvention zur Umwandlung von Groß- in Kleinbuchstaben und umgekehrt|Groß-/Kleinbuchstaben werden nicht umgewandelt.|

> [!NOTE]
>  Weitere Informationen finden Sie unter [ergänzte Namen](../build/reference/decorated-names.md).

Ort der **__cdecl** Modifizierer vor einer Variablen oder einem Funktionsnamen. Da es sich bei der Benennung c und C-Aufrufkonventionen die Standardeinstellung sind, nur dann hierarchieverwaltungstools **__cdecl** in X86 Code ist, wenn Sie angegeben haben die `/Gv` (Vectorcall), `/Gz` (Stdcall) oder `/Gr` (Fastcall) Compileroption. Die [/GD](../build/reference/gd-gr-gv-gz-calling-convention.md) Compiler-Option erzwingt, dass die **__cdecl** Aufrufkonvention.

Auf ARM und X64 Prozessoren **__cdecl** , akzeptiert jedoch in der Regel vom Compiler ignoriert wird. Gemäß der Konvention zu ARM und x64 werden Argumente in Register übergeben, wenn dies möglich ist, und darauf folgende Argumente werden auf den Stapel übergeben. In X64 codieren, verwenden Sie **__cdecl** zum Überschreiben der **/GV** Compileroption und das Verwenden der standardmäßige X64-Aufrufkonvention.

Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden. Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird. Bei dieser Klassendefinition:

```cpp
struct CMyClass {
   void __cdecl mymethod();
};
```

entspricht:

```cpp
void CMyClass::mymethod() { return; }
```

entspricht:

```cpp
void __cdecl CMyClass::mymethod() { return; }
```

Für die Kompatibilität mit früheren Versionen **Cdecl** und **_cdecl** sind ein Synonym für **__cdecl** , wenn Compileroption [/Za \(deaktivieren spracherweiterungen)](../build/reference/za-ze-disable-language-extensions.md) angegeben ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Compiler angewiesen, C-Namenskonventionen und C-Aufrufkonventionen für die `system`-Funktion zu verwenden.

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>Siehe auch

[Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)