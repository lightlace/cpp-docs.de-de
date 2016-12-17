---
title: "/GS (Puffer-Sicherheits&#252;berpr&#252;fung)"
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
  - "VC.Project.VCCLWCECompilerTool.BufferSecurityCheck"
  - "VC.Project.VCCLCompilerTool.BufferSecurityCheck"
  - "/GS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Puffer [C++], Pufferüberlauf"
  - "Pufferüberläufe, Compilerschalter /GS"
  - "GS (Compileroption) [C++]"
  - "/GS (Compileroption) [C++]"
  - "Sicherheitsüberprüfung (Compileroption) [C++]"
  - "-GS (Compileroption) [C++]"
  - "Puffer [C++], Vermeiden von Überläufen"
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
caps.latest.revision: 40
caps.handback.revision: "40"
ms.author: "corob"
manager: "ghogen"
---
# /GS (Puffer-Sicherheits&#252;berpr&#252;fung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erkennt einige Pufferüberläufe, welche die Rückgabeadresse einer Funktion, eine Ausnahmehandleradresse oder bestimmte Typen von Parametern überschreiben.  Einen Pufferüberlauf zu verursachen ist eine von Hackern verwendete Technik, um Code auszunutzen, der keine Puffergrößeneinschränkungen erzwingt.  
  
## Syntax  
  
```  
/GS[-]  
```  
  
