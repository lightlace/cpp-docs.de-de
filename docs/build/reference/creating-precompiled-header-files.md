---
title: Erstellen vorkompilierter Headerdateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: pch
dev_langs: C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09c436d55ad7087d407ba580be0b63286b056898
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-precompiled-header-files"></a>Erstellen vorkompilierter Headerdateien
  
Die Microsoft C- und C++-Compiler stellen Optionen für das Vorkompilieren von beliebigem C- oder C++-Code bereit, einschließlich Inlinecode. Mithilfe dieser leistungsstarken Funktion können Sie einen stabilen Codeabschnitt kompilieren, den Code im kompilierten Zustand in einer Datei speichern und bei nachfolgenden Kompilierungen den vorkompilierten Code mit dem noch in Entwicklung befindlichen Code kombinieren. So können nachfolgende Kompilierungen beschleunigt werden, da der bereits stabile Code nicht neu kompiliert werden muss.  
  
Dieses Thema enthält die folgenden Aspekte der vorkompilierten Headerdatei an:  
  
-   [Wann sollte Quellcode vorkompiliert werden?](#when-to-precompile-source-code)  
  
-   [Zwei Methoden für das Vorkompilieren von Code](#two-choices-for-precompiling-code)  
  
-   [Konsistenzregeln für vorkompilierte Header](#precompiled-header-consistency-rules)  
  
-   [Konsistenzregeln zur Verwendung einer vorkompilierten Headerdatei](#consistency-rules-for-per-file-use-of-precompiled-headers)  
  
-   [Konsistenzregeln für "/ Yc" und "/ Yu"](#consistency-rules-for-yc-and-yu)  
  
-   [Verwenden von vorkompilierten Headern in einem Projekt](#using-precompiled-headers-in-a-project)  
  
-   [PCH-Dateien im Erstellungsvorgang](#pch-files-in-the-build-process)  
  
-   [Beispielmakefile für PCH](#sample-makefile-for-pch)  
  
-   [Beispielcode für PCH](#example-code-for-pch)  
  
Referenzinformationen zu den Compileroptionen, die im Zusammenhang mit der vorkompilierte Header finden Sie unter [/y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md).  
  
<a name="when-to-precompile-source-code"></a>  
  
## <a name="when-to-precompile-source-code"></a>Wann sollte Quellcode vorkompiliert werden?  
  
Vorkompilierter Code eignet während des Entwicklungszyklus zum Zeitpunkt der Kompilierung, reduzieren sich insbesondere dann, wenn:  
  
-   Sie verwenden immer eine große Menge an Code, die sich selten ändern.  
  
-   Das Programm besteht aus mehreren Modulen, die einen Standardsatz von Include-Dateien und die gleichen Kompilierungsoptionen verwenden. In diesem Fall alle Includedateien in einem vorkompilierten Header vorkompiliert werden.  
  
Der ersten Kompilierung – das Abonnement, das die vorkompilierte Headerdatei (PCH) erstellt – dauert etwas länger als bei nachfolgenden Kompilierungen. Nachfolgende Kompilierungen können schneller mit vorkompilierter Code fortzufahren.  
  
Sie können C- und C++-Programme vorkompilieren. In C++-Programmierung ist es gängige Praxis, Informationen über die connectorklasse-Schnittstelle in Headerdateien zu trennen. Diese Headerdateien können später in Programmen eingefügt werden, die die Klasse verwenden. Durch das Vorkompilieren von diese Header, können Sie die Zeit reduzieren, die ein Programm zum Kompilieren benötigt.  
  
> [!NOTE]
>  Obwohl Sie nur eine vorkompilierte Headerdatei (.pch) pro Quelldatei verwenden können, können Sie mehrere PCH-Dateien in einem Projekt verwenden.  
  
<a name="two-choices-for-precompiling-code"></a>  
  
# <a name="two-choices-for-precompiling-code"></a>Zwei Methoden für das Vorkompilieren von Code  
  
Mit Visual C++ können Sie alle C- oder C++-Code Vorkompilieren; Sie sind nicht zum Vorkompilieren der Header-Dateien beschränkt.  
  
Vorkompilieren von Planung erforderlich, aber bedeutend schnellere Kompilierungen bietet, wenn Sie den Quellcode als einfache Headerdateien vorkompilieren.  
  
Vorkompilieren Sie Code an, wenn Sie wissen, dass die Quelldateien gemeinsame Headerdateien verwenden, aber Sie sie nicht in der gleichen Reihenfolge schließen oder wenn der Quellcode in die Vorkompilierung enthalten sein sollen.  
  
Die Optionen für vorkompilierte Header sind [/Yc (Datei der vorkompilierten Header erstellen)](../../build/reference/yc-create-precompiled-header-file.md) und [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md). Verwendung **"/ Yc"** einen vorkompilierten Header zu erstellen. Bei Verwendung mit dem optionalen [Hdrstop](../../preprocessor/hdrstop.md) Pragma **"/ Yc"** können Sie beide Headerdateien vorkompilieren und Quellcode. Wählen Sie **"/ Yu"** auf eine vorhandene vorkompilierte Headerdatei in der bestehenden Kompilierung zu verwenden. Sie können auch **/fp** mit der **"/ Yc"** und **"/ Yu"** Optionen aus, um einen alternativen Namen für die vorkompilierte Headerdatei anzugeben.  
  
Der Compiler Option Referenzthemen für **"/ Yu"** und **"/ Yc"** wird erläutert, wie den Zugriff auf diese Funktionen in der Entwicklungsumgebung.  
  
<a name="precompiled-header-consistency-rules"></a>  
  
## <a name="precompiled-header-consistency-rules"></a>Konsistenzregeln für vorkompilierte Header  
  
Da PCH-Dateien Informationen über die Umgebung des Computers sowie Arbeitsspeicher Adressinformationen über das Programm enthalten, sollten Sie nur eine PCH-Datei auf dem Computer verwenden, in dem es erstellt wurde.  
  
<a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>  
  
## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>Konsistenzregeln zur Verwendung einer vorkompilierten Headerdatei

Die ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) -Compileroption können Sie angeben, welche PCH-Datei zu verwenden.  
  
Wenn Sie eine PCH-Datei verwenden, nimmt der Compiler an die gleichen kompilierungsumgebung – denen eine konsistente Compileroptionen, Pragmas usw. –, die gültig war beim Erstellen der PCH-Datei, sofern nicht anders angegeben. Wenn der Compiler eine Inkonsistenz erkannt wird, eine Warnung ausgegeben und Inkonsistenzen bezeichnet, sofern möglich. Solche Warnungen deuten nicht zwangsläufig auf ein Problem mit der PCH-Datei auf; Sie warnen lediglich vor möglichen Konflikten. Konsistenzanforderungen für PCH-Dateien werden in den folgenden Abschnitten beschrieben.  
  
### <a name="compiler-option-consistency"></a>Konsistenz von Compileroptionen  
  
Die folgenden Compileroptionen können eine Inkonsistenz Warnung ausgeben, wenn es sich bei einer PCH-Datei:  
  
-   Makros, die mit der Präprozessor erstellt (/ D) Option muss zwischen der Kompilierung, die die PCH-Datei erstellt und der aktuellen Kompilierung identisch sein. Der Status der definierten Konstanten nicht aktiviert ist, jedoch zu unvorhersehbaren Ergebnissen führt können auftreten, wenn diese ändern.  
  
-   PCH-Dateien funktionieren nicht mit den Optionen/e und/EP.  
  
-   PCH-Dateien müssen erstellt werden, entweder die generieren durchsuchen Info verwenden (/ FR)-Option oder der lokalen Variablen ausschließen (/ Fr) option vor der nachfolgende Kompilierungen, die die PCH-Datei verwenden, diese Optionen verwenden können.  
  
### <a name="c-70-compatible-z7"></a>C 7.0-kompatibel (/ Z7)  
  
Wenn diese Option aktiviert ist, wenn die PCH-Datei erstellt wird, können nachfolgende Kompilierungen, die die PCH-Datei verwenden, die Debuginformationen.  
  
Wenn die C 7.0-kompatibel (/ Z7) Option ist nicht gültig, wenn die PCH-Datei erstellt wird, Kompilierungen, die PCH-Datei, und "/ Z7" verwenden, eine Warnung ausgelöst. Die Debuginformationen werden in der aktuellen OBJ-Datei, und lokale Symbole in der PCH-Datei definiert sind nicht verfügbar, die im Debugger.  
  
### <a name="include-path-consistency"></a>Pfad Konsistenz einschließen  
  
PCH-Datei enthält Informationen zum Includepfad keine, die gültig war, wenn er erstellt wurde. Wenn Sie eine PCH-Datei verwenden, verwendet der Compiler immer den Include-Pfad in der aktuellen Kompilierung angegeben.  
  
### <a name="source-file-consistency"></a>Quelle Konsistenz  
  
Wenn Sie die Option für die vorkompilierte Headerdatei verwenden (/ Yu) angeben, ignoriert der Compiler alle Präprozessordirektiven (einschließlich Pragmas) im Quellcode, der vorkompiliert werden soll. Durch solche Präprozessordirektiven festgelegte Kompilierung muss identisch mit der Kompilierung für die vorkompilierte Headerdatei erstellen (/ Yc)-Option verwendet werden.  
  
### <a name="pragma-consistency"></a>Pragma-Konsistenz    
  
Pragmas, die in der Regel während der Erstellung einer PCH-Datei verarbeitet wirken sich auf die Datei, mit der die PCH-Datei anschließend verwendet wird. Die `comment` und `message` Pragmas wirken sich nicht auf den Rest der Kompilierung.  
  
Diese Pragmas beeinflussen nur den Code innerhalb der PCH-Datei; Sie haben keine Auswirkungen auf Code, der anschließend die PCH-Datei verwendet:  
  
||||  
|-|-|-|  
|`comment`|`page`|`subtitle`|  
|`linesize`|`pagesize`|`title`|  
|`message`|`skip`||  
  
Diese Pragmas als Teil einer vorkompilierten Headerdatei beibehalten werden und Einfluss auf den Rest der Kompilierung, die des vorkompilierten Headers verwendet:  
  
||||  
|-|-|-|  
|`alloc_text`|`include_alias`|`pack`|  
|`auto_inline`|`init_seg`|`pointers_to_members`|  
|`check_stack`|`inline_depth`|`setlocale`|  
|`code_seg`|`inline_recursion`|`vtordisp`|  
|`data_seg`|`intrinsic`|`warning`|  
|`function`|`optimize`||  
  
<a name="consistency-rules-for-yc-and-yu"></a>  
  
## <a name="consistency-rules-for-yc-and-yu"></a>Konsistenzregeln für "/Yc" und "/Yu"  
  
Bei Verwendung einer vorkompilierten Headerdatei, die mit "/ Yc" oder "/ Yu" erstellt vergleicht der Compiler der aktuellen kompilierungsumgebung demjenigen, den befanden, während Sie die PCH-Datei erstellt. Achten Sie darauf, dass Sie eine Umgebung, die konsistent mit der vorherigen Abfrage (mit konsistenten Compileroptionen, Pragmas, usw.) für die aktuelle Kompilierung angeben. Wenn der Compiler eine Inkonsistenz erkannt wird, eine Warnung ausgegeben und Inkonsistenzen bezeichnet, sofern möglich. Solche Warnungen nicht unbedingt auf ein Problem mit der PCH-Datei hinweisen; Sie warnen lediglich vor möglichen Konflikten. In den folgenden Abschnitten wird erläutert, die konsistenzanforderungen für vorkompilierten Header.  
  
### <a name="compiler-option-consistency"></a>Konsistenz von Compileroptionen  
  
Diese Tabelle enthält Optionen für den Compiler, die eine Inkonsistenz Warnung auslösen könnte bei Verwendung einer vorkompilierten Headerdatei an:  
  
|Option|name|Regel|  
|------------|----------|----------|  
|/D|Definieren von Konstanten und Makros|Zwischen der Kompilierung, die den vorkompilierten Header erstellt und der aktuellen Kompilierung identisch sein muss. Der Status der definierten Konstanten wird nicht überprüft, aber zu unvorhersehbaren Ergebnissen führt können auftreten, wenn die Dateien von den Werten der geänderten Konstanten abhängen.|  
|/ E oder/EP|Kopieren der Präprozessorausgabe in die Standardausgabe|Vorkompilierte Header funktionieren nicht mit der Option/e oder/EP.|  
|/ FR oder/fr|Microsoft Source Browserinformationen generieren|Für die Optionen "/ fr und/fr" mit der Option "/ Yu" gültig ist muss auch faktisch gewesen, wenn der vorkompilierte Header erstellt wurde. Nachfolgende Kompilierungen, die Verwendung des vorkompilierten Headers generieren auch Browserinformationen Quelle. Browserinformationen befindet sich in einer einzelnen SBR-Datei und anderen Dateien auf die gleiche Weise wie Codeansichtsinformationen verwiesen wird. Sie können die Platzierung der Quelle Browserinformationen nicht überschreiben.|  
|/ GA/GD, / ge/GW oder/GW|Windows-Protokolloptionen|Zwischen der Kompilierung, die den vorkompilierten Header erstellt und der aktuellen Kompilierung identisch sein muss. Wenn diese Optionen voneinander abweichen, führt eine Warnmeldung angezeigt.|  
|/ZI|Vollständige Debuginformationen generieren|Wenn diese Option aktiviert ist, wenn der vorkompilierte Header erstellt wird, können nachfolgende Kompilierungen, die die Vorkompilierung verwenden, Debuginformationen zu verwenden. Kompilierungen, die Vorkompilierung und die/ZI-Option verwenden, wenn/Zi nicht aktiviert ist, wenn der vorkompilierte Header erstellt wird, eine Warnung ausgelöst. Die Debuginformationen in der aktuellen Objektdatei platziert wird, und lokale Symbole im vorkompilierten Header definiert sind nicht verfügbar, die im Debugger.|  
  
> [!NOTE]
>  Die vorkompilierte Header-Funktion ist nur in C und C++-Quelldateien vorgesehen.  
  
<a name="using-precompiled-headers-in-a-project"></a>  
  
## <a name="using-precompiled-headers-in-a-project"></a>Verwenden von vorkompilierten Headern in einem Projekt  
  
Vorherigen Abschnitte enthalten eine Übersicht über vorkompilierter Header: "/ Yc" und "/ Yu", die/Fp-Option und die [Hdrstop](../../preprocessor/hdrstop.md) Pragma. In diesem Abschnitt wird beschrieben, eine Methode für die Verwendung der manuellen Optionen für vorkompilierte Header in einem Projekt; Der Abschnitt endet mit einer Beispiel-Makefile und den Code, den er verwaltet.  
  
Untersuchen Sie für einen anderen Ansatz, verwenden die manuellen Optionen für vorkompilierte Header in einem Projekt den Makefiles befindet sich im Verzeichnis MFC\SRC, das bei der Standardinstallation von Visual C++ erstellt wird. Diese Makefiles einen ähnlichen Ansatz mit dem in diesem Abschnitt dargestellt werden, aber größer Nutzen von Microsoft Program Maintenance Utility (NMAKE) Makros und bieten mehr Kontrolle des Buildprozesses.  
  
<a name="pch-files-in-the-build-process"></a>  
  
## <a name="pch-files-in-the-build-process"></a>PCH-Dateien im Erstellungsvorgang  
  
Die Codebasis des einem Softwareprojekt ist normalerweise in mehrere C oder C++-Quelldateien, Objektdateien, Bibliotheken und Header-Dateien enthalten. In der Regel koordiniert ein Makefile die Kombination dieser Elemente in einer ausführbaren Datei. Die folgende Abbildung zeigt die Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet. Die Namen der NMAKE-Makros und die Dateinamen in diesem Diagramm sind mit denen in für Beispielcode, der konsistent [Beispielmakefile für PCH](#sample-makefile-for-pch) und [Beispielcode für PCH](#example-code-for-pch).  
  
Die Abbildung verwendet drei Verbindungskabel als Diagramm Medien, um den Fluss des Buildprozesses anzuzeigen. Jede Datei bzw. das Makro die benannt werden Rechtecke darstellen. die drei Makros stellen eine oder mehrere Dateien dar. Schattierte Bereiche darstellen, jede Kompilier- oder Aktion. Pfeile zeigen, welche Dateien und Makros während der Kompilierung oder Verknüpfungsvorgang kombiniert werden.  
  
![Makefiles, das eine vorkompilierte Headerdatei verwendet](../../build/reference/media/vc30ow1.gif "Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet")  
##### <a name="structure-of-a-makefile-that-uses-a-precompiled-header-file"></a>Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet  
  
Am oberen Rand des Diagramms sind STABLEHDRS und ist NMAKE-Makros, die in denen Sie Dateien, die wahrscheinlich nicht benötigt, die Neukompilierung auflisten. Diese Dateien werden von der Befehlszeichenfolge kompiliert.  
  
`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`  
  
nur, wenn die vorkompilierte Headerdatei (STABLE.pch) nicht vorhanden ist oder wenn Sie die Dateien ändern, die in die beiden Makros aufgelistet werden. In beiden Fällen enthält die vorkompilierte Headerdatei Code nur aus den Dateien im Makro STABLEHDRS aufgelistet. Liste der letzten Datei, in dem ist-Makro vorkompiliert werden soll.  
  
Die Dateien, die Sie in diesen Makros auflisten möglich Headerdateien oder C- oder C++-Quelldateien. (Eine einzelne PCH-Datei kann nicht mit C- und C++-Modulen verwendet werden.) Beachten Sie, die Sie verwenden können, die **Hdrstop** Makro Vorkompilierung irgendwann in der Datei ist beendet. Finden Sie unter [Hdrstop](../../preprocessor/hdrstop.md) für Weitere Informationen.  
  
Fortfahren nach unten im Diagramm stellt APPLIB.obj Unterstützungscode, die in der endgültigen Anwendung verwendet. Sie wird aus APPLIB.cpp erstellt, die Dateien im Makro UNSTABLEHDRS aufgeführt und vorkompilierter Code aus dem vorkompilierten Header.  
  
MYAPP.obj stellt die endgültige Anwendung dar. Sie wird aus MYAPP.cpp erstellt, die Dateien im Makro UNSTABLEHDRS aufgeführt und vorkompilierter Code aus dem vorkompilierten Header.  
  
Zum Schluss die ausführbare Datei ("MyApp". EXE-Datei) wird erstellt, indem Sie eine Verknüpfung im OBJS Makro (APPLIB.obj und MYAPP.obj) aufgelisteten Dateien.  
  
<a name="sample-makefile-for-pch"></a>  
  
## <a name="sample-makefile-for-pch"></a>Beispielmakefile für PCH  
  
Die folgenden Makefile verwendet Makros und ein! IF-! #ELSE! ENDIF flusssteuerung Befehl-Struktur, die die Anpassung an das Projekt zu vereinfachen.  
  
```NMAKE  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
Abgesehen von den STABLEHDRS ist und UNSTABLEHDRS Makros, die in der Abbildung "Struktur von einer Makefile, verwendet eine vorkompilierte Headerdatei" dargestellt wird, [PCH-Dateien im Erstellungsvorgang](#pch-files-in-the-build-process), dieses Makefile bietet ein CLFLAGS-Makro sowie ein LINKFLAGS Makro. Sie müssen diese Makros verwenden, um die Liste von Linkeroptionen für Compiler und, die angewendet werden, ob eine Debug- oder eine endgültige Version der ausführbaren Datei der Anwendung erstellt werden. Es gibt auch ein Makro BIBLIOTHEKEN, in dem Sie die Bibliotheken auflisten, das Projekt erforderlich ist.  
  
Das Makefile verwendet auch! IF-! #ELSE! ENDIF, um festzustellen, ob Sie eine DEBUG-Symbol in der Befehlszeile NMAKE definieren:  
  
```NMAKE  
NMAKE DEBUG=[1|0]  
```  
  
Diese Funktion ermöglicht das für die Verwendung der gleichen Makefiles während der Entwicklung und für die letzten Versionen des Programms – verwenden Sie DEBUG = 0 für den endgültigen Produktversionen. Die folgenden Befehlszeilen sind gleichwertig:  
  
```NMAKE  
NMAKE   
NMAKE DEBUG=0  
```  
  
Weitere Informationen zu Makefiles finden Sie unter [NMAKE-Referenz](../../build/nmake-reference.md). Siehe auch [Compileroptionen](../../build/reference/compiler-options.md) und [Optionen des Linkers](../../build/reference/linker-options.md).  
  
<a name="example-code-for-pch"></a>  
  
## <a name="example-code-for-pch"></a>Beispielcode für PCH  
  
Die folgenden Quelldateien werden in die in beschriebenen Makefile verwendet [PCH-Dateien im Erstellungsvorgang](#pch-files-in-the-build-process) und [Beispielmakefile für PCH](#sample-makefile-for-pch). Beachten Sie, dass die Kommentare wichtige Informationen enthalten.  
  
```cpp  
// ANOTHER.H : Contains the interface to code that is not  
//             likely to change.  
//  
#ifndef __ANOTHER_H  
#define __ANOTHER_H  
#include<iostream>  
void savemoretime( void );  
#endif // __ANOTHER_H  
```  
  
```cpp  
// STABLE.H : Contains the interface to code that is not likely  
//            to change. List code that is likely to change   
//            in the makefile's STABLEHDRS macro.  
//  
#ifndef __STABLE_H  
#define __STABLE_H  
#include<iostream>  
void savetime( void );  
#endif // __STABLE_H  
```  
  
```cpp  
// UNSTABLE.H : Contains the interface to code that is  
//              likely to change. As the code in a header  
//              file becomes stable, remove the header file  
//              from the makefile's UNSTABLEHDR macro and list  
//              it in the STABLEHDRS macro.  
//  
#ifndef __UNSTABLE_H  
#define __UNSTABLE_H  
#include<iostream.h>  
void notstable( void );  
#endif // __UNSTABLE_H  
```  
  
```cpp
// APPLIB.CPP : This file contains the code that implements  
//              the interface code declared in the header  
//              files STABLE.H, ANOTHER.H, and UNSTABLE.H.  
//  
#include"another.h"  
#include"stable.h"  
#include"unstable.h"  
// The following code represents code that is deemed stable and  
// not likely to change. The associated interface code is  
// precompiled. In this example, the header files STABLE.H and  
// ANOTHER.H are precompiled.  
void savetime( void )  
    { cout << "Why recompile stable code?\n"; }  
void savemoretime( void )  
    { cout << "Why, indeed?\n\n"; }  
// The following code represents code that is still under  
// development. The associated header file is not precompiled.  
void notstable( void )  
    { cout << "Unstable code requires"  
            << " frequent recompilation.\n"; 
    }  
```  
  
```cpp
// MYAPP.CPP : Sample application  
//             All precompiled code other than the file listed  
//             in the makefile's BOUNDRY macro (stable.h in  
//             this example) must be included before the file  
//             listed in the BOUNDRY macro. Unstable code must  
//             be included after the precompiled code.  
//  
#include"another.h"  
#include"stable.h"  
#include"unstable.h"  
int main( void )  
{  
    savetime();  
    savemoretime();  
    notstable();  
}  
```  
    
## <a name="see-also"></a>Siehe auch  
[Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)   
[Compileroptionen](../../build/reference/compiler-options.md)