---
title: ".NETMODULE-Dateien als Eingabe f&#252;r den Linker"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".netmodules"
  - "Verknüpfen [C++], Module"
  - "Module, Visual C++"
  - "MSIL verknüpfen"
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# .NETMODULE-Dateien als Eingabe f&#252;r den Linker
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

link.exe akzeptiert jetzt MSIL .obj und .netmodules, als Eingabe.  Die Ausgabedatei, die vom Linker erzeugt wird, ist eine Assembly oder .netmodule ohne Ablaufabhängigkeit auf einem der OBJ\-Datei oder der .netmodules, die als Eingabe für den Linker wurden.  
  
 .netmodules werden vom Visual C\+\+\-Compiler mit [\/LN \(Erstellen eines MSIL\-Moduls\)](../../build/reference/ln-create-msil-module.md) oder durch den Linker mit [\/NOASSEMBLY \(MSIL\-Modul erstellen\)](../../build/reference/noassembly-create-a-msil-module.md) erstellt. OBJ\-Dateien werden stets in einer Visual C\+\+\-Kompilierung erstellt.  Verwenden Sie bei anderen Visual Studio\-Compilern die **\/target:module**\-Compileroption.  
  
 In den meisten Fällen müssen Sie für den Linker die OBJ\-Datei von der Visual C\+\+\-Kompilierung übergeben, die .netmodule erstellte, es sei denn, .netmodule mit [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) erstellt wurde.  MSIL .netmodules, das verwendet wird, wie als Eingabe für den Linker, muss MSIL reines sein, das vom Visual C\+\+\-Compiler erzeugten, kann der **\/clr:safe** verwendet.  Andere Visual Studio\-Compiler erzeugen standardmäßig reine MSIL\-Module.  
  
 Informationen zum Aufrufen des Linkers über die Befehlszeile finden Sie unter [Syntax für die Linkerbefehlszeile](../../build/reference/linker-command-line-syntax.md) und [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Das Übergeben von .netmodule oder von DLL\-Datei den Linker, der vom Visual C\+\+\-Compiler mit **\/clr** oder mit **\/clr:pure** kompiliert wurde, kann keinen Linkerfehler führen.  Weitere Informationen finden Sie unter [Auswählen des Formats von .netmodule\-Eingabedateien](../../build/reference/choosing-the-format-of-netmodule-input-files.md).  
  
 Der Linker akzeptiert systemeigene OBJ\-Dateien sowie mit **\/clr**, **\/clr:pure** oder **\/clr:safe** kompilierte MSIL\-OBJ\-Dateien.  Bei der Übergabe gemischter OBJ\-Dateien im selben Build entspricht die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig der geringsten Überprüfbarkeitsstufe der Eingabemodule.  Wenn Sie beispielsweise eine überprüfbare und reine \(safe und pure\) OBJ\-Datei an den Linker übergeben, ist die Ausgabedatei rein \(pure\).  Mit [\/CLRIMAGETYPE \(Angeben des CLR\-Bildtyps\)](../../build/reference/clrimagetype-specify-type-of-clr-image.md) können Sie gegebenenfalls eine geringere Überprüfbarkeit angeben.  
  
 Wenn Sie eine Anwendung, die aus zwei oder mehr besteht Assemblys und Sie möchten die Anwendung, in einer Assembly enthalten werden haben, müssen Sie die Assembly neu kompilieren und das .objs oder das .netmodules und verknüpfen, um eine einzelne Assembly zu erzeugen.  
  
 Sie müssen mit [\/ENTRY \(Symbol für Einstiegspunkt\)](../../build/reference/entry-entry-point-symbol.md) einen Einstiegspunkt angeben, wenn Sie ein ausführbares Bild erstellen.  
  
 Beim Verknüpfen mit einem oder .netmodule\-Datei MSIL .obj, dem [\/LTCG \(Code zur Verknüpfungszeit generieren\)](../../build/reference/ltcg-link-time-code-generation.md); andernfalls, wenn der Linker die MSIL .obj oder .netmodule trifft, wird sie den Link mit \/LTCG neu.  
  
 MSIL .obj oder .netmodule\-Dateien können in CL.EXE auch übergeben werden.  
  
 Eingabe MSIL .obj oder .netmodule\-Dateien Eingebettete Ressourcen können nicht haben.  Eine Ressource wird mit der [\/ASSEMBLYRESOURCE \(Verwaltete Ressource einbetten\)](../../build/reference/assemblyresource-embed-a-managed-resource.md)\-Linkeroption oder in anderen Visual Studio\-Compilern mit der **\/resource**\-Compileroption in eine Ausgabedatei \(Modul oder Assembly\) eingebettet.  
  
 Wenn Sie die MSIL\-Verknüpfung ausführen, ohne auch [\/LTCG \(Code zur Verknüpfungszeit generieren\)](../../build/reference/ltcg-link-time-code-generation.md) angegeben zu haben, erhalten Sie eine Meldung mit der Information, dass die Verknüpfung neu gestartet wird.  Sie können diese Meldung ignorieren, zur Verbesserung der Linkerleistung bei der MSIL\-Verknüpfung sollten Sie jedoch explizit **\/LTCG** angeben.  
  
## Beispiel  
 In C\+\+\-Code wird für eine systemfremde Ausnahme der catch\-Block eines dazugehörigen try\-Blocks aufgerufen.  Standardmäßig umschließt die CLR systemfremde Ausnahmen mit <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  Wenn eine Assembly aus Visual C\+\+\-Modulen und nicht mit Visual C\+\+ geschriebenen Modulen erstellt wurde und beim Auslösen einer systemfremden Ausnahme durch einen try\-Block der entsprechende catch\-Block im C\+\+\-Code aus seiner zugehörigen try\-Klausel aufgerufen werden soll, müssen Sie das folgende Attribut zum Quellcode für nicht in C\+\+ geschriebene Module hinzufügen:  
  
 \[assembly:System::Runtime::CompilerServices::RuntimeCompatibility \(WrapNonExceptionThrows\=false\)\]  
  
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
  
## Beispiel  
 Wenn Sie den booleschen Wert für das WrapNonExceptionThrows\-Attribut ändern, ändern Sie die Fähigkeit des Visual C\+\+\-Codes, eine systemfremde Ausnahme abzufangen.  
  
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
  
  **Systemfremde Ausnahme in C\+\+\-Quellcodedatei abgefangen**   
## Siehe auch  
 [LINK\-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)