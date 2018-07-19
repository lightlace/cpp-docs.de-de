---
title: Beenden oder zurückgeben mit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- return keyword [C++], using for program termination
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41c5d00efa0f827b9e1c3cd7f3647c966eed67e4
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943223"
---
# <a name="using-exit-or-return"></a>Verwenden von "exit" oder "return"
Beim Aufruf **beenden** oder führen Sie eine **zurückgeben** -Anweisung vom `main`, statische Objekte werden in umgekehrter Reihenfolge ihrer Initialisierung zerstört. Das folgende Beispiel zeigt, wie so eine Initialisierung und Bereinigung funktionieren.  
  
## <a name="example"></a>Beispiel  
  
```cpp 
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
  
 Im vorherigen Beispiel werden die statischen Objekte `sd1` und `sd2` vor der Eingabe in `main` erstellt und initialisiert. Nachdem das Programm beendet mit der **zurückgeben** -Anweisung, die erste `sd2` zerstört wird und dann `sd1`. Der Destruktor für die Klasse `ShowData` schließt die Dateien, die diesen statischen Objekten zugeordnet sind.   
  
 Eine andere Möglichkeit zum Schreiben des Codes besteht darin, die `ShowData`-Objekte mit dem Blockbereich zu deklarieren, sodass sie gelöscht werden, wenn sie den Gültigkeitsbereich verlassen:  
  
```cpp 
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)