---
title: NETMODULE-Dateien als Linkereingabe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23a1ecdff483118d92ac2c5fd01c24e8f2599bc6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="netmodule-files-as-linker-input"></a>.NETMODULE-Dateien als Eingabe für den Linker
Link.exe akzeptiert nun MSIL-OBJ- und NETMODULE-Dateien als Eingabe an. Die Ausgabedatei, die vom Linker erstellt werden, eine Assembly oder eine NETMODULE-Datei mit keine Abhängigkeit zur Laufzeit auf Änderungen an den obj oder NETMODULE-Dateien, die an den Linker eingegeben wurden.  
  
 NETMODULE-Dateien werden von der Visual C++-Compiler erstellt [/ln (Erstellen von MSIL-Modul)](../../build/reference/ln-create-msil-module.md) oder vom Linker mit [/NOASSEMBLY (Erstellen eines MSIL-Moduls)](../../build/reference/noassembly-create-a-msil-module.md). OBJ-Dateien werden immer in einer Visual C++-Kompilierung erstellt. Verwenden Sie für andere Visual Studio-Compiler die **/target: Module** -Compileroption.  
  
  Sie müssen an den Linker die OBJ-Datei aus der Visual C++-Kompilierung übergeben, die die NETMODULE-Datei erstellt. Übergeben eines .netmodule wird nicht mehr unterstützt, da die **/CLR: pure** und **/CLR: safe** Compileroptionen sind in Visual Studio 2015 als veraltet markiert und wird in einer zukünftigen Version des Compilers entfernt.   
  
 Informationen zum Aufrufen des Linkers in der Befehlszeile finden Sie unter [Linker Befehlszeilensyntax](../../build/reference/linker-command-line-syntax.md), [Erstellen von C/C++-Code in der Befehlszeile](../../build/building-on-the-command-line.md), und [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Einer NETMODULE-Datei oder DLL-Datei an den Linker übergeben, die von der Visual C++-Compiler kompiliert wurde **"/ CLR"** kann dazu führen, einen Linkerfehler. Weitere Informationen finden Sie unter [auswählen des Formats von netmodule Eingabedateien](../../build/reference/choosing-the-format-of-netmodule-input-files.md).  
  
 Der Linker akzeptiert systemeigene OBJ-Dateien als auch MSIL-OBJ-Dateien kompiliert mit **"/ CLR"**. Bei der Übergabe gemischter OBJ-Dateien im selben Build wird die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig die unterste Ebene der Überprüfbarkeitsstufe der Eingabemodule gleich sein. 
  
 Wenn Sie derzeit eine Anwendung, die zusammengesetzt ist, wird von zwei oder mehrere Assemblys und die Anwendung, die in einer Assembly enthalten sein soll, müssen Sie die Assemblys neu kompilieren und verknüpfen Sie die OBJ- oder NETMODULE-Dateien auf eine einzelne Assembly erzeugen.  
  
 Sie müssen angeben, ein Eintrag mit [/Entry (Symbol für Einstiegspunkt)](../../build/reference/entry-entry-point-symbol.md) beim Erstellen eines ausführbaren Images.  
  
 Verwenden Sie beim Verknüpfen mit einer MSIL OBJ- oder NETMODULE-Datei [/LTCG (Link-Time Code Generation)](../../build/reference/ltcg-link-time-code-generation.md), andernfalls stößt der Linker die MSIL-OBJ- oder NETMODULE-Datei, neu die Verknüpfung mit/LTCG.  
  
 MSIL OBJ- oder NETMODULE-Dateien können auch an cl.exe übergeben werden.  
  
 Eingabe MSIL OBJ- oder NETMODULE-Dateien dürfen keine eingebetteten Ressourcen haben. Eine Ressource in eine Ausgabedatei (Modul oder Assembly) eingebettet ist, mit [/ASSEMBLYRESOURCE (Einbetten einer verwalteten Ressource)](../../build/reference/assemblyresource-embed-a-managed-resource.md) (Linkeroption) oder mit der **/Resource** in anderen Visual Studio-Compiler (Compileroption).  
  
 Beim Ausführen der MSIL-Verknüpfung, und wenn Sie nicht auch angeben [/LTCG (Link-Time Code Generation)](../../build/reference/ltcg-link-time-code-generation.md), sehen Sie eine Meldung, dass die Verknüpfung neu gestartet wird. Diese Meldung kann ignoriert werden, aber zum Umfang zur Leistungssteigerung Linker mit MSIL verknüpfen, explizit angeben **/LTCG**.  
  
## <a name="example"></a>Beispiel  
 In C++-Code wird der Catch-Block eines entsprechenden für eine Ausnahme nicht aufgerufen werden. Die CLR umschließt jedoch standardmäßig nicht Systemausnahmen mit <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Wenn eine Assembly aus Visual C++ erstellt wird und nicht Visual C++-Modulen und Sie möchten einen Catch-Block in C++-Code aus der entsprechenden Try-Klausel aufgerufen werden, wenn der Try-Block eine Ausnahme nicht zum System auslöst, müssen Sie hinzufügen, die  
  
 [assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]-Attribut auf den Quellcode für die nicht-c++-Module.  
  
```  
// MSIL_linking.cpp  
// compile with: /c /clr  
value struct V {};  
  
ref struct MCPP {  
   static void Test() {  
      try {  
         throw (gcnew V);  
      }  
      catch (V ^) {  
         System::Console::WriteLine("caught non System exception in C++ source code file");  
      }  
   }  
};  
  
/*  
int main() {  
   MCPP::Test();  
}  
*/  
```  
  
## <a name="example"></a>Beispiel  
 Durch ändern den booleschen Wert des Attributs WrapNonExceptionThrows, ändern Sie die Fähigkeit des Visual C++-Code, eine nicht-Ausnahme abzufangen.  
  
```  
// MSIL_linking_2.cs  
// compile with: /target:module /addmodule:MSIL_linking.obj  
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console  
using System.Runtime.CompilerServices;  
  
// enable non System exceptions  
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]  
  
class MLinkTest {  
   public static void Main() {  
      try {  
         MCPP.Test();  
      }  
      catch (RuntimeWrappedException) {  
         System.Console.WriteLine("caught a wrapped exception in C#");  
      }  
   }  
}  
```  
  
```Output  
caught non System exception in C++ source code file  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINK-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)