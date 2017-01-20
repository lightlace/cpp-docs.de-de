---
title: "Potenzielle Fehler bei der &#220;bergabe von CRT-Objekten &#252;ber DLL-Grenzen"
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
  - "C"
helpviewer_keywords: 
  - "DLL-Konflikte [C++]"
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Potenzielle Fehler bei der &#220;bergabe von CRT-Objekten &#252;ber DLL-Grenzen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie übergeben, wendet C\-Laufzeit \(CRT\) wie Dateihandles, Gebietsschemas und Umgebungsvariablen in ein, oder aus einer DLL \(Funktionsaufrufe über der DLL\-Grenze\) auschecken, kann unerwartetes Verhalten auftreten, wenn die DLL sowie von Dateien, die in die DLL aufrufen, unterschiedliche Kopien der CRT\-Bibliotheken verwenden.  
  
 Ein verwandtes Problem kann auftreten, wenn Sie Speicher belegen \(entweder explizit mit `new` oder `malloc` oder implizit mit `strdup`, `strstreambuf::str`, z.\) und dann einen Zeiger über eine freigegeben werden DLL\-führen Begrenzung.  Dies kann eine Speicherzugriffsverletzung verursachen oder Beschädigung häufen, wenn die DLL und ihre Benutzer unterschiedliche Kopien der CRT\-Bibliotheken verwenden.  
  
 Ein weiteres Symptom dieses Problems kann ein Fehler im Ausgabefenster während des Debuggens wie sein:  
  
 HEAP\[\]: Ungültige Adresse angegebene zu RtlValidateHeap \(\#,\#\)  
  
## Ursachen  
 Jede Kopie der CRT\-Bibliothek gelten separate und anderen Zustand.  Als solche Objekte wie CRT, Dateihandles Umgebungsvariablen ein, Gebietsschemas und sind für die Kopie des CRT nur gültig, in das diese Objekte zugeordnet oder festgelegt werden.  Wenn eine DLL und ihre Benutzer unterschiedliche Kopien der CRT\-Bibliothek verwenden, können Sie diese CRT\-Objekte über der DLL\-Grenze nicht übergeben und sie davon ausgehen, auf der anderen Seite ordnungsgemäß übernommen werden.  
  
 Da jede Kopie der CRT\-Bibliothek den eigenen Heapmanager verfügt, Speicher belegend in einer CRT\-Bibliothek und den Zeiger über eine durch eine andere Kopie der CRT\-Bibliothek gemeinsam genutzt DLL\-Grenze, stellt eine mögliche Ursache für Heapbeschädigung beginnt.  
  
 Falls die DLL entwerfen, dass sie CRT\-Objekte über die Begrenzung hinweg wird oder es, außerhalb der DLL gemeinsam genutzt belegt und erwartet, sollten Sie die DLL\-Benutzer ein, um die gleiche Kopie der CRT\-Bibliothek wie die DLL zu verwenden.  Die DLL und ihre Benutzer verwenden die gleiche Kopie der CRT\-Bibliothek, wenn beide mit derselben Version der CRT\-DLL verknüpft werden.  Dies kann ein Problem darstellen, wenn Sie Anwendungen kombinieren, die mit Visual C\+\+ 5.0 mit DLLs erstellt werden, die von Visual C\+\+ 4.1 oder früher erstellt werden.  Da die DLL\-Version der CRT\-Bibliothek, die von Visual C\+\+ 4.1, verwendete msvcrt40.dll ist und das, die von Visual 5,0, verwendete msvcrt.dll ist, können Sie die Anwendung nicht erstellen, die gleiche Kopie der CRT\-Bibliothek wie diese DLLs verwenden.  
  
 Es gibt jedoch eine Ausnahme.  In Version englischer US und in einigen anderen lokalisierten Versionen von Windows 2000, z Deutschem, Französisch und Tschechen, wird eine Weiterleitungsversion des msvcrt40.dll \(Version 4.20\) enthalten.  Folglich obwohl die DLL mit msvcrt40.dll verknüpft wird und der Benutzer mit msvcrt.dll verknüpft ist, verwenden Sie die gleiche Kopie der CRT\-Bibliothek, da alle Aufrufe, die zu msvcrt40.dll ausgeführt werden, an msvcrt.dll weitergeleitet werden.  
  
 Es ist dieser Weiterleitungsversion von msvcrt40.dll nicht in verschiedenen lokalisierten Versionen von Windows 2000, z Japanisch, Koreanisch und Chinesisch verfügbar.  Wenn die Anwendung auf diese Betriebssysteme abzielt, müssen Sie entweder erhalten eine aktualisierte Version der DLL, die nicht auf msvcrt40.dll beruht oder ändern die Anwendung, nicht für die Anwendung die gleiche Kopie der CRT\-Bibliotheken zu verlassen.  Wenn Sie die DLL entwickelt haben, bedeutet diese Neuerstellen sie mit Visual C\+\+ 4.2 oder höher.  Wenn eine DLL von Drittanbietern ist, müssen Sie dem Anbieter für ein Upgrade wenden.  
  
 Beachten Sie, dass diese Weiterleitung DLL\-Version von msvcrt40.dll \(Version 4.20\) nicht verteilt werden kann.  
  
## Beispiel  
  
### **Beschreibung**  
 In diesem Beispiel führt ein Dateihandle über eine DLL\-Grenze.  
  
 Die DLL und die EXE\-Datei mit \/MD erstellt werden, sodass sie eine einzige Kopie des CRT frei.  
  
 Wenn Sie mit \/MT neu erstellen, damit sie eigene Kopien des CRT verwenden, führt das Ausführen des resultierenden test1Main.exe eine Zugriffsverletzung.  
  
### Code  
  
```  
// test1Dll.cpp  
// compile with: /MD /LD  
#include <stdio.h>  
__declspec(dllexport) void writeFile(FILE *stream)  
{  
   char   s[] = "this is a string\n";  
   fprintf( stream, "%s", s );  
   fclose( stream );  
}  
```  
  
### Code  
  
```  
// test1Main.cpp  
// compile with: /MD test1dll.lib  
#include <stdio.h>  
#include <process.h>  
void writeFile(FILE *stream);  
  
int main(void)  
{  
   FILE  * stream;  
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );  
   writeFile(stream);  
   system( "type fprintf.out" );  
}  
```  
  
### Ausgabe  
  
```  
this is a string  
```  
  
## Beispiel  
  
### **Beschreibung**  
 In diesem Beispiel führt Umgebungsvariablen über eine DLL\-Grenze.  
  
### Code  
  
```  
// test2Dll.cpp  
// compile with: /MT /LD  
#include <stdio.h>  
#include <stdlib.h>  
  
__declspec(dllexport) void readEnv()  
{  
   char *libvar;  
   size_t libvarsize;  
  
   /* Get the value of the MYLIB environment variable. */   
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );  
  
   if( libvar != NULL )  
      printf( "New MYLIB variable is: %s\n", libvar);  
   else  
      printf( "MYLIB has not been set.\n");  
   free( libvar );  
}  
```  
  
### Code  
  
```  
// test2Main.cpp  
// compile with: /MT /link test2dll.lib  
#include <stdlib.h>  
#include <stdio.h>  
  
void readEnv();  
  
int main( void )  
{  
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );  
   readEnv();  
}  
```  
  
### Ausgabe  
  
```  
MYLIB has not been set.  
```  
  
 Wenn die DLL und die EXE\-Datei mit \/MD erstellt werden, sodass nur eine Kopie des CRT verwendet wird, wird das Programm erfolgreich ausgeführt und erzeugt die folgende Ausgabe:  
  
```  
New MYLIB variable is: c:\mylib;c:\yourlib  
```  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)