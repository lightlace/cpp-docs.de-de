---
title: "Verwenden von &quot;exit&quot; oder &quot;return&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit-Funktion"
  - "return-Schlüsselwort [C++], Verwendung zur Programmbeendigung"
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Verwenden von &quot;exit&quot; oder &quot;return&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie **exit** aufrufen oder eine `return`\-Anweisung aus **main** ausführen, werden statische Objekte in umgekehrter Reihenfolge ihrer Initialisierung gelöscht.  Das folgende Beispiel zeigt, wie so eine Initialisierung und Bereinigung funktionieren.  
  
## Beispiel  
  
```  
// using_exit_or_return1.cpp  
#include <stdio.h>  
class ShowData {  
public:  
   // Constructor opens a file.  
   ShowData( const char *szDev ) {  
   errno_t err;  
      err = fopen_s(&OutputDev, szDev, "w" );  
   }  
  
   // Destructor closes the file.  
   ~ShowData() { fclose( OutputDev ); }  
  
   // Disp function shows a string on the output device.  
   void Disp( char *szData ) {   
      fputs( szData, OutputDev );  
   }  
private:  
   FILE *OutputDev;  
};  
  
//  Define a static object of type ShowData. The output device  
//   selected is "CON" -- the standard output device.  
ShowData sd1 = "CON";  
  
//  Define another static object of type ShowData. The output  
//   is directed to a file called "HELLO.DAT"  
ShowData sd2 = "hello.dat";  
  
int main() {  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
 Im vorherigen Beispiel werden die statischen Objekte `sd1` und `sd2` vor der Eingabe in `main` erstellt und initialisiert.  Nachdem das Programm mithilfe der `return`\-Anweisung beendet ist, wird zuerst `sd2` und danach `sd1` gelöscht.  Der Destruktor für die Klasse `ShowData` schließt die Dateien, die diesen statischen Objekten zugeordnet sind. \(Weitere Informationen über die Initialisierung, Konstruktoren und Destruktoren finden Sie unter [Spezielle Memberfunktionen](../misc/special-member-functions-cpp.md)\).  
  
 Eine andere Möglichkeit zum Schreiben des Codes besteht darin, die `ShowData`\-Objekte mit dem Blockbereich zu deklarieren, sodass sie gelöscht werden, wenn sie den Gültigkeitsbereich verlassen:  
  
```  
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)