## Hinweise  
 Standardmäßig ist **\/GS** aktiviert.  Verwenden Sie **\/GS\-**, wenn Sie davon ausgehen, dass die Anwendung keinerlei Sicherheitsrisiken ausgesetzt ist.  Weitere Informationen zu **\/GS** finden Sie unter [Compiler\-Sicherheitsprüfungen im Detail](http://go.microsoft.com/fwlink/?linkid=7260).  Weitere Informationen zum Unterdrücken der Pufferüberlauferkennung finden Sie unter [safebuffers](../../cpp/safebuffers.md).  
  
## Sicherheitsüberprüfungen  
 Bei Funktionen, die vom Compiler als überlaufgefährdet und problematisch eingestuft werden, reserviert der Compiler vor der Rückgabeadresse Speicherplatz auf dem Stapel.  Beim Funktionsstart wird der reservierte Platz mit einem *Sicherheitscookie* belegt, das beim Laden des Moduls berechnet wird.  Bei Funktionsende und beim Entladen von Rahmen auf 64\-Bit\-Betriebssystemen wird dann eine Hilfsfunktion aufgerufen, die sicherstellt, dass sich der Wert des Cookies nicht geändert hat.  Ein abweichender Wert gibt an, dass der Stapel möglicherweise überschrieben wurde.  Ein abweichender Wert führt dazu, dass der Prozess beendet wird.  
  
## GS\-Puffer  
 Eine Pufferüberlauf\-Sicherheitsüberprüfung wird in einem *GS\-Puffer* ausgeführt.  Ein GS\-Puffer kann einer der Folgenden sein:  
  
-   Ein Array, das größer als 4 Bytes ist und über mehr als zwei Elemente sowie einen Elementtyp verfügt, der kein Zeigertyp ist.  
  
-   Eine Datenstruktur, die größer als 8 Bytes ist und keine Zeiger enthält.  
  
-   Ein mit der [\_alloca](../../c-runtime-library/reference/alloca.md)\-Funktion reservierter Puffer.  
  
-   Eine beliebige Klasse oder Struktur, die einen GS\-Puffer enthält.  
  
 Beispielsweise werden GS\-Puffer durch die folgenden Anweisungen deklariert.  
  
```  
char buffer[20];  
int buffer[20];  
struct { int a; int b; int c; int d; } myStruct;  
struct { int a; char buf[20]; };  
```  
  
 Die folgenden Anweisungen deklarieren jedoch keine GS\-Puffer.  Die ersten beiden Deklarationen enthalten Elemente des Zeigertyps.  Die dritte und vierte Anweisung deklariert Arrays, deren Größe zu klein ist.  Die fünfte Anweisung deklariert eine Struktur, deren Größe auf einer x86\-Plattform nicht mehr als 8 Bytes beträgt.  
  
```  
char *pBuf[20];  
void *pv[20];  
char buf[4];  
int buf[2];  
struct { int a; int b; };  
```  
  
## Initialisieren des Sicherheitscookies  
 Die **\/GS**\-Compileroption erfordert, dass das Sicherheitscookie initialisiert wird, bevor eine Funktion, die das Cookie verwendet, ausgeführt wird.  Das Sicherheitscookie muss beim Einstieg in eine EXE oder DLL initialisiert werden.  Dies geschieht automatisch, wenn die CTR\-Standardeinstiegspunkte \(mainCRTStartup, wmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup oder \_DllMainCRTStartup\) verwendet werden.  Wenn Sie einen alternativen Einstiegspunkt verwenden, müssen Sie das Sicherheitscookie manuell initialisieren, indem Sie [\_\_security\_init\_cookie](../../c-runtime-library/reference/security-init-cookie.md) aufrufen.  
  
## Geschützte Informationen  
 Die **\/GS**\-Compileroption schützt folgende Elemente:  
  
-   Die Rückgabeadresse eines Funktionsaufrufs.  
  
-   Die Adresse eines Ausnahmehandlers für eine Funktion.  
  
-   Anfällige Funktionsparameter.  
  
 **\/GS** versucht auf allen Plattformen, Pufferüberläufe in die Rücksprungadresse zu ermitteln.  Auf Plattformen wie x86 und x64 mit Aufrufkonventionen, durch welche die Rücksprungadresse eines Funktionsaufrufes auf dem Stapel gespeichert wird, lassen sich Pufferüberläufe leichter ausnutzen.  
  
 Wird auf x86\-Systemen ein Ausnahme\-Handler verwendet, fügt der Compiler ein Sicherheitscookie ein, um die Adresse des Ausnahmehandlers zu schützen.  Dieses Cookie wird beim Entladen von Rahmen überprüft.  
  
 **\/GS** bietet auch Schutz vor *verwundbaren Parametern,* die einer Funktion übergeben werden.  Ein verwundbarer Parameter ist ein Zeiger, ein C\+\+\-Verweis oder eine C\-Struktur \(C\+\+\-POD\-Typ\), die einen Zeiger oder einen GS\-Puffer enthält.  
  
 Ein verwundbarer Parameter wird vor dem Cookie und den lokalen Variablen zugeordnet.  Durch einen Pufferüberlauf kann dieser Parameter überschrieben werden.  Und der in der Funktion enthaltene Code, der diesen Parameter verwendet, könnte einen Angriff verursachen, bevor der Rücksprung aus der Funktion erfolgt und die Sicherheitsprüfung ausgeführt wird.  Um diese Gefahr zu minimieren, erstellt der Compiler während des Funktionsprologs eine Kopie der verwundbaren Parameter und legt diese unterhalb des Speicherbereichs ab, in dem sich sämtliche Puffer befinden.  
  
 Der Compiler erstellt keine Kopien verwundbarer Parameter, wenn folgende Bedingungen erfüllt sind:  
  
-   Funktionen enthalten keinen GS\-Puffer.  
  
-   Optimierungen \([\/O\-Optionen](../../build/reference/o-options-optimize-code.md)\) sind nicht aktiviert.  
  
-   Funktionen verfügen über eine variable Argumentliste \(...\).  
  
-   Funktionen sind mit [naked](../../cpp/naked-cpp.md) markiert.  
  
-   Funktionen enthalten Inlineassemblycode in der ersten Anweisung.  
  
-   Ein Parameter wird nur auf eine Art und Weise verwendet, die im Falle eines Pufferüberlaufs höchstwahrscheinlich nicht ausgenutzt werden kann.  
  
## Nicht geschützte Informationen  
 Die **\/GS**\-Compileroption bietet keinen Schutz vor allen Sicherheitsangriffen durch Pufferüberläufe.  Wenn ein Objekt beispielsweise einen Puffer und eine vtable enthält, könnte der Pufferüberlauf die vtable beschädigen.  
  
 Auch wenn Sie **\/GS** verwenden, versuchen Sie immer, sicheren Code zu schreiben, der keine Pufferüberläufe ermöglicht.  
  
#### So legen Sie diese Compileroption in Visual Studio fest  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.  
  
     Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie im Dialogfeld **Eigenschaftenseiten** auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Codegenerierung**.  
  
4.  Ändern Sie die Eigenschaft **Puffer\-Sicherheitsüberprüfung**.  
  
#### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck*>.  
  
## Beispiel  
 In diesem Beispiel wird ein Pufferüberlauf stattfinden.  Dadurch versagt die Anwendung zur Laufzeit.  
  
```  
// compile with: /c /W1  
#include <cstring>  
#include <stdlib.h>  
#pragma warning(disable : 4996)   // for strcpy use  
  
// Vulnerable function  
void vulnerable(const char *str) {  
   char buffer[10];  
   strcpy(buffer, str); // overrun buffer !!!  
  
   // use a secure CRT function to help prevent buffer overruns  
   // truncate string to fit a 10 byte buffer  
   // strncpy_s(buffer, _countof(buffer), str, _TRUNCATE);  
}  
  
int main() {  
   // declare buffer that is bigger than expected  
   char large_buffer[] = "This string is longer than 10 characters!!";  
   vulnerable(large_buffer);  
}  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)