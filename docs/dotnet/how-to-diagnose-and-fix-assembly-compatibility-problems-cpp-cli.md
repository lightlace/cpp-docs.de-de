---
title: "Gewusst wie: Diagnose und Behebung von Kompatibilit&#228;tsproblemen bei Assemblys (C++/CLI)"
ms.custom: na
ms.date: "12/14/2016"
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
  - "Kompatibilität, Von Assemblys"
  - "Ausnahmen, Ermitteln von abweichendem Verhalten"
  - "Versionskontrolle"
  - "Versionskontrolle, Ermitteln von Konflikten"
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Diagnose und Behebung von Kompatibilit&#228;tsproblemen bei Assemblys (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden die Folgen erläutert, die auftreten können, wenn die Version einer Assembly, auf die während der Kompilierung verwiesen wird, nicht mit der Version kompatibel ist, auf die während der Laufzeit verwiesen wird. Es wird außerdem erläutert, wie dieses Problem vermieden werden kann.  
  
 Beim Kompilieren einer Assembly kann unter Umständen mit der `#using`\-Syntax auf andere Assemblys verwiesen werden.  Während der Kompilierung greift der Compiler auf diese Assemblys zu.  Die Informationen aus diesen Assemblys werden verwendet, um Optimierungsentscheidungen zu treffen.  
  
 Wenn jedoch die Assembly, auf die verwiesen wird, verändert und neu kompiliert wurde, aber die davon abhängige, verweisende Assembly nicht neu kompiliert wird, dann kann es sein, dass die Assemblys nicht mehr kompatibel sind.  Optimierungsentscheidungen, die vorher gültig waren, sind aufgrund der neuen Assemblyversion möglicherweise nicht mehr richtig.  Diese Inkompatibilitäten können verschiedene Laufzeitfehler zur Folge haben.  In solchen Fällen werden keine spezifischen Ausnahmen erzeugt.  Wie der Fehler zur Laufzeit gemeldet wird, hängt von der Art der Codeänderung ab, die das Problem verursacht hat.  
  
 Solange die gesamte Anwendung für die freigegebene Version des Produkts neu erstellt wird, sollten diese Fehler im endgültigen Produktionscode kein Problem darstellen.  Assemblys, die für die Öffentlichkeit freigegeben werden, sollten mit einer offiziellen Versionsnummer gekennzeichnet werden, um derartige Probleme zu vermeiden.  Weitere Informationen finden Sie unter [Assemblyversionen](../Topic/Assembly%20Versioning.md).  
  
### Diagnose und Behebung eines Inkompatibilitätsfehlers  
  
1.  Wenn Laufzeitausnahmen oder andere Fehlerbedingungen in Code auftreten, der einen Verweis auf eine andere Assembly enthält, und keine andere Ursache festgestellt werden kann, liegt möglicherweise eine veraltete Assembly vor.  
  
2.  Isolieren und reproduzieren Sie zuerst die Ausnahme oder Fehlerbedingung.  Ein Problem, das aufgrund einer durch überholte Daten verursachten Ausnahme auftritt, sollte reproduzierbar sein.  
  
3.  Überprüfen Sie die Timestamps aller Assemblys, auf die in der Anwendung verwiesen wird.  
  
4.  Wenn einer der Timestamps der Assemblys, auf die verwiesen wird, neuer als der Timestamp der letzten Kompilierung der Anwendung ist, dann ist die Anwendung veraltet.  Kompilieren Sie in diesem Fall die Anwendung mit der neuesten Version der Assembly, und nehmen Sie alle erforderlichen Änderungen am Code vor.  
  
5.  Führen Sie die Anwendung erneut aus, und versuchen Sie, das Problem zu reproduzieren. Vergewissern Sie sich, dass die Ausnahme nicht mehr auftritt.  
  
## Beispiel  
 Das folgende Programm veranschaulicht das Problem, indem der Zugriff auf eine Methode reduziert und anschließend versucht wird, auf diese Methode in einer anderen Assembly zuzugreifen, ohne eine Neukompilierung durchzuführen.  Versuchen Sie, zuerst `changeaccess.cpp` zu kompilieren.  Dies ist die Assembly, auf die verwiesen wird und die sich ändert.  Kompilieren Sie anschließend `referencing.cpp`.  Die Kompilierung wird erfolgreich durchgeführt.  Reduzieren Sie jetzt den Zugriff der aufgerufenen Methode.  Kompilieren Sie erneut `changeaccess.cpp` mit dem Flag `/DCHANGE_ACCESS`.  Dadurch wird die Methode geschützt – und nicht privat – und kann somit länger legal aufgerufen werden.  Führen Sie die Anwendung erneut aus, ohne `referencing.exe` neu zu kompilieren.  Daraufhin wird die Ausnahme <xref:System.MethodAccessException> ausgelöst werden.  
  
```  
// changeaccess.cpp  
// compile with: /clr:safe /LD  
// After the initial compilation, add /DCHANGE_ACCESS and rerun  
// referencing.exe to introduce an error at runtime. To correct  
// the problem, recompile referencing.exe  
  
public ref class Test {  
#if defined(CHANGE_ACCESS)  
protected:  
#else  
public:  
#endif  
  
  int access_me() {  
    return 0;  
  }  
  
};  
  
```  
  
```  
// referencing.cpp  
// compile with: /clr:safe   
#using <changeaccess.dll>  
  
// Force the function to be inline, to override the compiler's own  
// algorithm.  
__forceinline  
int CallMethod(Test^ t) {  
  // The call is allowed only if access_me is declared public  
  return t->access_me();  
}  
  
int main() {  
  Test^ t = gcnew Test();  
  try  
  {  
    CallMethod(t);  
    System::Console::WriteLine("No exception.");  
  }  
  catch (System::Exception ^ e)  
  {  
    System::Console::WriteLine("Exception!");  
  }  
  return 0;  
}  
  
```  
  
## Siehe auch  
 [\#using\-Direktive](../preprocessor/hash-using-directive-cpp.md)   
 [Verwaltete Typen](../dotnet/managed-types-cpp-cli.md)