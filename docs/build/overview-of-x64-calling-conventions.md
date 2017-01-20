---
title: "&#220;bersicht &#252;ber x64-Aufrufkonventionen"
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
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
caps.latest.revision: 12
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# &#220;bersicht &#252;ber x64-Aufrufkonventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zwei wichtige Änderungen in [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] gegenüber x86 sind die 64\-Bit\-Adressierbarkeit und ein pauschaler Satz von 16 64\-Bit\-Registern zur allgemeinen Verwendung.  Aufgrund des erweiterten Registersatzes verwendet [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] nur die [\_\_fastcall](../cpp/fastcall.md)\-Aufrufkonvention und ein RISC\-basiertes Ausnahmebehandlungsmodell.  Das `__fastcall`\-Modell verwendet für die ersten vier Argumente Register und zur Übergabe der anderen Parameter den Stapelrahmen.  
  
 Mit der folgenden Compileroption können Sie die Anwendung für [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] optimieren:  
  
-   [\/favor \(Optimieren für Besonderheiten der Architektur\)](../build/reference/favor-optimize-for-architecture-specifics.md)  
  
## Aufrufkonvention  
 Das [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-ABI \(Application Binary Interface\) ist eine Aufrufkonvention mir vier Registern für Schnellaufrufe mit Stapelsicherung für die Register.  Es gibt eine strenge 1:1\-Entsprechung zwischen den Argumenten in einer Funktion und den Registern für diese Argumente.  Argumente, die größer als 8 Bytes sind, bzw. deren Länge nicht 1, 2, 4 oder 8 Bytes entspricht, müssen als Verweis übergeben werden.  Es wird nicht versucht, ein einzelnes Argument auf mehrere Register zu verteilen.  Der x87\-Registerstapel wird nicht verwendet.  Er kann verwendet werden, ist aber zwischen Funktionsaufrufen als flüchtig zu betrachten.  Alle Gleitkommaoperationen werden mithilfe der 16 XMM\-Register durchgeführt.  Die Argumente werden in den Registern RCX, RDX, R8 und R9 übergeben.  Wenn die Argumente vom Format float\/double sind, werden sie in XMM0L, XMM1L, XMM2L und XMM3L übergeben.  16\-Byte\-Argumente werden als Verweis übergeben.  Die Parameterübergabe wird ausführlich unter [Parameterübergabe](../build/parameter-passing.md) beschrieben.  Zusätzlich zu diesen Registern sind RAX, R10, R11, XMM4 und XMM5 flüchtig.  Alle anderen Register sind nicht flüchtig.  Die Verwendung von Registern ist in [Registerverwendung](../build/register-usage.md) und [Gespeicherte Register von Aufrufer\/Aufgerufenem](../build/caller-callee-saved-registers.md) ausführlich dokumentiert.  
  
 Der Aufrufer ist verantwortlich für die Reservierung von Speicherplatz für die an den Aufgerufenen zu übergebenden Parameter und muss stets genügend Speicher für die 4 Registerparameter reservieren, auch wenn der Aufgerufene weniger Parameter hat.  Dies dient einfach der Unterstützung von C\-Funktionen ohne Prototypen und vararg\-Funktionen in C\/C\+\+.  Für vararg\-Funktionen und Funktionen ohne Prototypen müssen alle float\-Werte im entsprechenden Allzweckregister dupliziert werden.  Vor dem Aufruf müssen alle Parameter, die über die ersten vier hinausgehen, auf dem Stapel oberhalb des Sicherungsspeichers für die ersten vier gespeichert werden.  Ausführliche Informationen zu vararg\-Funktionen finden Sie unter [VarArgs](../build/varargs.md).  Ausführliche Informationen zu Funktionen ohne Prototyp finden Sie unter [Funktionen ohne Prototyp](../build/unprototyped-functions.md).  
  
## Ausrichtung  
 Die meisten Strukturen werden gemäß ihrer natürlichen Ausrichtung ausgerichtet.  Hauptsächliche Ausnahmen sind die Stapelzeiger und der malloc\- oder alloca\-Speicher, die zur Leistungsverbesserung auf 16 Bytes ausgerichtet werden.  Eine Ausrichtung auf mehr als 16 Bytes muss manuell erfolgen. Da jedoch 16 Bytes eine verbreitete Ausrichtungsgröße für XMM\-Operationen ist, sollte dies für die meisten Fälle ausreichen.  Weitere Informationen zu Strukturlayout und Ausrichtung finden Sie unter [Typen und Speicher](../build/types-and-storage.md).  Informationen zum Stapellayout finden Sie unter [Verwendung von Stapeln](../build/stack-usage.md).  
  
## Entladbarkeit  
 Alle verzweigenden Funktionen \[Funktionen, die weder eine Funktion aufrufen noch selbst irgendwelchen Stapelspeicher reservieren\] müssen mit Daten gekennzeichnet werden \[diese werden als xdata oder ehdata bezeichnet, auf die pdata zeigen\], die eine Beschreibung für das Betriebssystem enthalten, wie sie ordnungsgemäß zu entladen sind, um die nicht flüchtigen Register freizugeben.  Prologe und Epiloge sind in hohem Maß beschränkt, damit sie ordnungsgemäß in xdata beschrieben werden können.  In jedem Codebereich, der nicht Teil eines Epilogs oder Prologs ist, muss der Stapelzeiger auf 16 Bytes ausgerichtet werden, außer für Endfunktionen.  Ausführliche Informationen über die richtige Struktur von Funktionsprologen und \-epilogen finden Sie unter [Prolog und Epilog](../build/prolog-and-epilog.md).  Weitere Informationen über Ausnahmebehandlung und Ausnahmebehandlung\/Entladen von pdata und xdata finden Sie unter [Ausnahmebehandlung \(x64\)](../build/exception-handling-x64.md).  
  
## Siehe auch  
 [x64\-Softwarekonventionen](../build/x64-software-conventions.md)