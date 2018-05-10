---
title: '#using-Anweisung (C + c++ / CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
dev_langs:
- C++
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 053c425a6bb8dcab0dc5cb94db1537f0fff3d9f8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="using-directive-cclr"></a>#using-Anweisung (C + c++ / CLR)
Importiert Metadaten in einem Programm kompiliert mit ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
#using file [as_friend]  
```  
  
#### <a name="parameters"></a>Parameter  
 `file`  
 Eine DLL-, EXE-, NETMODULE- oder OBJ-Datei für MSIL. Ein auf ein Objekt angewendeter  
  
 `#using <MyComponent.dll>`  
  
 as_friend  
 Gibt an, dass auf alle Typen in `file` zugegriffen werden kann.  Weitere Informationen finden Sie unter [Friend-Assemblys (C++)](../dotnet/friend-assemblies-cpp.md).  
  
## <a name="remarks"></a>Hinweise  
 `file` kann eine MSIL-Datei (Microsoft Intermediate Language) sein, die Sie aufgrund ihrer verwalteten Daten und verwalteten Konstrukte importieren. Wenn eine DLL-Datei ein Assemblymanifest enthält, und klicken Sie dann alle DLLs, die im Manifest verwiesen werden importiert und die Assembly, die Sie erstellen werden aufgelistet *Datei* in den Metadaten als Verweis auf eine Assembly.  
  
 Wenn `file` enthält keine Assembly (Wenn `file` ist ein Modul) und wenn Sie nicht beabsichtigen, Typinformationen aus dem Modul in der aktuellen (Assembly-) Anwendung zu verwenden, stehen Ihnen die Möglichkeit, nur anzugeben, dass das Modul Teil ist die Assembly; verwenden Sie [ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md). Die Typen im Modul wären dann für jede Anwendung verfügbar, die auf die Assembly verweist.  
  
 Eine Alternative zur Verwendung `#using` ist die [/FU](../build/reference/fu-name-forced-hash-using-file.md) -Compileroption.  
  
 übergebene .exe-Assemblys zu `#using` kompiliert werden soll mithilfe der Visual Studio .NET Compiler (Visual Basic oder Visual C#-Beispiel).  Beim Importieren von Metadaten aus einer .exe-Assembly kompiliert, die mit **"/ CLR"** führt zu einer Ausnahme beim Laden von Datei.  
  
> [!NOTE]
>  Eine Komponente, auf die mit `#using` verwiesen wird, kann mit einer anderen Version der Datei ausgeführt werden, die zur Kompilierzeit importiert wurde. Dies führt dazu, dass eine Clientanwendung unerwartete Ergebnisse zurückgibt.  
  
 Damit der Compiler einen Typ in einer Assembly (nicht in einem Modul) erkennen kann, muss die Auflösung des Typs erzwungen werden, beispielsweise durch die Definition einer Instanz des Typs. Der Compiler verfügt über andere Möglichkeiten, Typnamen in einer Assembly aufzulösen. Beispielsweise wird dem Compiler beim Erben von einem Typ in einer Assembly der Typname mitgeteilt.  
  
 Beim Importieren von Metadaten, die aus Quellcode, mit denen erstellt [__declspec(thread)](../cpp/thread.md), die Thread-Semantik nicht in Metadaten beibehalten werden. Angenommen, eine Variable mit **__declspec(thread)** in einem Programm, das Build für die common Language Runtime von .NET Framework und importiert dann über kompilierten `#using`, nicht mehr **__declspec ( Thread)** Semantik für die Variable.  
  
 Alle importierten Typen (sowohl verwaltete als auch systemeigene) in einer Datei, auf die von `#using` verwiesen wird, sind verfügbar. Der Compiler behandelt systemeigene Typen jedoch als Deklarationen und nicht als Definitionen.  
  
 "mscorlib.dll" wird automatisch beim Kompilieren mit referenziert **"/ CLR"**.  
  
 Die LIBPATH-Umgebungsvariable gibt die Verzeichnisse an, die durchsucht werden, wenn der Compiler versucht, Dateinamen aufzulösen, die an `#using` übergeben werden.  
  
 Der Compiler sucht unter folgendem Pfad nach Verweisen:  
  
-   Ein in der `#using`-Anweisung angegebener Pfad.  
  
-   Das aktuelle Verzeichnis.  
  
-   Das .NET Framework-Systemverzeichnis.  
  
-   Verzeichnisse hinzugefügt, mit der [/AI](../build/reference/ai-specify-metadata-directories.md) -Compileroption.  
  
-   Verzeichnisse der LIBPATH-Umgebungsvariable.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie eine Assembly (C) erstellen und auf eine Assembly (B) verweisen, die selbst auf eine andere Assembly (A) verweist, müssen Sie nicht explizit auf Assembly A verweisen, es sei denn, Sie verwenden explizit einen der Typen von A in C.  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## <a name="example"></a>Beispiel  
  
```  
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
  
```  
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