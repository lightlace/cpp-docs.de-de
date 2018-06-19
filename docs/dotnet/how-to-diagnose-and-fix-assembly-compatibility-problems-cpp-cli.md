---
title: 'Vorgehensweise: Diagnose und Behebung von Kompatibilitätsproblemen bei Assemblys (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4440ab455aff8922c108cdb35cff041cd67f56d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133419"
---
# <a name="how-to-diagnose-and-fix-assembly-compatibility-problems-ccli"></a>Gewusst wie: Diagnose und Behebung von Kompatibilitätsproblemen bei Assemblys (C++/CLI)
In diesem Thema wird erläutert, was passieren kann, wenn die Version einer Assembly verwiesen wird, zum Zeitpunkt der Kompilierung nicht mit der Version der Assembly verwiesen wird, zur Laufzeit übereinstimmt und wie Sie das Problem zu vermeiden.  
  
 Wenn eine Assembly kompiliert wird, können andere Assemblys verwiesen werden, mit der `#using` Syntax. Diese Assemblys werden bei der Kompilierung durch den Compiler zugegriffen. Informationen über diese Assemblys wird verwendet, um Optimierung Entscheidungen zu treffen.  
  
 Wenn jedoch die referenzierte Assembly geändert und neu kompiliert wird, und kompilieren Sie nicht die verweisende Assembly, die davon abhängigen ist neu, die Assemblys möglicherweise nicht kompatibel sein. Optimierung Entscheidungen, die bei gültig waren möglicherweise zuerst nicht in Bezug auf die neue Version der Assembly richtig sind. Aufgrund dieser Inkompatibilitäten können verschiedene Laufzeitfehler auftreten. Es gibt keine spezifischen Ausnahmen, die in einem solchen Fall erzeugt werden. Die Möglichkeit, die der Fehler zur Laufzeit gemeldet wird, hängt von den Charakter der Änderung des Codes, die das Problem verursacht hat.  
  
 Diese Fehler sollte ein Problem in der endgültigen Produktionscode nicht, solange die gesamte Anwendung für die freigegebene Version Ihres Produkts neu erstellt wird. Assemblys, die öffentlich freigegeben werden sollte mit einer Anzahl offiziellen Version gekennzeichnet werden, um sicherzustellen, dass diese Probleme vermieden werden. Weitere Informationen dazu finden Sie unter [Assemblyversionen](/dotnet/framework/app-domains/assembly-versioning).  
  
### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>Diagnostizieren und Beheben eines Inkompatibilitätsfehlers  
  
1.  Wenn Sie auftreten Laufzeitausnahmen oder andere fehlerbedingungen, die im Code auftreten, die auf eine andere Assembly verweist, und keine anderen identifizierten Ursache haben, können Sie mit einer Assembly nicht mehr aktuell arbeiten.  
  
2.  Zunächst isolieren, und die Ausnahme oder andere Fehler zu reproduzieren. Ein Problem, das aufgrund einer veralteten Ausnahme auftritt, sollten reproduziert werden.  
  
3.  Überprüfen Sie die Timestamps aller Assemblys, auf die in Ihrer Anwendung verwiesen wird.  
  
4.  Wenn die Zeitstempel von alle referenzierten Assemblys höher als der Zeitstempel der letzten Kompilierung der Anwendung sind, ist Ihre Anwendung nicht mehr aktuell. In diesem Fall wird kompilieren Sie die Anwendung mit der aktuellen Assembly neu, und stellen Sie alle codeänderungen, die erforderlich sind.  
  
5.  Führen Sie die Anwendung erneut aus, führen Sie die Schritte, die das Problem zu reproduzieren, und stellen Sie sicher, dass die Ausnahme nicht auftritt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Programm veranschaulicht das Problem, indem der Zugriff auf eine Methode reduziert und Aufrufen dieser Methode in einer anderen Assembly ohne erneutes kompilieren möchten. Kompilieren Sie `changeaccess.cpp` erste. Dies ist die referenzierte Assembly, wodurch geändert werden. Kompilieren Sie dann `referencing.cpp`. Die Kompilierung erfolgreich ausgeführt wird. Reduzieren Sie jetzt den Zugriff auf die aufgerufene Methode. RECOMPILE `changeaccess.cpp` mit dem Flag `/DCHANGE_ACCESS`. Dadurch wird die Methode geschützten, anstatt privat ist, damit diese mehr gesetzlich aufgerufen werden können. Ohne erneute Kompilierung `referencing.exe`, führen Sie die Anwendung erneut aus. Eine Ausnahme <xref:System.MethodAccessException> führt.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [#using-Direktive](../preprocessor/hash-using-directive-cpp.md)   
 [Verwaltete Typen (C++/CLI)](../dotnet/managed-types-cpp-cli.md)