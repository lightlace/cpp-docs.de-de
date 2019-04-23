---
title: '#using-Direktive (C++ / CLI)'
ms.date: 10/18/2018
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
ms.openlocfilehash: ddae6137e94e10f5701e1e7d0f8f7a7514b18662
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034260"
---
# <a name="using-directive-ccli"></a>#using-Direktive (C++ / CLI)

Importiert Metadaten in ein Programm mit kompiliert ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="syntax"></a>Syntax

```
#using file [as_friend]
```

### <a name="parameters"></a>Parameter

*datei*<br/>
Eine DLL-, EXE-, NETMODULE- oder OBJ-Datei für MSIL. Ein auf ein Objekt angewendeter

`#using <MyComponent.dll>`

*as_friend*<br/>
Gibt an, dass alle Typen in *Datei* zugegriffen werden. Weitere Informationen finden Sie unter [Friend-Assemblys (C++)](../dotnet/friend-assemblies-cpp.md).

## <a name="remarks"></a>Hinweise

*Datei* eine Microsoft intermediate Language (MSIL)-Datei, die Sie importieren für die verwaltete Daten und verwalteten Konstrukte. Wenn eine DLL-Datei ein Assemblymanifest enthält, und klicken Sie dann alle DLLs, die im Manifest verwiesen wird importiert, und die Assembly, die Sie beim Erstellen listet *Datei* in den Metadaten als Assemblyverweis.

Wenn *Datei* enthält keine Assembly (Wenn *Datei* ist ein Modul), und wenn Sie nicht beabsichtigen, Typinformationen aus dem Modul in der aktuellen (Assembly-) Anwendung verwendet werden, Sie haben die Möglichkeit, nur gibt an, dass das Modul ist Teil der Assembly. Verwenden Sie [ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md). Die Typen im Modul wären dann für jede Anwendung verfügbar, die auf die Assembly verweist.

Eine Alternative zur Verwendung **#using** ist die [/FU](../build/reference/fu-name-forced-hash-using-file.md) -Compileroption.

.exe-Assemblys, die an **#using** kompiliert werden soll mit einem der Visual Studio .NET Compiler (Visual Basic oder Visual C#-, z. B.).  Der Versuch, Metadaten von einer EXE-Assembly zu importieren, die mit `/clr` kompiliert wurde, führt zu einem Ausnahmefehler beim Laden der Datei.

> [!NOTE]
> Eine Komponente, die mit verwiesen wird **#using** kann ausgeführt werden, mit einer anderen Version der Datei importiert, die zum Zeitpunkt der Kompilierung, dass eine Clientanwendung unerwartete Ergebnisse zurückgibt.

Damit der Compiler einen Typ in einer Assembly (nicht in einem Modul) erkennen kann, muss die Auflösung des Typs erzwungen werden, beispielsweise durch die Definition einer Instanz des Typs. Der Compiler verfügt über andere Möglichkeiten, Typnamen in einer Assembly aufzulösen. Beispielsweise wird dem Compiler beim Erben von einem Typ in einer Assembly der Typname mitgeteilt.

Beim Importieren von Metadaten, die erstellt werden, aus dem Quellcode, der verwendet [__declspec(thread)](../cpp/thread.md), die Thread-Semantik werden in den Metadaten nicht beibehalten. Z. B. eine Variable mit **__declspec(thread)**, in ein Programm, das für die common Language Runtime von .NET Framework, und klicken Sie dann über importiert kompilierten **#using**, müssen Sie nicht mehr **__declspec(thread)** Semantik für die Variable.

Alle importierten Typen (verwaltet und systemeigen) in eine Datei **#using** verfügbar sind, aber der Compiler behandelt systemeigene Typen, die Deklarationen keine Definitionen.

Auf "mscorlib.dll" wird automatisch beim Kompilieren mit `/clr` verwiesen.

Die LIBPATH-Umgebungsvariable gibt die Verzeichnisse, die durchsucht werden, wenn der Compiler versucht, Auflösen von Dateinamen, die an **#using**.

Der Compiler sucht unter folgendem Pfad nach Verweisen:

- Ein im angegebenen Pfad die **#using** Anweisung.

- Das aktuelle Verzeichnis.

- Das .NET Framework-Systemverzeichnis.

- Verzeichnisse hinzugefügt, mit der [/AI](../build/reference/ai-specify-metadata-directories.md) -Compileroption.

- Verzeichnisse der LIBPATH-Umgebungsvariable.

## <a name="example"></a>Beispiel

Wenn Sie eine Assembly (C) erstellen und auf eine Assembly (B) verweisen, die selbst auf eine andere Assembly (A) verweist, müssen Sie nicht explizit auf Assembly A verweisen, es sei denn, Sie verwenden explizit einen der Typen von A in C.

```cpp
// using_assembly_A.cpp
// compile with: /clr /LD
public ref class A {};
```

## <a name="example"></a>Beispiel

```cpp
// using_assembly_B.cpp
// compile with: /clr /LD
#using "using_assembly_A.dll"
public ref class B {
public:
   void Test(A a) {}
   void Test() {}
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel tritt aufgrund der fehlenden Verweise auf "using_assembly_A.dll" kein Compilerfehler auf, da das Programm keinen der Typen verwendet, die in "using_assembly_A.cpp" definiert sind.

```cpp
// using_assembly_C.cpp
// compile with: /clr
#using "using_assembly_B.dll"
int main() {
   B b;
   b.Test();
}
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)