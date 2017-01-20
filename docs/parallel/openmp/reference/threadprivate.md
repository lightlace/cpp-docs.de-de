---
title: "threadprivate"
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
  - "threadprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threadprivate OpenMP directive"
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# threadprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass eine Variable zu einem Thread privat ist.  
  
## Syntax  
  
```  
#pragma omp threadprivate(var)  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `var`  
 Eine durch Trennzeichen getrennte Liste von Variablen, die als privat Sie zu einem Thread ausführen möchten.  `var` NAMESPACE\-bewertete muss entweder eine globale oder statische Variable sein oder eine lokale Variable.  
  
## Hinweise  
 Die `threadprivate`\-Direktiven unterstützen keine OpenMP\-Klauseln.  
  
 Weitere Informationen finden Sie unter [threadprivate Direktive 2.7.1](../../../parallel/openmp/2-7-1-threadprivate-directive.md).  
  
 Die `threadprivate`\-Direktive basieren auf das Attribut [Thread](../../../cpp/thread.md)`__declspec` . **\_\_declspec \(thread\)** Begrenzungen gelten für `threadprivate`.  
  
 Sie können in jedem `threadprivate` DLL nicht verwenden, das über [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)geladen wird.  Dies schließt DLL ein, das [\/DELAYLOAD \(Laden von Import verzögern\)](../../../build/reference/delayload-delay-load-import.md)geladen werden, das auch **LoadLibrary**verwendet.  
  
 Sie können `threadprivate` in einer DLL verwenden, die statisch am Start Prozess geladen wird.  
  
 Da `threadprivate` auf Grundlage **\_\_declspec \(thread\)**vorhanden ist `threadprivate` eine Variable in einem beliebigen Thread, der im Prozess, nicht nur diese Threads gestartet wird, die Teil eines Threads Teams sind, das durch einen parallelen Bereich erstellt wird.  Dies ist ein Implementierungsdetail, die Sie beachten sollten, da Sie sich z. B. Konstruktoren für einen benutzerdefinierten Typ `threadprivate` erwartet dann häufig aufgerufen.  
  
 Eine `threadprivate`\-Variable eines Typs destructable ist nicht gewährleistet, dass ihr aufgerufene Destruktoren verfügen.  Beispiele:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 Benutzer haben kein Steuerelement in Bezug auf, wenn die Threads, die den parallelen Bereich beendet wird, bewertet.  Wenn diese Threads vorhanden sein, wenn der Prozess beendet wird, die Threads nicht zu den Prozess beendet wird benachrichtigt werden und der Destruktor nicht für `threaded_var` auf einen beliebigen Thread aufgerufen wird, der außer dem hier beendet \(der primäre Thread\).  Deshalb sollte Code nicht auf richtiger Zerstörung von `threadprivate`\-Variablen zählen.  
  
## Beispiel  
 Ein Beispiel zur Verwendung von `threadprivate`finden Sie unter [Private](../../../parallel/openmp/reference/private-openmp.md).  
  
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)