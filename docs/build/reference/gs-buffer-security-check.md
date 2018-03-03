---
title: "-GS (Puffer-Sicherheitsüberprüfung) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BufferSecurityCheck
- VC.Project.VCCLCompilerTool.BufferSecurityCheck
- /GS
dev_langs:
- C++
helpviewer_keywords:
- buffers [C++], buffer overruns
- buffer overruns, compiler /GS switch
- GS compiler option [C++]
- /GS compiler option [C++]
- security check compiler option [C++]
- -GS compiler option [C++]
- buffers [C++], avoiding overruns
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e5699830a090f42feb92b24ec43fbae36634c4df
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="gs-buffer-security-check"></a>/GS (Puffer-Sicherheitsüberprüfung)  
  
Erkennt einige Pufferüberläufe, welche die Rückgabeadresse einer Funktion, eine Ausnahmehandleradresse oder bestimmte Typen von Parametern überschreiben. Einen Pufferüberlauf zu verursachen ist eine von Hackern verwendete Technik, um Code auszunutzen, der keine Puffergrößeneinschränkungen erzwingt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GS[-]  
```  
  
## <a name="remarks"></a>Hinweise  
  
**/ GS** ist standardmäßig aktiviert. Wenn Sie erwarten, die Anwendung keinerlei Sicherheitsrisiken ausgesetzt ist dass, verwenden Sie **/GS-**. Weitere Informationen zu **/GS**, finden Sie unter [Compiler Security überprüft In Depth](http://go.microsoft.com/fwlink/p/?linkid=7260). Weitere Informationen zum Unterdrücken von Pufferüberlauf-Erkennung, finden Sie unter [Safebuffers](../../cpp/safebuffers.md).  
  
## <a name="security-checks"></a>Sicherheitsüberprüfungen  
  
Bei Funktionen, die vom Compiler als überlaufgefährdet und problematisch eingestuft werden, reserviert der Compiler vor der Rückgabeadresse Speicherplatz auf dem Stapel. Beim Funktionsstart, der zugewiesene Speicherplatz mit geladen wurde eine *Sicherheitscookie* einmal beim Laden des Moduls berechnet wird. Bei Funktionsende und beim Entladen von Rahmen auf 64-Bit-Betriebssystemen wird dann eine Hilfsfunktion aufgerufen, die sicherstellt, dass sich der Wert des Cookies nicht geändert hat. Ein abweichender Wert gibt an, dass der Stapel möglicherweise überschrieben wurde. Ein abweichender Wert führt dazu, dass der Prozess beendet wird.  
  
## <a name="gs-buffers"></a>GS-Puffer  
  
Eine Pufferüberlauf-sicherheitsüberprüfung erfolgt auf einer *GS-Puffer*. Ein GS-Puffer kann einer der Folgenden sein:  
  
-   Ein Array, das größer als 4 Bytes ist und über mehr als zwei Elemente sowie einen Elementtyp verfügt, der kein Zeigertyp ist.  
  
-   Eine Datenstruktur, die größer als 8 Bytes ist und keine Zeiger enthält.  
  
-   Ein Pufferspeicher mithilfe der [_alloca](../../c-runtime-library/reference/alloca.md) Funktion.  
  
-   Eine beliebige Klasse oder Struktur, die einen GS-Puffer enthält.  
  
Beispielsweise werden GS-Puffer durch die folgenden Anweisungen deklariert.  
  
```cpp  
char buffer[20];  
int buffer[20];  
struct { int a; int b; int c; int d; } myStruct;  
struct { int a; char buf[20]; };  
```  
  
Die folgenden Anweisungen deklarieren jedoch keine GS-Puffer. Die ersten beiden Deklarationen enthalten Elemente des Zeigertyps. Die dritte und vierte Anweisung deklariert Arrays, deren Größe zu klein ist. Die fünfte Anweisung deklariert eine Struktur, deren Größe auf einer x86-Plattform nicht mehr als 8 Bytes beträgt.  
  
```cpp  
char *pBuf[20];  
void *pv[20];  
char buf[4];  
int buf[2];  
struct { int a; int b; };  
```  
  
## <a name="initialize-the-security-cookie"></a>Initialisieren des Sicherheitscookies  
  
Die **/GS** -Compileroption erfordert, dass das Sicherheitscookie initialisiert werden, bevor eine Funktion, die das Cookie wird verwendet, ausgeführt wird. Das Sicherheitscookie muss beim Einstieg in eine EXE oder DLL sofort initialisiert werden. Dies erfolgt automatisch bei der Verwendung der Standardeinstellung VCRuntime-Einstiegspunkte: MainCRTStartup, WmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup, oder den _DllMainCRTStartup. Wenn Sie einen alternativen Einstiegspunkt verwenden, müssen Sie das Sicherheitscookie manuell initialisieren, durch den Aufruf [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md).  
  
## <a name="what-is-protected"></a>Geschützte Informationen  
  
Die **/GS** -Compileroption schützt folgende Elemente:  
  
-   Die Rückgabeadresse eines Funktionsaufrufs.  
  
-   Die Adresse eines Ausnahmehandlers für eine Funktion.  
  
-   Anfällige Funktionsparameter.  
  
Auf allen Plattformen **/GS** versucht, Pufferüberläufe in die Rücksprungadresse zu ermitteln. Auf Plattformen wie x86 und x64 mit Aufrufkonventionen, durch welche die Rücksprungadresse eines Funktionsaufrufes auf dem Stapel gespeichert wird, lassen sich Pufferüberläufe leichter ausnutzen.  
  
Wird auf x86-Systemen ein Ausnahme-Handler verwendet, fügt der Compiler ein Sicherheitscookie ein, um die Adresse des Ausnahmehandlers zu schützen. Dieses Cookie wird beim Entladen von Rahmen überprüft.  
  
**/ GS** schützt *verwundbaren Parametern* , die in eine Funktion übergeben werden. Ein verwundbarer Parameter ist ein Zeiger, ein C++-Verweis oder eine C-Struktur (C++-POD-Typ), die einen Zeiger oder einen GS-Puffer enthält.  
  
Ein verwundbarer Parameter wird vor dem Cookie und den lokalen Variablen zugeordnet. Durch einen Pufferüberlauf kann dieser Parameter überschrieben werden. Und der in der Funktion enthaltene Code, der diesen Parameter verwendet, könnte einen Angriff verursachen, bevor der Rücksprung aus der Funktion erfolgt und die Sicherheitsprüfung ausgeführt wird. Um diese Gefahr zu minimieren, erstellt der Compiler während des Funktionsprologs eine Kopie der verwundbaren Parameter und legt diese unterhalb des Speicherbereichs ab, in dem sich sämtliche Puffer befinden.  
  
Der Compiler erstellt keine Kopien verwundbarer Parameter, wenn folgende Bedingungen erfüllt sind:  
  
-   Funktionen enthalten keinen GS-Puffer.  
  
-   Optimierungen ([/o-Optionen](../../build/reference/o-options-optimize-code.md)) sind nicht aktiviert.  
  
-   Funktionen verfügen über eine variable Argumentliste (...).  
  
-   Funktionen, die mit markiert sind [naked](../../cpp/naked-cpp.md).  
  
-   Funktionen enthalten Inlineassemblycode in der ersten Anweisung.  
  
-   Ein Parameter wird nur auf eine Art und Weise verwendet, die im Falle eines Pufferüberlaufs höchstwahrscheinlich nicht ausgenutzt werden kann.  
  
## <a name="what-is-not-protected"></a>Nicht geschützte Informationen  
  
Die **/GS** -Compileroption schützt nicht vor allen Sicherheitsangriffen durch Pufferüberläufe Angriffen. Wenn ein Objekt beispielsweise einen Puffer und eine vtable enthält, könnte der Pufferüberlauf die vtable beschädigen.  
  
Selbst bei Verwendung von **/GS**, versuchen Sie immer, sicheren Code zu schreiben, der keine Pufferüberläufe.  
  
### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.  
  
     Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  In der **Eigenschaftenseiten** (Dialogfeld), klicken Sie auf die **C/C++-** Ordner.  
  
3.  Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.  
  
4.  Ändern der **Puffer-Sicherheitsüberprüfung** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>.  
  
## <a name="example"></a>Beispiel  
  
In diesem Beispiel wird ein Pufferüberlauf stattfinden. Dadurch versagt die Anwendung zur Laufzeit.  
  
```C  
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
  
## <a name="see-also"></a>Siehe auch  
  
[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)