---
title: '#using-Direktive (C++/CLI)'
ms.date: 08/29/2019
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
ms.openlocfilehash: 5dae5c277055157aef5451c19ee020fbbd2aaccb
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220201"
---
# <a name="using-directive-ccli"></a>#using-Direktive (C++/CLI)

Importiert Metadaten in ein Programm, das mit [/CLR](../build/reference/clr-common-language-runtime-compilation.md)kompiliert wurde.

## <a name="syntax"></a>Syntax

> **#using** *Datei* [**as_friend**]

### <a name="parameters"></a>Parameter

*Datei*\
Eine DLL-, EXE-, NETMODULE- oder OBJ-Datei für MSIL. Ein auf ein Objekt angewendeter

`#using <MyComponent.dll>`

**as_friend**\
Gibt an, dass auf alle Typen in der *Datei* zugegriffen werden kann. Weitere Informationen finden Sie unter Friend-Assemblys [(C++)](../dotnet/friend-assemblies-cpp.md).

## <a name="remarks"></a>Hinweise

bei der *Datei* kann es sich um eine MSIL-Datei (Microsoft Intermediate Language) handeln, die Sie für die verwalteten Daten und verwalteten Konstrukte importieren. Wenn eine DLL-Datei ein Assemblymanifest enthält, werden alle DLLs, auf die im Manifest verwiesen wird, importiert, und die Assembly, die Sie erstellt, listet die *Datei* in den Metadaten als Assemblyverweis auf.

Wenn die *Datei* keine Assembly enthält (wenn die *Datei* ein Modul ist) und Sie nicht beabsichtigen, Typinformationen aus dem Modul in der aktuellen (assemblyanwendung) zu verwenden, haben Sie die Möglichkeit, nur anzugeben, dass das Modul Teil der Assembly ist. Verwenden Sie [/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md). Die Typen im Modul wären dann für jede Anwendung verfügbar, die auf die Assembly verweist.

Eine Alternative zur Verwendung von **#using** ist die [/Fu](../build/reference/fu-name-forced-hash-using-file.md) -Compileroption.

. exe-Assemblys, die an **#using** weitergegeben werden, sollten mithilfe eines der .net Visual Studio-Compiler C#(z. b. Visual Basic oder Visual) kompiliert werden.  Der Versuch, Metadaten von einer EXE-Assembly zu importieren, die mit `/clr` kompiliert wurde, führt zu einem Ausnahmefehler beim Laden der Datei.

> [!NOTE]
> Eine Komponente, auf die mit **#using** verwiesen wird, kann mit einer anderen Version der Datei ausgeführt werden, die zur Kompilierzeit importiert wurde, wodurch eine Client Anwendung unerwartete Ergebnisse liefert.

Damit der Compiler einen Typ in einer Assembly (nicht in einem Modul) erkennen kann, muss er gezwungen werden, den Typ aufzulösen. Sie können dies erzwingen, indem Sie z. b. eine Instanz des Typs definieren. Es gibt weitere Möglichkeiten, Typnamen in einer Assembly für den Compiler aufzulösen. Wenn Sie z. b. von einem Typ in einer Assembly erben, wird der Typname dem Compiler bekannt.

Beim Importieren von Metadaten, die aus Quellcode erstellt wurden, der [__declspec (Thread)](../cpp/thread.md)verwendet hat, wird die Thread Semantik nicht in den Metadaten beibehalten. Beispielsweise verfügt eine mit **__declspec (Thread)** deklarierte Variable, die in einem Programm kompiliert wurde, das für die .NET Framework Common Language Runtime erstellt und dann über **#using**importiert wurde, keine **__declspec (Thread)** -Semantik für die Variable.

Alle importierten Typen (sowohl verwaltete als auch native) in einer Datei, auf die von **#using** verwiesen wird, sind verfügbar, aber der Compiler behandelt systemeigene Typen als Deklarationen, nicht als Definitionen.

Auf "mscorlib.dll" wird automatisch beim Kompilieren mit `/clr` verwiesen.

Die LIBPATH-Umgebungsvariable gibt die Verzeichnisse an, die durchsucht werden sollen, wenn der Compiler an **#using**über gegebene Dateinamen auflöst.

Der Compiler sucht nach Verweisen im folgenden Pfad:

- Ein Pfad, der in der **#using** -Anweisung angegeben ist.

- Das aktuelle Verzeichnis.

- Das .NET Framework-Systemverzeichnis.

- Mit der [/AI](../build/reference/ai-specify-metadata-directories.md) -Compileroption hinzugefügte Verzeichnisse.

- Verzeichnisse der LIBPATH-Umgebungsvariable.

## <a name="example"></a>Beispiel

Wenn Sie eine Assembly (C) erstellen und auf eine Assembly (B) verweisen, die selbst auf eine andere Assembly (a) verweist, müssen Sie nicht explizit auf Assembly A verweisen, es sei denn, Sie verwenden explizit einen der Typen in C.

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

Im folgenden Beispiel gibt es keinen Compilerfehler für den Verweis auf *using_assembly_A. dll*, da das Programm keinen der in *using_assembly_A. cpp*definierten Typen verwendet.

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
