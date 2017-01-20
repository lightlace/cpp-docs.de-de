---
title: "#using-Direktive (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "friend_as_cpp"
  - "#using"
  - "friend_as"
  - "#using_cpp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#using-Direktive"
  - "LIBPATH-Umgebungsvariable"
  - "Präprozessor, Direktiven"
  - "using-Direktive (#using)"
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# #using-Direktive (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Importiert Metadaten in ein Programm, das mit [\/clr](../build/reference/clr-common-language-runtime-compilation.md) kompiliert wurde.  
  
## Syntax  
  
```  
#using file [as_friend]  
```  
  
#### Parameter  
 `file`  
 Eine DLL\-, EXE\-, NETMODULE\- oder OBJ\-Datei für MSIL.  Beispiel:  
  
 `#using <MyComponent.dll>`  
  
 as\_friend  
 Gibt an, dass auf alle Typen in `file` zugegriffen werden kann.  Weitere Informationen finden Sie unter [Friend\-Assemblys \(C\+\+\)](../dotnet/friend-assemblies-cpp.md).  
  
## Hinweise  
 `file` kann eine MSIL\-Datei \(Microsoft Intermediate Language\) sein, die Sie aufgrund ihrer verwalteten Daten und verwalteten Konstrukte importieren.  Wenn eine DLL\-Datei ein Assemblymanifest enthält, werden alle DLLs, auf die im Manifest verwiesen wird, importiert, und die Assembly, die Sie erstellen, listet *file* in den Metadaten als Assemblyverweis auf.  
  
 Wenn `file` keine Assembly enthält \(wenn `file` ein Modul ist\) und wenn Sie nicht beabsichtigen, Typinformationen aus dem Modul in der aktuellen \(Assembly\-\) Anwendung zu verwenden, haben Sie die Möglichkeit, nur anzugeben, dass das Modul Teil der Assembly ist. Verwenden Sie hierfür [\/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  Die Typen im Modul wären dann für jede Anwendung verfügbar, die auf die Assembly verweist.  
  
 Eine Alternative zur Verwendung von `#using` ist die [\/FU](../build/reference/fu-name-forced-hash-using-file.md)\-Compileroption.  
  
 An `#using` übergebene EXE\-Assemblys sollten mit **\/clr:safe** oder **\/clr:pure** oder mit einem der anderen Visual Studio\-Compiler kompiliert werden \(beispielsweise Visual Basic oder Visual C\#\).  Der Versuch, Metadaten von einer EXE\-Assembly zu importieren, die mit **\/clr** kompiliert wurde, führt zu einem Ausnahmefehler beim Laden der Datei.  
  
> [!NOTE]
>  Eine Komponente, auf die mit `#using` verwiesen wird, kann mit einer anderen Version der Datei ausgeführt werden, die zur Kompilierzeit importiert wurde. Dies führt dazu, dass eine Clientanwendung unerwartete Ergebnisse zurückgibt.  
  
 Damit der Compiler einen Typ in einer Assembly \(nicht in einem Modul\) erkennen kann, muss die Auflösung des Typs erzwungen werden, beispielsweise durch die Definition einer Instanz des Typs.  Der Compiler verfügt über andere Möglichkeiten, Typnamen in einer Assembly aufzulösen. Beispielsweise wird dem Compiler beim Erben von einem Typ in einer Assembly der Typname mitgeteilt.  
  
 Wenn die Metadaten importiert werden, die aus Quellcode erstellt wurden, der [\_\_declspec \(Thread\)](../cpp/thread.md) verwendete, wird die Threadsemantik in Metadaten nicht beibehalten.  Beispielsweise weist eine Variable, die mit **\_\_declspec\(thread\)** deklariert wurde, in einem Programm kompiliert wurde, das für die .NET Framework Common Language Runtime erstellt wurde, und dann mithilfe von `#using` importiert wurde, keine **\_\_declspec\(thread\)**\-Semantik mehr für die Variable auf.  
  
 Alle importierten Typen \(sowohl verwaltete als auch systemeigene\) in einer Datei, auf die von `#using` verwiesen wird, sind verfügbar. Der Compiler behandelt systemeigene Typen jedoch als Deklarationen und nicht als Definitionen.  
  
 Auf "mscorlib.dll" wird automatisch beim Kompilieren mit **\/clr** verwiesen.  
  
 Die LIBPATH\-Umgebungsvariable gibt die Verzeichnisse an, die durchsucht werden, wenn der Compiler versucht, Dateinamen aufzulösen, die an `#using` übergeben werden.  
  
 Der Compiler sucht unter folgendem Pfad nach Verweisen:  
  
-   Ein in der `#using`\-Anweisung angegebener Pfad.  
  
-   Das aktuelle Verzeichnis.  
  
-   Das .NET Framework\-Systemverzeichnis.  
  
-   Verzeichnisse, die mit der [\/AI](../build/reference/ai-specify-metadata-directories.md)\-Compileroption hinzugefügt wurden.  
  
-   Verzeichnisse der LIBPATH\-Umgebungsvariable.  
  
## Beispiel  
 Wenn Sie eine Assembly \(C\) erstellen und auf eine Assembly \(B\) verweisen, die selbst auf eine andere Assembly \(A\) verweist, müssen Sie nicht explizit auf Assembly A verweisen, es sei denn, Sie verwenden explizit einen der Typen von A in C.  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## Beispiel  
  
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
  
## Beispiel  
 Im folgenden Beispiel tritt aufgrund der fehlenden Verweise auf "using\_assembly\_A.dll" kein Compilerfehler auf, da das Programm keinen der Typen verwendet, die in "using\_assembly\_A.cpp" definiert sind.  
  
```  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)